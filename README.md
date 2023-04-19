# Garments-Management-System-Software
GMS is a software for managing garment manufacturing operations. It streamlines order management, inventory tracking, production planning, quality control, shipping, and invoicing in one systems software. We can say all in one and a complete solutions for Garments Industry

##here is prototype code model using c##

#include <stdio.h>

// Function prototypes
void erp();
void scm();
void ims();
void crm();

int main() {
    char choice;

    printf("Welcome to the Garments Management System Software!\n");

    do {
        printf("\nPlease select an option:\n");
        printf("E - ERP - Enterprise Resource Planning\n");
        printf("S - SCM - Supply Chain Management\n");
        printf("I - IMS - Inventory Management System\n");
        printf("C - CRM - Customer Relationship Management\n");
        printf("Q - Quit\n");
        printf("Choice: ");
        scanf(" %c", &choice);

        switch (choice) {
            case 'E':
            case 'e':
                erp();
                break;

            case 'S':
            case 's':
                scm();
                break;

            case 'I':
            case 'i':
                ims();
                break;

            case 'C':
            case 'c':
                crm();
                break;

            case 'Q':
            case 'q':

                printf("Exiting Global Management System...\n");
                break;

            default:
                printf("Invalid choice. Please try again.\n");
        }
    } while (choice != 'Q' && choice != 'q');

    return 0;
}

// ERP function
void erp() {
    printf("\nExecuting ERP - Enterprise Resource Planning\n");

    float balance, expense, income;
    char choice;

    balance = 0;

    printf("\n\nERP Function\n\n");

    do {
        printf("\n\nEnter 'I' for income, 'E' for expense, or 'Q' to quit: ");
        scanf(" %c", &choice);

        switch (choice) {
            case 'I':
                printf("\nEnter income amount: ");
                scanf("%f", &income);
                balance += income;
                printf("\nCurrent balance: %.2f", balance);
                break;

            case 'E':
                printf("\nEnter expense amount: ");
                scanf("%f", &expense);
                balance -= expense;
                printf("\nCurrent balance: %.2f", balance);
                break;

            case 'Q':
                printf("\n\nThank you for using ERP Function!");
                break;

            default:
                printf("\n\nInvalid input. Please try again.");
        }

    } while (choice != 'Q');
}

// SCM function
void scm() {
    printf("\nExecuting SCM - Supply Chain Management\n");

    int order_quantity, reorder_point, stock_on_hand;
    char choice;

    printf("\n\nSCM Function\n\n");

    do {
        printf("\n\nEnter 'O' for order, 'S' for stock level, or 'Q' to quit: ");
        scanf(" %c", &choice);

        switch (choice) {
            case 'O':
                printf("\nEnter order quantity: ");
                scanf("%d", &order_quantity);
                printf("\nOrder placed for %d units.", order_quantity);
                break;

            case 'S':
                printf("\nEnter reorder point: ");
                scanf("%d", &reorder_point);
                printf("\nEnter stock on hand: ");
                scanf("%d", &stock_on_hand);
                if (stock_on_hand < reorder_point) {
                    printf("\nOrder needed.");
                } else {
                    printf("\nNo order needed.");
                }
                break;

            case 'Q':
                printf("\n\nThank you for using SCM Function!");
                break;

            default:
                printf("\n\nInvalid input. Please try again.");
        }

    } while (choice != 'Q');
}

// IMS function
void ims() {
    printf("\nExecuting IMS - Inventory Management System\n");

    int customer_id, order_id, quantity;
    char choice;

    printf("\n\nIMS Function\n\n");

    do {
        printf("\n\nEnter 'C' for customer lookup, 'O' for order placement, or 'Q' to quit: ");
        scanf(" %c", &choice);

        switch (choice) {
            case 'C':
                printf("\nEnter customer ID: ");
                scanf("%d", &customer_id);
                printf("\nCustomer %d found in database.", customer_id);
                break;

            case 'O':
                printf("\nEnter order ID: ");
                scanf("%d", &order_id);
                printf("\nEnter quantity: ");
                scanf("%d", &quantity);
                printf("\nOrder placed for %d units.", quantity);
                break;

            case 'Q':
                printf("\n\nThank you for using IMS Function!");
                break;

            default:
                printf("\n\nInvalid input. Please try again.");
        }

    } while (choice != 'Q');
}

   // CRM function
void crm() {
    printf("\nExecuting CRM - Customer Relationship Management\n");

    int customer_id, choice;
    float balance, payment;
    char name[50], address[100];

    printf("\n\nCRM Function\n\n");

    do {
        printf("\n\nEnter 'A' for add customer, 'P' for payment, 'Q' to quit: ");
        scanf(" %c", &choice);

        switch (choice) {
            case 'A':
                printf("\nEnter customer ID: ");
                scanf("%d", &customer_id);
                printf("\nEnter customer name: ");
                scanf("%s", name);
                printf("\nEnter customer address: ");
                scanf("%s", address);
                printf("\nCustomer added successfully!");
                break;

            case 'P':
                printf("\nEnter customer ID: ");
                scanf("%d", &customer_id);
                printf("\nEnter payment amount: ");
                scanf("%f", &payment);
                printf("\nPayment of %.2f received from customer %d.", payment, customer_id);
                break;

            case 'Q':
                printf("\n\nThank you for using CRM Function!");
                break;

            default:
                printf("\n\nInvalid input. Please try again.");
        }

    } while (choice != 'Q');
}
