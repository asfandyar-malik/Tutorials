### **👋 Solidity **

Highly influenced by C++, Python, Javascript  and focuses on EVM (Ethereum virtual Machine)

Ethereum is a decentralized ie. blockchain platform that runs smart contracts

EVM converts Smart contracts into Bytecode. It is runtime environment for Ethereum. 

Smart contracts just provide credible transactions without third parties interferece. 

```
pragma solidity >=0.4.0 <0.6.0;

contract SimpleStorage {
   uint storedData;

   function set(uint x) public {
      storedData = x;
   }

   function get() public view returns (uint) {
      return storedData;
   }
}
```

A **Solidity contract** is a collection of code (its functions) and data (its state) that resides at a specific address on the Ethereumblockchain.


**Address** holds the 20 byte value representing the size of an Ethereum address. Address is a datatype in solidity. 

functions which are **public** can be accessed by anyone who is connected to blockchain.  

Use remix.ethereum as IDE to create Smart contracts in Ethereum. 

The smart contract will be like a microservice all read write data with it, execute it. Its publically accessible. 



**Pointers**
1. ```uint``` cannot be negative 
2. View functions ensure that they will not modify the state. 
3. Getter method are by default view functions


3 Types of variables in Solidity: 

**State Variables** Variables whose values are permanently stored in a Contract storage.

**Local Variables** Variables whose values are present till function is executing.

**Global Variables** These are special variables which exist in global namespace and are used to get information about the blockchain. 

**Solidity-Structs**

Struct types are used to represent a record. Suppose you want to keep track of your books in a library. You might want to track the following attributes about each book −

```
pragma solidity ^0.5.0;

contract test {
   struct Book { 
      string title;
      string author;
      uint book_id;
   }
   Book book;

   function setBook() public {
      book = Book('Learn Java', 'TP', 1);
   }
   function getBookId() public view returns (uint){
      return book.book_id;
   }
}
```

Solidity provides a datasctructure called Mapping. 

**mapping** is like **associative array** or like hash map in other languages

```mapping(unit=>Person) public people;``` is like hashmap. 

In Solidity, no way to figure out size of array, so we have to keep track of it with count inside structs. 


**Modifiers**
Who are allowed to access the method.  

**public modifier**: can be used by external callers. 

**internal functions**: external callers cant use them. Different visibility of functions.  

**Custom modifiers**: we can create our own modifiers. 

```
modifier onlyOwner() {
    require(msg.sender == owner); 
}
```
*require has to be true otherwise error thrown*

**msg.sender** tells us the account which is calling a specific function. 

Use Epoch time in ethereum as well. 

```block.timestamp``` is used to find ```now()```


Contract owner is different from Token Owner


A **Modifier** allows you to control the behavior of your smart contract functions. It includes a variety of use cases, such as restricting who has the ability to run a given function, unlocking functions at a certain time frame, etc


**Truffle** is a world-class development environment, testing framework and asset pipeline for blockchains using the Ethereum Virtual Machine (EVM), aiming to make life as a developer easier. Truffle is widely considered the most popular tool for blockchain application development with over 1.5 million lifetime downloads.

On mintable or rarible, you are the token owner and not the contract owner. Only the contract owner can set up royalties. 


ERC: Ethereum request for comments. It features a standard set of rules for creating tokens on Ethereum. 


**ERC721** tokens have become quite popular in recent times with the radically growing attention towards NFTs. As a matter of fact, the basic nature of ERC-721 tokens is one of the formidable factors for ERC20 vs. ERC721 differences. ERC-721 tokens are also **referred to as NFTs**. 

The difference between **ERC20 and ERC721** tokens is that every token in the ERC721 contract is unique. It’s like deploying many ER20 contracts, just under one address. ERC20 Tokens can be sent from one address to another. This is a very fundamental property why ERC20 tokens are so popular.

ERC721 transferFrom function: 

```
 function transferFrom(address from, address to, uint256 tokenId) external;
```

**Non Fungible**: a unique digital identifier that cannot be copied, substituted, or subdivided. 



**Physical and Digital Example**

An interesting ERC721 example which brings the digital and physical world together: https://medium.com/aisthisi/aisthisi-technical-deep-dive-part-1-4f708da67cbd 


**ABI** The Contract Application Binary Interface (ABI) is the standard way to interact with contracts in the Ethereum ecosystem, both from outside the blockchain and for contract-to-contract interaction
