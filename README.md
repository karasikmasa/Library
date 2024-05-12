# Library
class Book:
    def __init__(self, title, author, year, isbn):
        self.title = title
        self.author = author
        self.year = year
        self.isbn = isbn

class Library:
    def __init__(self):
        self.books = []

    def add_book(self, book):
        self.books.append(book)
        print("Book added successfully!")

    def remove_book(self, isbn):
        self.books = [book for book in self.books if book.isbn != isbn]
        print("Book removed successfully!")

    def display_books(self):
        if not self.books:
            print("No books in the library.")
        else:
            print("Books in the library:")
            for book in self.books:
                print(f"Title: {book.title}, Author: {book.author}, Year: {book.year}, ISBN: {book.isbn}")

def main():
    library = Library()

    while True:
        print("\nMenu:")
        print("1. Add book")
        print("2. Remove book")
        print("3. Display books")
        print("4. Quit")

        choice = input("Enter your choice: ")

        if choice == '1':
            title = input("Enter book title: ")
            author = input("Enter book author: ")
            year = input("Enter book publication year: ")
            isbn = input("Enter book ISBN: ")
            book = Book(title, author, year, isbn)
            library.add_book(book)

        elif choice == '2':
            isbn = input("Enter book ISBN to remove: ")
            library.remove_book(isbn)

        elif choice == '3':
            library.display_books()

        elif choice == '4':
            print("Exiting program...")
            break

        else:
            print("Invalid choice, please try again.")

if __name__ == "__main__":
    main()
