# Event-organizer

The EventContract contains the following main components:

Event Struct: A structure named Event is defined to store information about an event. It includes fields for the event's organizer's address, name, date, ticket price, total ticket count, and remaining ticket count.

Mappings:
events: A mapping that associates an event ID with an Event struct, storing details about each event.
tickets: A nested mapping that tracks the number of tickets owned by each address for each event.

State Variable:
nextId: An unsigned integer that keeps track of the next available event ID.

createEvent Function:
The createEvent function allows an address to create a new event. It requires the event's name, date (in the future), price per ticket, and total ticket count. It verifies that the event's date is in the future and that the ticket count is greater than zero. The event's details are stored in the events mapping using the nextId as the event ID.
buyTicket Function:
The buyTicket function enables users to buy tickets for an event by providing the event ID and the desired quantity of tickets. It checks if the event exists and if it's still in the future. The function requires the exact amount of Ether to be sent, calculated as the ticket price multiplied by the ticket quantity. It also verifies that there are enough available tickets for purchase. If all conditions are met, the user's ticket count for the specific event is incremented, and the remaining tickets for the event are updated.
transferTicket Function:
The transferTicket function allows users to transfer tickets to other addresses. It verifies that the event exists and is in the future, and that the sender has enough tickets to transfer. If the conditions are met, the sender's ticket count for the event is decreased, and the recipient's ticket count is increased.




**Deploying in Remix IDE:**

To deploy the EventContract in Remix IDE, follow these steps:

Open the Remix IDE.
Create a new Solidity file and paste the provided code into it.
Choose the appropriate Solidity compiler version (e.g., 0.8.0) from the Remix compiler dropdown.
Ensure that the account you are using is connected to the desired Ethereum network (e.g., local development network, Rinkeby, etc.).
Click on the "Deploy & Run Transactions" tab in Remix.
Select the EventContract from the Contract dropdown.
Click the "Deploy" button to deploy the contract to the connected Ethereum network.
Confirm the transaction in your connected wallet.
Once the contract is deployed, you'll see information about the deployed contract in the "Deployed Contracts" section, including its address
