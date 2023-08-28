// User Class


package pkg4;



class User {
    private boolean role;
    private String loginId;
    private String password;

    public User(boolean role, String loginId, String password) {
        this.role = role;
        this.loginId = loginId;
        this.password = password;
    }

    public boolean verifyUser() {
        
        return true;
    }
    public String getloginId() {
return loginId;}
    public String getpassword() {
    	return password;}
}


//Customer Class

package pkg4;

class Customer extends User {
    private String Id;
    private String address;
    private String phone;
    private String email;

    public Customer(boolean role, String loginId, String password, String Id, String address, String phone, String email) {
        super(role, loginId, password);
        this.Id = Id;
        this.address = address;
        this.phone = phone;
        this.email = email;
 
    }

    public String login() {
    	return Id;
    }
    public String register() {
    	return address;
    }
    public String updateProfile() {
    	return phone ;
  
  }  

}





//Seller Class

package pkg4;

class Seller extends User {
    private String Id;
    private String address;
    private String phone;
    private String Email;
    private int sellerRating;

    public Seller(boolean role, String loginId, String password, String Id, String address, String phone, String email, int SellerRating) {
        super(role, loginId, password);
        this.Id = Id;
        this.address = address;
        this.phone = phone;
        this.Email=email;
        this.sellerRating = sellerRating ;
    }

    public String login() {
    	return Id;
     
    }
    public String register() {
    return address;
    }
    public String updateProfile() {
        return phone;
        }
}



//Product Class

package pkg4;

import java.util.Date;

class Product  extends User {
    private String productID;
    private String productName;
    private int productCost;
    private String sellerID;
    private Date d1;
    

    public Product(boolean role, String loginId, String password, String productID, String productName ,int productCost, String sellerID) {
    	super(role, loginId, password);
    	this.productID = productID;
        this.productName = productName;
        this.productCost = productCost;
        this.sellerID = sellerID;
        this.d1 = d1;
    }

    public String addToCart() {
    	return productID;
      
    }
    public int sellProduct() {
    	return productCost;
        
    }
    public String getProductDetails() {
    	return productName;
    }
    public Date buyProduct() {
    	return d1;
        
    }
    }




//Payment Class 

package pkg4;

class Payment extends User {
    private String Id;
    private  String orderID;
    private  boolean paid;
    private int total;
    private String details;

    public Payment(boolean role, String loginId, String password, String Id, String orderID, boolean paid, int total, String details) {
        super(role, loginId, password);
        this.Id = Id;
        this.orderID = orderID;
        this.paid = paid;
        this.total = total;
        this.details = details; 
    }

    private void sendOtp() {
  
    }
    private boolean confirmTransaction() {
    	return paid;
    	
    }
    private String getPaymentDetails () {
    	return details;
    	
    }
    private void makeTransaction() {
    	
    }
    
    
    }
    


//Shopping_Cart Class

package pkg4;

import java.util.Date;

class Shopping_Cart extends User {
    
	private Date created;
    

    public Shopping_Cart(boolean role, String loginId, String password) {
        super(role, loginId, password);
        
        this.created = created;
        
    }

    public void addCartItem() {
  
    }
    public void checkOut() {
    	
    }
    public void viewCartDetails () {
    	
    }
    public void updateQuantity() {
    	
    }
    
    
    }



//Review Class

package pkg4;

class Reviews extends User {
    private String reviewID;
    private  String customerID;
    private  String reviewContent;
    private int rating;
    private String parentID;
    private String productID;

    public Reviews (boolean role, String loginId, String password, String reviewID, String customerID, String reviewContent, int rating, String productID) {
        super(role, loginId, password);
        this.reviewID = reviewID;
        this.customerID = customerID;
        this.rating = rating;
        this.parentID = parentID;
        this.productID = productID; 
    }

    public String addReview() {
    	return reviewContent;
  
    }
    public void deleteReview() {
    	
    }
    public void editReview () {
    	
    }


// Orders Class

package pkg4;
import java.util.Date;
class Orders extends User {
    private String id;
    private  String sellerID;
    private  String customerID;
    private String totalAmount;
    private Date orderDate;
    private String address;
    private Date deliveryDate;
    private String deliveryStatus;

    public Orders (boolean role, String loginId, String password, String id, String customerID, String totalAmount, String deliveryStatus) {
        super(role, loginId, password);
        this.id = id;
        this.sellerID = sellerID;
        this.customerID = customerID;
        this.totalAmount = totalAmount;
        this.orderDate = orderDate ;
        this.address = address;
        this.deliveryDate = deliveryDate;
        this.deliveryStatus = deliveryStatus;
        
    }

    public String placeOrder() {
    	return deliveryStatus;
  
    }



// Main Class

package pkg4;

import java.util.Date;

public class Main {


    public static void main(String[] args) {
        // Example usage of the classes and their methods
    	User user = new User(true, "user@123", "U123");
        Customer customer = new Customer(true, "user@123", "U123", "customer@123", "Shyamnagar", "7583938822", "customer@123.com");
        Seller seller = new Seller (true, "user@123", "U123", "seller@123", "Ichapur", "7689456723","seller@123.com", 5);
        Product product = new Product(true, "user@123", "U123","product@123","Samsung", 1000, "selller@123");
        Date d1 = new Date();
        Payment payment = new Payment(true, "user@123", "U123","product@123","order@123", true, 1000, "Samsung");
        Shopping_Cart shoppingcart = new Shopping_Cart(true, " user@123", "U123");
        Date created = new Date();
        Orders orders = new Orders (true, "user@123", "U123","orders@123", "customer@123", "Five","Delivered");
        
        System.out.println("Customer has the customer id :" + "  " +customer.login());
        System.out.println("\n"+ "Customer has register the address :" + "  " +customer.register());
        System.out.println("\n"+ "Customer has updated the phone number:" + "  " +customer.updateProfile());
        System.out.println("\n"+ " Seller has the seller id:" + "  " +seller.login());
        System.out.println("\n"+ "Shopping_Cart has been created on the Date:" + "  " + created);
        System.out.println("\n"+ "Order has been deliverd :" + "  " +orders.placeOrder());
        
        
    }
}
