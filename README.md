# internet-ethics
i am a student and my project is on Future of E-Commerce in India .

---

## 💻 e_commerce_workflow.c
```c
// e_commerce_workflow.c
// Simulation: Future of E-Commerce in India (Internet Ethics Project)

#include <stdio.h>
#include <string.h>

// Function prototypes
void browseProducts();
void selectProduct();
void placeOrder();
void makePayment();
void processOrder();
void deliverOrder();
void feedback();

char selectedProduct[50];
int orderPlaced = 0;
int paymentDone = 0;

int main() {
    int choice;
    printf("\n=========================================\n");
    printf("   🌐 FUTURE OF E-COMMERCE IN INDIA\n");
    printf("=========================================\n");

    while (1) {
        printf("\n1. Browse Products");
        printf("\n2. Select Product");
        printf("\n3. Place Order");
        printf("\n4. Make Payment");
        printf("\n5. Process & Deliver Order");
        printf("\n6. Give Feedback");
        printf("\n7. Exit");
        printf("\n\nEnter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1: browseProducts(); break;
            case 2: selectProduct(); break;
            case 3: placeOrder(); break;
            case 4: makePayment(); break;
            case 5: processOrder(); deliverOrder(); break;
            case 6: feedback(); break;
            case 7: 
                printf("\nThank you for using our E-Commerce Simulation!\n");
                return 0;
            default: printf("Invalid choice! Please try again.\n");
        }
    }
}

// Function definitions

void browseProducts() {
    printf("\nAvailable Products:\n");
    printf("1. Smartphone\n");
    printf("2. Laptop\n");
    printf("3. Shoes\n");
    printf("4. Headphones\n");
}

void selectProduct() {
    int productChoice;
    printf("\nEnter product number to add to cart: ");
    scanf("%d", &productChoice);

    switch (productChoice) {
        case 1: strcpy(selectedProduct, "Smartphone"); break;
        case 2: strcpy(selectedProduct, "Laptop"); break;
        case 3: strcpy(selectedProduct, "Shoes"); break;
        case 4: strcpy(selectedProduct, "Headphones"); break;
        default: printf("Invalid product choice!\n"); return;
    }

    printf("%s added to cart successfully!\n", selectedProduct);
}

void placeOrder() {
    if (strlen(selectedProduct) == 0) {
        printf("\nNo product selected! Please select a product first.\n");
        return;
    }
    orderPlaced = 1;
    printf("\nOrder placed successfully for: %s\n", selectedProduct);
}

void makePayment() {
    if (!orderPlaced) {
        printf("\nPlease place your order before making payment.\n");
        return;
    }

    int method;
    printf("\nSelect Payment Method:\n1. UPI\n2. Debit/Credit Card\n3. Cash on Delivery\n");
    printf("Enter your choice: ");
    scanf("%d", &method);

    switch (method) {
        case 1: printf("Payment done via UPI.\n"); break;
        case 2: printf("Payment done via Debit/Credit Card.\n"); break;
        case 3: printf("Payment selected: Cash on Delivery.\n"); break;
        default: printf("Invalid payment option!\n"); return;
    }
    paymentDone = 1;
    printf("Transaction successful!\n");
}

void processOrder() {
    if (!paymentDone) {
        printf("\nPayment not done yet. Please complete payment first.\n");
        return;
    }
    printf("\nProcessing your order...\n");
    printf("Order shipped successfully!\n");
}

void deliverOrder() {
    printf("Product delivered to your address successfully!\n");
}

void feedback() {
    int rating;
    printf("\nRate your experience (1 to 5): ");
    scanf("%d", &rating);

    if (rating < 1 || rating > 5)
        printf("Invalid rating!\n");
    else
        printf("Thank you for your feedback! You rated %d ⭐\n", rating);
}
