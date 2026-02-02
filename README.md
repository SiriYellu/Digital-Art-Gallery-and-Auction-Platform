# Digital-Art-Gallery-and-Auction-Platform
Primary Objective: The objective of our project is to develop a Digital Art  Gallery and Auction Platform that manages digital artwork inventory, bids,  auctions, transactions, and user information.
[Digital_Art_Gallery_Database_Documentation.md](https://github.com/user-attachments/files/25025719/Digital_Art_Gallery_Database_Documentation.md)
# Database Systems
## Digital Art Gallery and Auction Platform

## Table of Contents
- Executive Overview
- ER Diagram
- Relational Schema
- Data Dictionary
- CRUD Matrix
- Table Descriptions
- Database Tables
- Design Tables
- Forms
- Queries
- References and Citations


## Executive Overview

### Primary Objective
The objective of this project is to develop a **Digital Art Gallery and Auction Platform** that manages digital artwork inventory, bids, auctions, transactions, and user information. The system allows artists to easily upload artwork, buyers to place bids in auctions, administrators to manage transactions, and users. This system provides an efficient way to manage artwork, track bids, and process sales.

### Client
Digital Art Gallery and Auction Platform

### Overview
An ER Diagram is drawn using IE Crow’s Foot notation, defining the relationships between entities such as Transactions, Auctions, Users, Bids, and Artwork. The relational schema is implemented using MS Access, ensuring primary and foreign keys are present to maintain data consistency. Records support CRUD operations, allowing users to create, read, update, and delete records within each table.

These features enable efficient digital art and auction management, provide real-time reports on artwork, auctions, and transactions, enhance customer experience, and support the growth of the digital art marketplace.


---


## Relational Schema

- Users (UserID [PK], Name, Email, WalletAddress, UserType)
- Artwork (ArtworkID [PK], Title, ArtistID [FK], Medium, Price, NFTTokenID, AuctionStatus)
- Auction (AuctionID [PK], ArtworkID [FK], StartDate, EndDate, ReservePrice, CurrentHighestBid)
- Bid (BidID [PK], AuctionID [FK], UserID [FK], BidAmount, BidTime)
- Transactions (TransactionID [PK], UserID [FK], ArtworkID [FK], PaymentMethod, AmountPaid, TransactionDate)
- <img width="908" height="634" alt="image" src="https://github.com/user-attachments/assets/f7434228-79d9-48e3-925a-0920e55fcb03" />

Primary Keys (PK) and Foreign Keys (FK) are used to ensure referential integrity between tables.

---
## Data Dictionary
The data dictionary defines attributes, data types, nullability, uniqueness, and key constraints for all tables in the database.
<img width="902" height="894" alt="image" src="https://github.com/user-attachments/assets/b80a08d5-9bdd-4b4c-85c5-a61e7530f313" />
---

## CRUD Matrix
CRUD operations (Create, Read, Update, Delete) are supported across the following entities:
- Users
- Artwork
- Auction
- Bid
- Transactions
<img width="883" height="521" alt="image" src="https://github.com/user-attachments/assets/271bf853-f9ec-4ab2-abb1-7b7895ff2d5b" />
---
## Table Descriptions

### Users Table
Contains 10 records including artists, buyers, and administrators. Attributes include Name, Email, WalletAddress, and UserType.

### Artwork Table
Contains 10 digital artwork entries. Each ArtworkID is unique and includes attributes such as Title, ArtistID, Medium, Price, NFTTokenID, and AuctionStatus.

### Auction Table
Contains 10 auction entries, each associated with a specific artwork. Attributes include StartDate, EndDate, ReservePrice, and CurrentHighestBid.

### Bid Table
Links AuctionID and UserID with BidAmount and BidTime. Contains 10 bid records placed by users.

### Transactions Table
Contains 10 transaction records for completed artwork sales. Each transaction includes TransactionID, UserID (buyer), ArtworkID, PaymentMethod, AmountPaid, and TransactionDate.

---

## Database Tables
- Artwork Datasheet
- Auction Datasheet
- Bid Datasheet
- Transactions Datasheet
- Users Datasheet

---

## Design Tables
- Artwork Table
- Auction Table
- Bid Table
- Transaction Table
- Users Table

---

## Forms
Forms are created for:
- Artwork
- Auction
- Bid
- Transactions
- Users

  
These forms support data entry and record management.

---

## Queries

```sql
SELECT Auction.AuctionID, Artwork.ArtworkID, Artwork.Title,
       Auction.StartDate, Auction.EndDate, Auction.CurrentHighestBid
FROM Artwork
INNER JOIN Auction
ON Artwork.ArtworkID = Auction.ArtworkID;
SELECT Transactions.TransactionID,
       Transactions.UserID,
       Artwork.ArtworkID,
       Transactions.AmountPaid,
       Transactions.TransactionDate
FROM Artwork
INNER JOIN Transactions
ON Artwork.ArtworkID = Transactions.ArtworkID;
SELECT Bid.BidID, Bid.AuctionID, Bid.BidAmount,
       Bid.BidTime, Bid.UserID, Auction.ArtworkID
FROM Auction
INNER JOIN (Users INNER JOIN Bid
ON Users.UserID = Bid.UserID)
ON Auction.AuctionID = Bid.AuctionID;
