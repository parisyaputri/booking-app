## Screenshot of result
![image](https://github.com/user-attachments/assets/8e003f88-701f-44aa-9e61-6b65689b86f8)

## Explanation of codes
  ### main.go
  - Constant and variables
    - `conferenceTickets` holds the total number of the tickets
    - `conferenceName` holds the name of the conference
    - `remainingTickets` holds the number of tickets available
    - `bookings` stores all bookings represented by UserData
  - Struct Definition
    - Represents booking with user's data, and `wg` used to manage concurrency for sending tickets
- main function
  - `getUserInput` tells user to enter their data
  - `validateUserInput` checks if input is valid
  - If inputs are valid, `bookTicket` reserves the ticket
  - Error message if inputs are invalid
  - `wg.Wait()` blocks the program from exiting until background tasks are complete
- greetUsers Function
  - Displays welcome message, conference name, total tickets, remaining tickets
- getFirstNames function
  - Loops through the bookings slice, extracts each first name, and returns a slice of first names
- getUserInput function
  - Prompts user to input their personal data, each input captured using `fmt.Scan`
- bookTicket Function
  - Decreases `remainingTickets` by the number user have inputted
  - Creates `UserData` struct for new booking
  - Display thank you message and updates the number of remaining tickets
- sendTicket function
  - Simulates a delay in ticket sending by pausing for 50 seconds, then "sends" a ticket message to the specified email. It calls `wg.Done()` when complete to signal that the goroutine is finished.
### help.go
- validateUserInput function
  - Parameters
    - `firstName`    : The first name of the user.
    - `lastName`     : The last name of the user.
    - `email`        : The user's email address.
    - `userTickets`  : The number of tickets the user wants to book.
  - Function Logic
    - `isValidName`          : checks that both first and last name have at least 2 characters
    - `isValidEmail`         : checks if email contains `@`
    - `isValidTicketNumber`  : checks if number ticket requested is positive numbers and is not greater than the `remainingTickets`
  



