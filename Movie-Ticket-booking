# Online Python compiler (interpreter) to run Python online.
# Write Python 3 code in this online editor and run it.
# Function to initialize seat matrix (5x5 for example)
def initialize_seat_matrix():
    return [['O' for _ in range(5)] for _ in range(5)]  # 'O' indicates the seat is available

# Function to display the seat matrix
def display_seat_matrix(seats):
    print("\nCurrent seat availability (O = Available, X = Booked):")
    for row in seats:
        print(' '.join(row))
    print()  # Empty line for better readability

# Function to select seats and update seat matrix
def select_seats(seats, num_tickets):
    selected_seats = []
    for _ in range(num_tickets):
        try:
            row = int(input("Enter seat row (1-5): ")) - 1
            col = int(input("Enter seat column (1-5): ")) - 1
            if seats[row][col] == 'O':
                seats[row][col] = 'X'  # Mark seat as booked
                selected_seats.append((row + 1, col + 1))  # Save seat number for confirmation
                print(f"Seat ({row + 1}, {col + 1}) successfully booked.")
                display_seat_matrix(seats)  # Show updated seat matrix after booking
            else:
                print("Seat is already booked, please select another seat.")
                continue
        except (ValueError, IndexError):
            print("Invalid input. Please select a valid seat.")
            continue
    return selected_seats

# Function to select a movie
def t_movie():
    print("Which movie do you want to watch?")
    print("1. Kalki 2898 AD")
    print("2. Devara Part 1")
    print("3. Okkadu Re-Release")
    print("4. Back")
    
    try:
        movie = int(input("Choose your movie (1-4): "))
        if movie == 4:
            center()  # Go back to theater selection
        else:
            theater()  # Proceed to theater selection
    except ValueError:
        print("Invalid input, please choose a valid option.")
        t_movie()

# Function to select a theater screen
def theater():
    print("Which screen do you want to watch the movie on?")
    print("1. SCREEN 1")
    print("2. SCREEN 2")
    print("3. SCREEN 3")
    
    try:
        screen = int(input("Choose your screen (1-3): "))
        tickets = int(input("Number of tickets you want?: "))
        timing(screen, tickets)
    except ValueError:
        print("Invalid input, please enter valid choices.")
        theater()

# Function to select movie timing and book seats
def timing(screen, num_tickets):
    time1 = {
        "1": "10:00AM - 1:00PM",
        "2": "1:10PM - 4:10PM",
        "3": "4:20PM - 7:20PM",
        "4": "7:30PM - 10:30PM"
    }
    time2 = {
        "1": "10:15AM - 1:15PM",
        "2": "1:25PM - 4:25PM",
        "3": "4:35PM - 7:35PM",
        "4": "7:45PM - 10:45PM"
    }
    time3 = {
        "1": "10:30AM - 1:30PM",
        "2": "1:40PM - 4:40PM",
        "3": "4:50PM - 7:50PM",
        "4": "8:00PM - 10:45PM"
    }

    time_options = {1: time1, 2: time2, 3: time3}

    if screen in time_options:
        print("Choose your time:")
        for k, v in time_options[screen].items():
            print(f"{k}. {v}")
        try:
            time_choice = input("Select your time (1-4): ")
            if time_choice in time_options[screen]:
                print(f"Selected time: {time_options[screen][time_choice]}")
                seats = initialize_seat_matrix()  # Initialize seat availability
                display_seat_matrix(seats)  # Show available seats
                selected_seats = select_seats(seats, num_tickets)  # Book seats
                print(f"Successfully booked seats: {selected_seats}")
                print(f"Enjoy your movie at {time_options[screen][time_choice]}!")
            else:
                print("Invalid time selection. Please try again.")
                timing(screen, num_tickets)
        except KeyError:
            print("Invalid input. Please select a valid time.")
            timing(screen, num_tickets)
    else:
        print("Invalid screen choice.")
        theater()

# Function to select a movie theater
def movie(theater_choice):
    if theater_choice in [1, 2, 3]:
        t_movie()
    elif theater_choice == 4:
        city()  # Go back to city selection
    else:
        print("Invalid choice.")
        center()

# Function to select a center/theater location
def center():
    print("Which theater do you wish to see a movie at?")
    print("1. PVR INOX")
    print("2. Asian ALLU ARJUN")
    print("3. Asian Mahesh Babu")
    print("4. Asian Ravi Teja")
    
    try:
        choice = int(input("Choose your option (1-4): "))
        movie(choice)
    except ValueError:
        print("Invalid input, please choose a valid option.")
        center()

# Function to select a city for the movie
def city():
    print("Hi, welcome to movie ticket booking!")
    print("Where do you want to watch a movie?")
    print("1. Bengaluru")
    print("2. Hyderabad")
    print("3. Chennai")
    
    try:
        place = int(input("Choose your option (1-3): "))
        if place in [1, 2, 3]:
            center()
        else:
            print("Invalid choice, please select again.")
            city()
    except ValueError:
        print("Invalid input, please enter a number.")
        city()

# Start the process by calling the city function
city()
