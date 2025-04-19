# Bag.Java
Java Source Code 

import java.util.ArrayList
import java.util.List;

/**
 * A generic Bag class implementing the bag data structure.
 * @param <T> the type of elements stored in the bag
 */
public class Bag<T> {
    private List<T> items; // List to store bag elements

    /**
     * Constructor to initialize the bag.
     */
    public Bag() {
        this.items = new ArrayList<>();
    }

    /**
     * Adds an item to the bag.
     * @param item the item to add
     */
    public void add(T item) {
        items.add(item);
    }

    /**
     * Removes one occurrence of the specified item from the bag, if it exists.
     * @param item the item to remove
     */
    public void remove(T item) {
        items.remove(item); // removes first occurrence if exists
    }

    /**
     * Checks if the bag contains the specified item.
     * @param item the item to check
     * @return true if item exists, false otherwise
     */
    public boolean contains(T item) {
        return items.contains(item);
    }

    /**
     * Counts the number of occurrences of the specified item in the bag.
     * @param item the item to count
     * @return the count of the item
     */
    public int count(T item) {
        int count = 0;
        for (T element : items) {
            if (element.equals(item)) {
                count++;
            }
        }
        return count;
    }

    /**
     * Returns a string representation of the bag's contents.
     * @return string of all items
     */
    @Override
    public String toString() {
        return items.toString();
    }

    /**
     * Main method to demonstrate the Bag class functionality.
     */
    public static void main(String[] args) {
        // Create an instance of Bag for String elements
        Bag<String> bag = new Bag<>();

        // Add elements to the bag, including duplicates
        bag.add("apple");
        bag.add("banana");
        bag.add("apple");
        bag.add("orange");
        bag.add("banana");
        bag.add("kiwi");

        // Print the bag contents
        System.out.println("Bag contents: " + bag);

        // Test the contains method
        System.out.println("Contains 'apple'? " + bag.contains("apple")); // true
        System.out.println("Contains 'grape'? " + bag.contains("grape")); // false

        // Test the count method
        System.out.println("Count of 'apple': " + bag.count("apple")); // 2
        System.out.println("Count of 'banana': " + bag.count("banana")); // 2
        System.out.println("Count of 'kiwi': " + bag.count("kiwi")); // 1

        // Remove an element
        System.out.println("Removing 'banana'...");
        bag.remove("banana");

        // Print the bag contents again
        System.out.println("Bag contents after removal: " + bag);

        // Test contains and count for removed element
        System.out.println("Contains 'banana'? " + bag.contains("banana")); // true or false?
        System.out.println("Count of 'banana': " + bag.count("banana")); // 1

        // Remove 'banana' again
        System.out.println("Removing 'banana' again...");
        bag.remove("banana");
        System.out.println("Bag contents after second removal: " + bag);
        System.out.println("Contains 'banana'? " + bag.contains("banana")); // false
        System.out.println("Count of 'banana': " + bag.count("banana")); // 0
    }
}
