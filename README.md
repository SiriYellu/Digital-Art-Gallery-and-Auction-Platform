# Digital-Art-Gallery-and-Auction-Platform
Primary Objective: The objective of our project is to develop a Digital Art  Gallery and Auction Platform that manages digital artwork inventory, bids,  auctions, transactions, and user information.
[Digital_Art_Gallery_Database_Documentation.md](https://github.com/user-attachments/files/25025719/Digital_Art_Gallery_Database_Documentation.md)
# Database Systems
## Digital Art Gallery and Auction Platform

**Authors:**
- Andrew Bala Abhilash Polisetty (001138913)
- Siri Yellu (001165833)
- Keerthana Mandava (001138885)
- Baby Naga Venkata Uttara Mekala (001142228)

---

## Executive Overview

The objective of this project is to develop a Digital Art Gallery and Auction Platform that manages digital artwork inventory, bids, auctions, transactions, and user information.

## Relational Schema

- Users (UserID [PK], Name, Email, WalletAddress, UserType)
- Artwork (ArtworkID [PK], Title, ArtistID [FK], Medium, Price, NFTTokenID, AuctionStatus)
- Auction (AuctionID [PK], ArtworkID [FK], StartDate, EndDate, ReservePrice, CurrentHighestBid)
- Bid (BidID [PK], AuctionID [FK], UserID [FK], BidAmount, BidTime)
- Transactions (TransactionID [PK], UserID [FK], ArtworkID [FK], PaymentMethod, AmountPaid, TransactionDate)
- <img width="908" height="634" alt="image" src="https://github.com/user-attachments/assets/f7434228-79d9-48e3-925a-0920e55fcb03" />
<img width="902" height="894" alt="image" src="https://github.com/user-attachments/assets/b80a08d5-9bdd-4b4c-85c5-a61e7530f313" />
<img width="883" height="521" alt="image" src="https://github.com/user-attachments/assets/271bf853-f9ec-4ab2-abb1-7b7895ff2d5b" />


