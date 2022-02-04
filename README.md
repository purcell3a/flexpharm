# flexpharm
Hackathon Project with Clovyr and Chia

## Objective

- This project is designed to help individuals purchase necessary prescriptions at bulk price from manufacturers, allowing them to avoid unsupported mark-up in the pharmaceutical industry. (Think insulin, inhalers etc. )

## How does it work

### Recievers
    - recievers are modeled after the "piggybank example", recievers set up a piggy bank and when that bank has met a certain monetary amount the prescriptions are filled & shipped to the address of each coin in the piggy bank

### User
    - users put in a request for a prescription which contains:
        - personal address or pharmacy for pickup
        - wallet for payment
        - doctors contact
            - if the doctor/office is already in the system they'll recieve a notification to confirm the prescription
            - if they are not in the system if will initiate an automated process for verifying the practice and retrieving permission

### SmartCoin

    some iteration will be needed here but MVP 

    1. coin verifies user is user 
    2. coin verifies user has prescription from listed doctor
    3. upon verification of all info coin will be "spent" on best fit piggybank in the system. See PiggyBank system heirarchy for detail 
    4. once that piggybank fills up, the coin will release the user information from each parent coin into the recievers system for prescription distribution

## Target User Base

 Users are broken up into two categories (spenders & recievers)

### spenders 
    - any individual with a a prescription

    - doctors & doctors offices (those who prescribe)

### receivers

    - Governments 
        - Implement this on a state level and take a small cut to fund medicare

    - DAO's or other organizations 
        - organize it and take a small cut, (capped at x percent)
        - think private orgs funding more experimental medication or procedures 

    - manufacturing fascilities &/or distribution centers
        - Implement this for a direct-to-consumer model

### PiggyBank System Heirarchy

    - anyone(qualifying) can create a piggy bank although targeted recievers listed above 
    
    - piggybanks have hierarchy in order as such:
        1. lowest price accepted for prescription
        2. closest bank to being full 

    The piggy bank hierarchy motivates recievers to compete in accepted price for the order in order to GET that order/buisness/whatever
