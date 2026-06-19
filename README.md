# Movie Ticket Booking System in C

A console-based Movie Ticket Booking System written in C that allows users to view movies, check seat availability, book tickets, cancel bookings, calculate billing, and generate booking receipts using file handling and arrays.

## Project Overview

This project simulates a simple cinema booking system in the console. It uses structures, arrays, seat layout management, and file handling to store movies, bookings, and seat data permanently.

## Features

- Add new movies to the system.
- Display all available movies.
- Show seat layout with availability.
- Select seats for booking.
- Check seat availability before booking.
- Book tickets with customer details.
- Cancel bookings and release seats.
- Calculate total bill with GST and convenience fee.
- Generate printable booking receipt.
- Search bookings by ID.
- Display all bookings.
- Save and load movies, bookings, and seats using files.

## Concepts Used

- Arrays for movies, seats, and bookings.
- Two-dimensional seat management for cinema layout.
- Conditional statements and loops for booking logic.
- File handling with binary save/load operations.
- Billing calculation with tax and service charges.
- Console-based input and output.

## Data Structures

### Movie
```c
typedef struct {
    int movieID;
    char movieName;
    char genre;[3]
    int duration;
    float ticketPrice;
    char language;[4]
    char rating;[5]
} Movie;
```

### Seat
```c
typedef struct {
    int seatNumber;
    char status;
    char bookedBy;
    float price;
} Seat;
```

### Booking
```c
typedef struct {
    int bookingID;
    int movieID;
    char customerName;
    char phone;[6]
    int seats;[7]
    int seatCount;
    float totalAmount;
    long bookingDate;
    char status;[7]
} Booking;
```

## Seat Layout

The system uses a 10x8 seat layout with a total of 80 seats.

- `0` = Available
- `X` = Booked

## Billing Details

The bill is calculated using:

- Ticket price multiplied by seat count.
- GST at 12%.
- Convenience fee of ₹20 per seat.

## File Handling

### Movies File
- File name: `movies.dat`
- Type: Binary file
- Used to store movie details

### Bookings File
- File name: `bookings.dat`
- Type: Binary file
- Used to store booking details

### Seats File
- File name: `seats.dat`
- Type: Binary file
- Used to store seat status and price

## Menu Options

1. Add Movie  
2. Display Movies  
3. Book Tickets  
4. Cancel Booking  
5. View All Bookings  
6. Search Booking  
7. Display Seats  
8. Exit  

## How to Compile

Use GCC to compile the program:

```bash
gcc movie_booking.c -o movie_booking.exe
```

If you are using Linux or Mac:

```bash
gcc movie_booking.c -o movie_booking
```

## How to Run

### Windows PowerShell
```powershell
.\movie_booking.exe
```

### Linux / Mac
```bash
./movie_booking
```

## Sample Test Cases

### Add Movie
- Movie ID: 1
- Name: Avengers
- Genre: Action
- Duration: 180
- Price: ₹200
- Language: English
- Rating: PG-13

### Display Movies
- Avengers - Action - ₹200
- Titanic - Drama - ₹150
- Frozen - Animation - ₹180

### Display Seats
The seat grid is shown with the screen on top and each seat marked as available or booked.

### Booking Example
- Customer Name: Rahul Kumar
- Phone: 9876543210
- Seats Selected: 5, 6, 10
- Booking Confirmed with a generated booking ID

### Cancel Booking
- Enter Booking ID
- Seats are released after cancellation

## Validation Rules

- Maximum 10 seats per booking.
- Seat number must be valid.
- Already booked seats cannot be selected.
- Booking amount is calculated automatically.
- File data must be loaded before booking.

## Limitations

- This is a console-only simulation.
- No real payment gateway is used.
- No GUI or online ticketing is included.
- No real printer integration is used.

## Requirements

- C compiler (GCC recommended)
- Standard C libraries only:
  - `stdio.h`
  - `stdlib.h`
  - `string.h`
  - `time.h`

## File Structure

```bash
MovieTicketBooking/
│
├── movie_booking.c
├── movies.dat
├── bookings.dat
├── seats.dat
├── README.md
└── Makefile
```

## Notes

- This project is designed for learning C programming, arrays, file handling, and booking logic.
- Movie, booking, and seat data are saved in binary files for persistence.
- Seat selection and billing are handled entirely in the console.

## Author

Created for educational purposes to practice C programming and data structure concepts.

## License

This project is free to use for academic and learning purposes.
