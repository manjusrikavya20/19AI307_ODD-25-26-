# Ex.No:4(D) DESIGN PATTERN  ---- BEHAVIOUR PATTERN

## QUESTION:
Design a program where a Product model stores item info, and the view displays it. Implement a controller to update product price and refresh the view automatically.



## **Aim**

To design a program using the MVC (Model–View–Controller) pattern where a Product model stores item information, the View displays the product details, and the Controller updates the product price and automatically refreshes the View.

## **Algorithm**

1. Start the program.
2. Create a **Product Model** class with fields such as name, id, and price.
3. Implement getter and setter methods in the Product model.
4. Create a **View** class responsible for displaying product details.
5. Implement a method in the View (e.g., `displayProduct()`) to show the product’s current data.
6. Create a **Controller** class that holds references to both the Product model and the View.
7. Add a method in the Controller to update the product price.
8. Inside this method, update the model’s price using its setter.
9. After updating the model, immediately call the View’s display method to refresh the output.
10. In the main program, create objects for the model, view, and controller.
11. Display initial product details.
12. Use the controller to change the price and automatically refresh the view.
13. End the program.





## PROGRAM:
 ```
/*
Program to implement a Behaviour Pattern using Java
Developed by: MANJUSRI KAVYA R
RegisterNumber: 212224040186
*/
```

## SOURCE CODE:
```
import java.util.Scanner;

class Product {
    private String name;
    private double price;
    private String code;

    public Product(String name, double price, String code) {
        this.name = name;
        this.price = price;
        this.code = code;
    }

    public String getName() { return name; }
    public double getPrice() { return price; }
    public String getCode() { return code; }
    public void setPrice(double price) { this.price = price; }
}

class ProductView {
    private Scanner sc;

    public ProductView(Scanner sc) {
        this.sc = sc;
    }

    public void displayProductDetails(Product product) {
        System.out.println("--- Product Details ---");
        System.out.println("Name : " + product.getName());
        System.out.println("Price: " + product.getPrice());
        System.out.println("Code : " + product.getCode());
    }

    public double getNewPriceFromUser() {
        System.out.print("");
        return sc.nextDouble();
    }
}

class ProductController {
    private Product model;
    private ProductView view;

    public ProductController(Product model, ProductView view) {
        this.model = model;
        this.view = view;
    }

    public void updateView() {
        view.displayProductDetails(model);
    }

    public void changePrice() {
        double newPrice = view.getNewPriceFromUser();
        model.setPrice(newPrice);
        updateView();
    }
}

public class MVCUserInputDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String name = sc.nextLine();
        double price = sc.nextDouble();
        sc.nextLine(); 
        String code = sc.nextLine();

        Product model = new Product(name, price, code);
        ProductView view = new ProductView(sc);
        ProductController controller = new ProductController(model, view);

        controller.updateView();
        controller.changePrice();
    }
}

```






## OUTPUT:

<img width="680" height="332" alt="image" src="https://github.com/user-attachments/assets/1c1d8e93-3dfa-4d40-b34f-4177d4089b2a" />


## RESULT:

Thus java program executed successfully.

