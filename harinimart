import java.util.ArrayList;
import java.util.Scanner;

class Product {
    int id;
    String name;
    double price;
    int stock;

    Product(int id, String name, double price, int stock) {
        this.id = id;
        this.name = name;
        this.price = price;
        this.stock = stock;
    }
}

public class HariniMart {

    static Scanner sc = new Scanner(System.in);
    static ArrayList<Product> products = new ArrayList<>();

    public static void main(String[] args) {

        addProducts();

        while (true) {

            System.out.println("\n==============================");
            System.out.println("        HARINIMART");
            System.out.println("==============================");
            System.out.println("1. View Products");
            System.out.println("2. Search Product");
            System.out.println("3. Buy Product");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");

            int choice = sc.nextInt();

            switch (choice) {

                case 1:
                    viewProducts();
                    break;

                case 2:
                    searchProduct();
                    break;

                case 3:
                    buyProduct();
                    break;

                case 4:
                    System.out.println("\nThank you for using HariniMart!");
                    return;

                default:
                    System.out.println("Invalid choice!");
            }
        }
    }

    static void addProducts() {

        products.add(new Product(101, "Rice", 60, 50));
        products.add(new Product(102, "Sugar", 50, 40));
        products.add(new Product(103, "Milk", 30, 30));
        products.add(new Product(104, "Biscuit", 20, 50));
        products.add(new Product(105, "Cooking Oil", 120, 25));
        products.add(new Product(106, "Soap", 40, 35));
    }

    static void viewProducts() {

        System.out.println("\n--------- PRODUCTS ---------");

        System.out.printf("%-5s %-15s %-10s %-10s%n",
                "ID", "Name", "Price", "Stock");

        for (Product p : products) {

            System.out.printf("%-5d %-15s %-10.2f %-10d%n",
                    p.id, p.name, p.price, p.stock);
        }
    }

    static void searchProduct() {

        System.out.print("\nEnter product ID: ");
        int id = sc.nextInt();

        for (Product p : products) {

            if (p.id == id) {

                System.out.println("\nProduct Found!");
                System.out.println("ID    : " + p.id);
                System.out.println("Name  : " + p.name);
                System.out.println("Price : ₹" + p.price);
                System.out.println("Stock : " + p.stock);

                return;
            }
        }

        System.out.println("Product not found!");
    }

    static void buyProduct() {

        viewProducts();

        System.out.print("\nEnter product ID: ");
        int id = sc.nextInt();

        Product selected = null;

        for (Product p : products) {

            if (p.id == id) {
                selected = p;
                break;
            }
        }

        if (selected == null) {
            System.out.println("Product not found!");
            return;
        }

        System.out.print("Enter quantity: ");
        int quantity = sc.nextInt();

        if (quantity <= 0) {
            System.out.println("Invalid quantity!");
            return;
        }

        if (quantity > selected.stock) {
            System.out.println("Sorry! Not enough stock.");
            return;
        }

        double total = selected.price * quantity;

        selected.stock = selected.stock - quantity;

        System.out.println("\n--------- BILL ---------");
        System.out.println("Product  : " + selected.name);
        System.out.println("Quantity : " + quantity);
        System.out.println("Price    : ₹" + selected.price);
        System.out.println("Total    : ₹" + total);
        System.out.println("------------------------");
        System.out.println("Purchase successful!");
    }
}