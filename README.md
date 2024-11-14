# foodie-cli
The purpose of this document is to provide a detailed specification for a command-line interface (CLI) application like Zomato. The application will allow customers to choose restaurants, browse dishes, and place orders.
Software Requirements Specification (SRS)
FoodieCLI Application
1. Introduction
   1.1 Purpose
   The purpose of this document is to provide a detailed specification for a command-line interface (CLI) application like Zomato. The application will allow customers to choose restaurants, browse dishes, and place orders.
   1.2 Scope
   This application will support:
   Customer registration and login
   Viewing available restaurants
   Browsing dishes from selected restaurants
   Placing orders for dishes
2. System Overview
   The system will be a simple CLI-based Java application. It will include various classes to represent Customers, Restaurants, Dishes, and Orders.
3. Functional Requirements
   3.1 Customer Operations
   Register a new customer
   Login for existing customers
   Browse restaurants
   View dishes in a selected restaurant
   Place an order
   3.2 Restaurant Operations
   Add new restaurants (admin functionality)
   List all restaurants
   3.3 Order Operations
   Place a new order
   View order history (for customers)
4. Classes and Attributes
   4.1 Customer
   public class Customer {
   private String id;
   private String name;
   private String email;
   private String password;
   private List<Order> orderHistory;

   // Constructors, getters, and setters
   }
   4.2 Restaurant
   public class Restaurant {
   private String id;
   private String name;
   private String address;
   private List<Dish> menu;

   // Constructors, getters, and setters
   }
   4.3 Dish
   public class Dish {
   private String id;
   private String name;
   private String description;
   private double price;

   // Constructors, getters, and setters
   }
   4.4 Order
   public class Order {
   private String id;
   private Customer customer;
   private Restaurant restaurant;
   private List<Dish> dishes;
   private double totalPrice;
   private Date orderDate;

   // Constructors, getters, and setters
   }
5. Operations
   5.1 Customer Operations
   public class CustomerService {
   public void registerCustomer(String name, String email, String password);
   public Customer login(String email, String password);
   public void browseRestaurants();
   public void viewDishes(String restaurantId);
   public void placeOrder(String customerId, String restaurantId, List<String> dishIds);
   }
   5.2 Restaurant Operations
   public class RestaurantService {
   public void addRestaurant(String name, String address);
   public List<Restaurant> listRestaurants();
   }
   5.3 Order Operations
   public class OrderService {
   public void placeOrder(Customer customer, Restaurant restaurant, List<Dish> dishes);
   public List<Order> getOrderHistory(Customer customer);
   }
6. Associations
   6.1 Customer and Order
   A Customer can have multiple Orders (1 to many relationship).
   6.2 Restaurant and Dish
   A Restaurant can have multiple Dishes (1 to many relationship).
   6.3 Order, Customer, and Restaurant
   An Order is associated with one Customer and one Restaurant.
7. Visibility Levels
   All properties in classes will be private.
   Service methods will be public to allow interaction with the CLI.
   Getters and setters will be used for accessing and modifying private fields.
8. Basic Operations
   8.1 Register a New Customer
   Input: Customer name, email, and password.
   Processing: Create a new Customer object and store it.
   Output: Confirmation message.
   8.2 Customer Login
   Input: Customer email and password.
   Processing: Validate credentials and return Customer object if valid.
   Output: Success or failure message.
   8.3 Browse Restaurants
   Input: None.
   Processing: Retrieve list of all Restaurant objects.
   Output: Display restaurant names and addresses.
   8.4 View Dishes in a Restaurant
   Input: Restaurant ID.
   Processing: Retrieve list of Dish objects for the specified Restaurant.
   Output: Display dish names, descriptions, and prices.
   8.5 Place an Order
   Input: Customer ID, Restaurant ID, and list of Dish IDs.
   Processing: Create a new Order object, calculate the total price, and store the order.
   Output: Order confirmation and total price.
9. Non-Functional Requirements
   Performance: The system should handle concurrent access efficiently.
   Usability: The CLI should be user-friendly and provide clear instructions.
   Security: Passwords should be stored securely, and user data should be protected.


