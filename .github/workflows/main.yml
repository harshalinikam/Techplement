import json

def load_contacts():
    try:
        with open('contacts.json', 'r') as file:
            return json.load(file)
    except FileNotFoundError:
        return {}

def save_contacts(contacts):
    with open('contacts.json', 'w') as file:
        json.dump(contacts, file)

def add_contact(contacts):
    name = input("Enter the name of the contact: ").strip()
    if not name:
        print("Name cannot be empty.")
        return

    if name in contacts:
        print("Contact already exists.")
        return

    phone = input("Enter the phone number: ").strip()
    email = input("Enter the email address: ").strip()
    contacts[name] = {'phone': phone, 'email': email}
    save_contacts(contacts)
    print("Contact added successfully.")

def search_contact(contacts):
    name = input("Enter the name of the contact to search: ").strip()
    contact = contacts.get(name)
    if contact:
        print(f"Name: {name}\nPhone: {contact['phone']}\nEmail: {contact['email']}")
    else:
        print("Contact not found.")

def update_contact(contacts):
    name = input("Enter the name of the contact to update: ").strip()
    if name not in contacts:
        print("Contact not found.")
        return

    print("Current Contact Information:")
    print(f"Name: {name}\nPhone: {contacts[name]['phone']}\nEmail: {contacts[name]['email']}")
    new_phone = input("Enter the new phone number (press enter to keep it unchanged): ").strip()
    new_email = input("Enter the new email address (press enter to keep it unchanged): ").strip()
    if new_phone:
        contacts[name]['phone'] = new_phone
    if new_email:
        contacts[name]['email'] = new_email
    save_contacts(contacts)
    print("Contact updated successfully.")

def display_menu():
    print("\n1. Add Contact")
    print("2. Search Contact")
    print("3. Update Contact")
    print("4. Exit")

def main():
    contacts = load_contacts()
    while True:
        display_menu()
        choice = input("Enter your choice: ").strip()
        if choice == '1':
            add_contact(contacts)
        elif choice == '2':
            search_contact(contacts)
        elif choice == '3':
            update_contact(contacts)
        elif choice == '4':
            print("Exiting...")
            break
        else:
            print("Invalid choice.")

if __name__ == "__main__":
    main()
