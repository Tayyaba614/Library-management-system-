# Library-management-system-
class Library:
    def __init__(self):
        self.books = {}  # Dictionary to store books and their availability

    def add_book(self, book_name, quantity=1):
        if book_name in self.books:
            self.books[book_name] += quantity
        else:
            self.books[book_name] = quantity
        print(f"'{book_name}' has been added with {quantity} copies.")

    def display_books(self):
        print("\nAvailable Books:")
        for book, quantity in self.books.items():
            print(f"{book} (Copies: {quantity})")

    def issue_book(self, book_name):
        if book_name in self.books and self.books[book_name] > 0:
            self.books[book_name] -= 1
            print(f"'{book_name}' has been issued.")
        else:
            print(f"'{book_name}' is not available or out of stock.")

    def return_book(self, book_name):
        if book_name in self.books:
            self.books[book_name] += 1
            print(f"'{book_name}' has been returned.")
        else:
            print(f"'{book_name}' does not belong to this library.")

def main():
    library = Library()

    while True:
        print("\nLibrary Management System")
        print("1. Add Book")
        print("2. Display Books")
        print("3. Issue Book")
        print("4. Return Book")
        print("5. Exit")

        choice = input("Enter your choice (1-5): ")

        if choice == "1":
            book_name = input("Enter book name: ")
            quantity = int(input("Enter quantity: "))
            library.add_book(book_name, quantity)
        elif choice == "2":
            library.display_books()
        elif choice == "3":
            book_name = input("Enter book name to issue: ")
            library.issue_book(book_name)
        elif choice == "4":
            book_name = input("Enter book name to return: ")
            library.return_book(book_name)
        elif choice == "5":
            print("Exiting Library Management System. Goodbye!")
            break
        else:
            print("Invalid choice. Please try again.")

if __name__ == "__main__":
    main()
