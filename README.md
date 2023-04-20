# stunning-umbrellaimport java.util.ArrayList;
import java.util.Collections;
import java.util.Random;
import java.util.Scanner;

public class TarotCardApp {
    
    private static ArrayList<String> tarotDeck;
    private static Random random;
    
    public static void main(String[] args) {
        initializeDeck();
        shuffleDeck();
        
        Scanner scanner = new Scanner(System.in);
        System.out.println("Welcome to the Tarot Card App!");
        System.out.println("What would you like to do? (1) Shuffle and draw a card, (2) Quit");
        
        int choice = scanner.nextInt();
        while (choice != 2) {
            switch (choice) {
                case 1:
                    drawCard();
                    break;
                default:
                    System.out.println("Invalid choice, please try again.");
                    break;
            }
            
            System.out.println("What would you like to do next? (1) Shuffle and draw a card, (2) Quit");
            choice = scanner.nextInt();
        }
        
        scanner.close();
    }
    
    private static void initializeDeck() {
        tarotDeck = new ArrayList<>();
        tarotDeck.add("The Fool");
        tarotDeck.add("The Magician");
        tarotDeck.add("The High Priestess");
        tarotDeck.add("The Empress");
        tarotDeck.add("The Emperor");
        tarotDeck.add("The Hierophant");
        tarotDeck.add("The Lovers");
        tarotDeck.add("The Chariot");
        tarotDeck.add("Strength");
        tarotDeck.add("The Hermit");
        tarotDeck.add("Wheel of Fortune");
        tarotDeck.add("Justice");
        tarotDeck.add("The Hanged Man");
        tarotDeck.add("Death");
        tarotDeck.add("Temperance");
        tarotDeck.add("The Devil");
        tarotDeck.add("The Tower");
        tarotDeck.add("The Star");
        tarotDeck.add("The Moon");
        tarotDeck.add("The Sun");
        tarotDeck.add("Judgement");
        tarotDeck.add("The World");
        
        random = new Random();
    }
    
    private static void shuffleDeck() {
        Collections.shuffle(tarotDeck);
    }
    
    private static void drawCard() {
        String card = tarotDeck.get(random.nextInt(tarotDeck.size()));
        System.out.println("Your card is: " + card);
        tarotDeck.remove(card);
        
        if (tarotDeck.isEmpty()) {
            System.out.println("The deck is empty, shuffling again...");
            initializeDeck();
            shuffleDeck();
        }
    }
}

