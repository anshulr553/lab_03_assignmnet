# lab_03_assignmnet
...
#e22cseu1120

# Define a class for Flight
class Flight:
    # Initialize the attributes of the flight
    def __init__(self, id, origin, destination, price):
        self.id = id
        self.origin = origin
        self.destination = destination
        self.price = price

    # Define a method to display the flight details
    def display(self):
        print(f"Flight ID: {self.id}")
        print(f"From: {self.origin}")
        print(f"To: {self.destination}")
        print(f"Price: {self.price}")

# Create a list of flights using the given data
flights = [
    Flight("AI161E90", "BLR", "BOM", 5600),
    Flight("BR161F91", "BOM", "BBI", 6750),
    Flight("AI161F99", "BBI", "BLR", 8210),
    Flight("VS171E20", "JLR", "BBI", 5500),
    Flight("AS171G30", "HYD", "JLR", 4400),
    Flight("AI131F49", "HYD", "BOM", 3499)
]

# Define a function to search and print the flights based on the user's choice
def search_flights(choice):
    # If the user chooses to search flights for a particular city
    if choice == 1:
        # Ask the user to enter the city name
        city = input("Enter the city name: ")
        # Initialize a flag to indicate if any flight is found
        found = False
        # Loop through the flights list
        for flight in flights:
            # If the flight's origin or destination matches the city name
            if flight.origin == city or flight.destination == city:
                # Display the flight details
                flight.display()
                # Set the flag to True
                found = True
                # Print a blank line for readability
                print()
        # If no flight is found, print a message
        if not found:
            print(f"No flights found for {city}.")

    # If the user chooses to search flights from a city
    elif choice == 2:
        # Ask the user to enter the origin city name
        origin = input("Enter the origin city name: ")
        # Initialize a flag to indicate if any flight is found
        found = False
        # Loop through the flights list
        for flight in flights:
            # If the flight's origin matches the origin city name
            if flight.origin == origin:
                # Display the flight details
                flight.display()
                # Set the flag to True
                found = True
                # Print a blank line for readability
                print()
        # If no flight is found, print a message
        if not found:
            print(f"No flights found from {origin}.")

    # If the user chooses to search flights between two given cities
    elif choice == 3:
        # Ask the user to enter the origin and destination city names
        origin = input("Enter the origin city name: ")
        destination = input("Enter the destination city name: ")
        # Initialize a flag to indicate if any flight is found
        found = False
        # Loop through the flights list
        for flight in flights:
            # If the flight's origin and destination match the given cities
            if flight.origin == origin and flight.destination == destination:
                # Display the flight details
                flight.display()
                # Set the flag to True
                found = True
                # Print a blank line for readability
                print()
        # If no flight is found, print a message
        if not found:
            print(f"No flights found between {origin} and {destination}.")

    # If the user enters an invalid choice, print a message and ask again
    else:
        print("Invalid choice. Please enter 1, 2 or 3.")
        search_flights(int(input("Enter your choice: ")))


# Ask the user to choose the search parameter from the given options
print("Choose the search parameter:")
print("[1. Flights for a particular City]")
print("[2. Flights From a city]")
print("[3. Flights between two given cities]")
choice = int(input("Enter your choice: "))

# Call the search_flights function with the user's choice as an argument
search_flights(choice)
