# DSA-project-
sem 2 final project 


#include <stdio.h>
#include <string.h>

struct Book {
    int id;
    char title[50];
    char author[50];
};

struct Book library[100];
int count = 3; // starting with 3 books already

void loadSampleBooks() {
    library[0].id = 101;
    strcpy(library[0].title, "The Alchemist");
    strcpy(library[0].author, "Paulo Coelho");

    library[1].id = 102;
    strcpy(library[1].title, "Harry Potter");
    strcpy(library[1].author, "J.K. Rowling");

    library[2].id = 103;
    strcpy(library[2].title, "Atomic Habits");
    strcpy(library[2].author, "James Clear");
}

void addBook() {
    if (count >= 100) {
        printf("Library is full!\n");
        return;
    }
    printf("Enter Book ID: ");
    scanf("%d", &library[count].id);
    printf("Enter Title: ");
    scanf(" %[^\n]", library[count].title);
    printf("Enter Author: ");
    scanf(" %[^\n]", library[count].author);
    count++;
    printf("Book added!\n");
}

void showBooks() {
    if (count == 0) {
        printf("No books in the library.\n");
        return;
    }
    printf("\n--- Library Books ---\n");
    for (int i = 0; i < count; i++) {
        printf("ID: %d\n", library[i].id);
        printf("Title: %s\n", library[i].title);
        printf("Author: %s\n\n", library[i].author);
    }
}

int main() {
    loadSampleBooks(); // add real books before starting

    int choice;
    while (1) {
        printf("\n1. Add Book\n2. Show Books\n3. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        if (choice == 1)
            addBook();
        else if (choice == 2)
            showBooks();
        else if (choice == 3) {
            printf("Goodbye!\n");
            break;
        }
        else
            printf("Invalid choice.\n");
    }
    return 0;
}
![Screenshot (1)](https://github.com/user-attachments/assets/ea59a2da-a53f-4f37-9029-929e951af701)


