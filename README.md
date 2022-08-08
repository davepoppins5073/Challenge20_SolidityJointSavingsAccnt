# Challenge20_SolidityJointSavingsAccnt
![20-5-challenge-image](https://user-images.githubusercontent.com/101449950/183302821-de42884c-6d3e-4a2c-aaf8-71e337bdf01c.png)
---

# TASK 
Automate the creation of joint savings accounts with a Solidity smart contract that accepts two user addresses. These addresses will be able to control a joint savings account. Your smart contract will use ether management functions to implement a financial institution’s requirements for providing the features of the joint savings account. These features will consist of the ability to deposit and withdraw funds from the account.

---

# Instructions

The steps for this Challenge are divided into the following sections:
1. Create a Joint Savings Account Contract in Solidity
2. Compile and Deploy Your Contract in the JavaScript VM
3. Interact with Your Deployed Smart Contract

---
## Resources

### Remix IDE
<img width="1325" alt="Screen Shot 2022-08-07 at 1 38 58 PM" src="https://user-images.githubusercontent.com/101449950/183303945-2bf14db4-d5fd-402c-aaf9-01eba130d787.png">

**Remix Online IDE:** https://remix.ethereum.org
**Remix Documentation:** https://remix-ide.readthedocs.io/en/latest/#

> Remix IDE is used for the entire journey of smart contract development by users at every knowledge level. It requires no setup, fosters a fast development cycle and has a rich set of plugins with intuitive GUIs. The IDE comes in 2 flavors (web app or desktop app) and as a VSCode extension. Supported browsers: Firefox, Chrome, Brave. We do not support Remix’s use on tablets or mobile devices.

---
### Solidity

<img width="1018" alt="Screen Shot 2022-08-07 at 1 40 25 PM" src="https://user-images.githubusercontent.com/101449950/183304006-471a9f82-146e-4500-8eed-1826c5af7d7f.png">

> Solidity is an object-oriented, high-level language for implementing smart contracts. Smart contracts are programs which govern the behaviour of accounts within the Ethereum state. Solidity is a curly-bracket language designed to target the Ethereum Virtual Machine (EVM). It is influenced by C++, Python and JavaScript. You can find more details about which languages Solidity has been inspired by in the language influences section. Solidity is statically typed, supports inheritance, libraries and complex user-defined types among other features.

## CODE

### Step 1: Create a Joint Savings Account Contract in Solidity


Define a new contract named JointSavings.

#### Variables
Define the following variables in the new contract:
1. Two variables of type address payable named 
     1. `accountOne` 
     2. `accountTwo`
2. One variable of type address public named `lastToWithdraw`
3. Two variables of type uint public named `lastWithdrawAmount` and `contractBalance`


```solidity
contract JointSavings {

    /*
    Inside the new contract define the following variables:
    - Two variables of type `address payable` named `accountOne` and `accountTwo`
    - A variable of type `address public` named `lastToWithdraw`
    - Two variables of type `uint public` named `lastWithdrawAmount` and `contractBalance`.
    */
    address payable accountOne;
    address payable accountTwo;
    address public lastToWithdraw;
    uint public lastWithdrawAmount; 
    uint public contractBalance;


```
#### Functions
1. withdraw function: accepts two arguments: 
      1. amount of type uint 
      2. recipient of type payable address.

``` solidity
    function withdraw(uint amount, address payable recipient) public {
```

2. public payable function named deposit
      1. Set the contractBalance variable equal to the balance of the contract by using addressbalance.

``` solidity
function deposit() public payable {

        /*
        Call the `contractBalance` variable and set it equal to the balance of the contract by using `address(this).balance`.
        */
        contractBalance = address(this).balance;
    }
```  

3. public function named setAccounts that takes two address payable arguments:
      1. named account1 
      2. account2

```solidity
function setAccounts(address payable account1, address payable account2) public{

        // Set the values of `accountOne` and `accountTwo` to `account1` and `account2` respectively.
        accountOne=account1;
        accountTwo=account2;
    }
```
4. fallback function allows contract to store ether that’s sent from outside the deposit function.

```solidity
function() external payable {}
```
#### Statements

```solidity

```

### Compile and Deploy Your Contract in the JavaScript VM
1. Compile your smart contract without errors.
2. Deploy your smart contract in the JavaScript VM.

#### Contract Creation
<img width="1339" alt="Screen Shot 2022-08-07 at 2 47 49 PM" src="https://user-images.githubusercontent.com/101449950/183306568-601072b6-21a7-448e-b13c-fe24c3fea78e.png">

#### Compile (Contract)
<img width="1512" alt="Screen Shot 2022-08-07 at 2 52 17 PM" src="https://user-images.githubusercontent.com/101449950/183306663-e4411732-c9e4-4ec9-8439-9022e38883d1.png">

#### Deploy (Contract)
<img width="1512" alt="Screen Shot 2022-08-07 at 2 55 00 PM" src="https://user-images.githubusercontent.com/101449950/183317480-5a78e523-563f-4013-9cb3-f5ced5f46b0c.png">

---

### Interact with Your Deployed Smart Contract

<img width="363" alt="Screen Shot 2022-08-07 at 3 35 34 PM" src="https://user-images.githubusercontent.com/101449950/183318867-b7e9ae43-099b-40fc-89b3-1f200c85ba3b.png">


![image](https://user-images.githubusercontent.com/101449950/183319219-be7d4b5d-b3e5-4ab4-8e3b-6d5f77a32653.png)





![image](https://user-images.githubusercontent.com/101449950/183319102-9b7e6254-d7e2-4fdd-aa4c-623e5af41b70.png)



![image](https://user-images.githubusercontent.com/101449950/183318984-ac554964-d9e7-4b54-a7c3-0801560b03d0.png)







