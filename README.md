# FlexPharm

Hackathon Project with Clovyr and Chia



## Objective

- This project was designed to help individuals purchase prescriptions at bulk price from manufacturers, allowing them to avoid unsupported mark-up in the pharmaceutical industry. (Think insulin, inhalers etc. )



## Issues

- I originally wanted to build this as a coin & piggybank model where states or manufacturing facilities could accept bulk orders for individuals and then distribute those orders directly to pharmacies or homes. The "recievers" would have a piggybank that releases the addresses and prescriptions in all parent coints once full. This proved not possible for scale because the only way to really hold and maintain a registry of Doctors and Users was to use a singleton. Using a singleton limits us to one transaction per block/ about one per minute which would be much too slow at scale.

- Since it seems there's no great way of building something like this on CHIA that I'm cognizant of at the moment I figured i'd alteast flesh out the idea as much as possible and submit. Maybe some one will think of something. :) 

- considering the blockchain is public and this would be a breach of privacy for the individuals there would need to be some cryptographical gymnastics with a users information. This could look like verifying information through an app that sends the orders to the recievers bank without personal identifying information and the corresponding users information to a local pharmacy where they can pick it up.  EDIT: looking into Zero-knowledge_proofs



## Definitions

 Users are broken up into two categories (spenders & recievers)


### Spenders 

 The system might be simpler if I only allow doctors to place these orders and fill out the users information for the pharmacy but for now.....
   - any individual with a prescription
   - doctors & doctors offices (those who prescribe)


### Receivers

   - Governments 
        - Implement this on a state level and take a small fee to fund medicare

   - DAO's or other organizations 
        - organize it and take a small fee, (capped at x percent)
        - think private orgs funding more experimental medication or procedures 

   - Manufacturing fascilities &/or distribution centers
        - Implement this for a direct-to-consumer model


### PiggyBank System Heirarchy

   - any legal entity that can produce and/or distribute prescriptions can create a piggy bank and compete for market share
    
   - piggybanks have hierarchy in order as such:
        1. lowest price accepted for prescription
        2. closest bank to being full 

   The piggy bank hierarchy motivates recievers to compete for lowest accepted price in order to WIN orders


## Key Components

### Recievers

- Recievers are modeled after the "piggybank example", recievers set up a piggybank and when that bank has met a certain monetary amount the prescriptions are filled & shipped to the address of each coin in the piggybank

### Spenders
- spenders put in a request for a prescription through an app that does the following:
    - verifies individuals identity and address
    - takes wallet address for payment
    - verifies the prescription through the listed prescriber
      - if the doctor/office is already in the system they'll recieve a notification to confirm the prescription
      - if they are not in the system if will initiate an automated process for verifying the practice and retrieving permission
    - once all details have been verified the app creates a coin to spend on the highest piggybank in the heirarchy
    - the app also sends the users information to their listed pharmacy for pickup 

### SmartCoin
   the coin contains two things:
   - the prescription
   - the address for the pharmacy for distribution
