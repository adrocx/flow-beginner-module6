# Creating an NFT

This is a cadence contract for creating a 'custom NFT collection'.

## Description

The link to flow playground:
```
https://play.flow.com/6d8e384f-2973-41c2-b06a-e79e062865c1?type=script&id=9c7c7af3-4b30-4d56-b275-44ce6e52bb0b

```

The "contract1.cdc" file includes a custom NFT collection Cadence contract named CryptoPoops.

This contract adheres to the NFT interface standard as defined in the "contract2.cdc" file.

The "multidata.cdc" file retrieves metadata (name) for a specific NFT (identified by id) within a CryptoPoops collection held by a given account.

The "createcollection.cdc" transaction script allows an authenticated account (signer) to interact with a CryptoPoops.Collection stored in their account storage by borrowing a reference to it, enabling operations like depositing NFTs or retrieving NFT IDs.

The "collection.cdc" file retrieves the NFT IDs from all NFT collections owned by a user's address and organizes them by the type of collection, returning the result as a mapping of collection types to arrays of NFT IDs.

The "create.cdc" transaction script creates and stores a CryptoPoops.Collection in the signer's account storage, exposing only the deposit and getIDs functions to the public, and logs the success of the collection creation.

The "mint.cdc" transaction script mints a new NFT with specified metadata and deposits it into the recipient's CryptoPoops.Collection, provided that the signer has the necessary privileges and the recipient has a collection, and it logs the success of the minting process.

The "script.cdc" file etrieves and returns a reference to a specific NFT (identified by _id) from the user's public CryptoPoops.Collection if it exists, using borrowAuthNFT.

## Getting Started

Deploy the "contract2.cdc" to 0x05 account.

Then Deploy the "contract1.cdc" to 0x06 account.

Sign the first transaction (collection.cdc) with address 0x06 and send it.

Sign the second transaction (mint.cdc) with address 0x05 and send it with the below parameters:

recipient = 0x06

variables:

name: Adrocx

favouritefood: Maggi

luckynumber: 6

### Executing program

Execute the script (collection.cdc) with the following parameter

User = 0x06

The response is an array of NFT IDs of NFts minted into 0x02's CryptoPoops Collection

Pick one of these IDs and pass it as the 'index' parameter in the script.cdc script

Execute the script (accessNFT.cdc) with the following parameters:

User = 0x06

id = (as specified above)


## Authors

Aditya Raju

adrocxsmma@gmail.com


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
