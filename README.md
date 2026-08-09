# Sports Event Management System

events = []

def add_event():
    name = input("Enter sports event name: ")
    sport = input("Enter sport name: ")
    date = input("Enter event date: ")
    venue = input("Enter venue: ")

    event = {
        "name": name,
        "sport": sport,
        "date": date,
        "venue": venue
    }

    events.append(event)
    print("Event added successfully!")


def view_events():
    if not events:
        print("No events available.")
        return

    print("\n--- Sports Events ---")
    for i, event in enumerate(events, 1):
        print(f"\nEvent {i}")
        print("Event Name :", event["name"])
        print("Sport      :", event["sport"])
        print("Date       :", event["date"])
        print("Venue      :", event["venue"])


def delete_event():
    if not events:
        print("No events available.")
        return

    view_events()

    try:
        number = int(input("\nEnter event number to delete: "))

        if 1 <= number <= len(events):
            events.pop(number - 1)
            print("Event deleted successfully!")
        else:
            print("Invalid event number.")

    except ValueError:
        print("Please enter a valid number.")


while True:
    print("\n===== Sports Event Management System =====")
    print("1. Add Sports Event")
    print("2. View Sports Events")
    print("3. Delete Sports Event")
    print("4. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        add_event()
    elif choice == "2":
        view_events()
    elif choice == "3":
        delete_event()
    elif choice == "4":
        print("Thank you!")
        break
    else:
        print("Invalid choice. Please try again.")
