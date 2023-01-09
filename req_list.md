## Objects

User {  
id: string, // use uuidv4 to generate  
firstName: string,  
lastName: string,  
screenName: string,  
email: string,  
carpoolsOwned: [string], // this is a set of unique keys  
carpoolsJoined: [string], // this is a set of unique keys  
paymentMethods: [Payment],  
}

Payment {  
userID: string,  
default: boolean,  
name: string, // optional name the user can give to payment method  
creditCard: boolean,  
nameOnCard: string,  
cardNumber: number,  
expiration: number, // something like YYMM  
}

Carpools -> [Carpool]

Carpool {  
id: string, // use uuidv4 to generate  
owner: string, // screenName of the User  
members: [string], // screenName of each member  
attendance: [Attendance],  
dateLastPayment: Date,  
paymentHistory: [PaymentRecord],  
}

Attendance {  
user: string, // userID  
count: number, // number of days attended since last payout  
days: [Date],  
}

## Functions

- factory function to generate Users
  - helper functions:
    - update user data
    - create new carpool (Links to the actual function below)
    - edit an owned carpool
    - leave joined carpool
    - view current accrued costs
    - input attendance
    - edit attendance
    - send/generate bill
    - input costs (gas, upkeep)(specific to each carpool)
- function to display stats
  - helper functions:
    - sort data
    - filter data
- function to create new carpool
- function to search for carpools
  - helper functions:
    - sort carpools
    - filter carpools
- function to handle authentication (logging in/out)
