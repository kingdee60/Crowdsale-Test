# Crowdsale_Test
Background
After waiting for years and passing several tests, you were selected by the Martian Aerospace Agency (a fictitious organization) to become part of the first human colony on Mars. As a prominent fintech professional, you were chosen to lead a project developing a monetary system for the new colony. You decide to base this new system on blockchain technology and to define a new cryptocurrency, named KaseiCoin. (Kasei means Mars in Japanese.)

KaseiCoin will be a fungible token that’s ERC-20 compliant. You’ll launch a crowdsale that will allow people who are moving to Mars to convert their earthling money to KaseiCoin.

What You're Creating
A fungible token that’s ERC-20 compliant and that will get minted via a crowdsale contract that you create based on the Crowdsale contract from the Solidity library.

A crowdsale contract that you create, which manages the entire crowdsale process. Specifically, it will allow users to send ether to the contract and receive KAI, or KaseiCoin tokens, in return. Your contract will automatically mint the tokens and distribute them to buyers in one transaction.

Either a short video or a set of screenshots that illustrates your work for each subsection of the Challenge. You should place this in the Evaluation Evidence section of the README.md file in your GitHub repository for this Challenge.

Files
Download the following files to help you get started:

Starter code

Instructions
The high-level steps for this Challenge are as follows:

Create the KaseiCoin token contract.

Create the KaseiCoin crowdsale contract.

Create the KaseiCoin deployer contract.

Deploy the crowdsale to a local blockchain.

Optional: Extend the crowdsale contract by using OpenZeppelin.

The following subsections detail the instructions for these steps.

Create the KaseiCoin Token Contract
In this section, you’ll create a smart contract that defines KaseiCoin as an ERC-20 token. To do so, complete the following steps:

Import the provided KaseiCoin.sol starter file into the Remix IDE.

Import the following contracts from the OpenZeppelin library:

ERC20

ERC20Detailed

ERC20Mintable

Define a contract for the KaseiCoin token that’s named KaseiCoin, and have the contract inherit the three contracts that you just imported from OpenZeppelin.

In the KaseiCoin contract, add a constructor with the following parameters: name, symbol, and initial_supply.

As part of the constructor definition, add a call to the constructor of the ERC20Detailed contract, passing the name, symbol, and 18 parameters. (Recall that 18 is the value for the decimal parameter.)

Compile the contract by using version 0.5.5 of the compiler.

Check for errors, and debug them as needed.

Take a screenshot of the successful compilation of the contract, and then add it to the Evaluation Evidence section of the README.md file for your GitHub Challenge repository.

Create the KaseiCoin Crowdsale Contract
In this section, you’ll define the KaseiCoin crowdsale contract. To do so, complete the following steps:

Import the provided KaseiCoinCrowdsale.sol starter code into the Remix IDE.

Have this contract inherit the following OpenZeppelin contracts:

Crowdsale

MintedCrowdsale

In the KaisenCoinCrowdsale constructor, provide parameters for all the features of your crowdsale, such as rate, wallet (where to deposit the funds that the token raises), and token (the KaseiCoin that the KaseiCoin crowdsale will use). Configure these parameters as you want for your KaseiCoin token.

Compile the contract by using version 0.5.5 of the compiler.

Check for errors, and debug them as needed.

Take a screenshot of the successful compilation of the contract, and then add it to the Evaluation Evidence section of your README.md file.

Create the KaseiCoin Deployer Contract
In this section, you’ll create the KaseiCoin deployer contract. To do so, complete the following steps:

Uncomment the KaseiCoinCrowdsaleDeployer contract in the provided KaseiCoinCrowdsale.sol starter code.

In the KaseiCoinCrowdsaleDeployer contract, add variables to store the addresses of the KaseiCoin and KaseiCoinCrowdsale contracts, which this contract will deploy.

Create an address public variable named kasei_token_address, which will store the KaseiCoin address when that contract has been deployed.

Create an address public variable named kasei_crowdsale_address, which will store the KaseiCoinCrowdsale address once that contract has been deployed.

Add the following parameters to the constructor for the KaseiCoinCrowdsaleDeployer contract: name, symbol, and wallet.

Finish the constructor body by completing the following steps:

Create the KaseiCoin token by using a new instance of the KaseiCoin contract with the name and symbol parameters and by setting the initial_supply parameter to 0.

Assign the address of the KaseiCoin token contract to the kasei_token_address variable. (This will allow you to easily get the token's address later.)

Create a new instance of the KaseiCoinCrowdsale contract by using the following parameters:

rate: Set rate equal to 1 to maintain parity with ether.

wallet: Pass wallet in from the main constructor. This is the wallet that will get paid all the ether that the crowdsale contract raises.

token: Use the token variable where KaseiCoin is stored.

Assign the address of the KaseiCoin crowdsale contract to the kasei_crowdsale_address variable. (This will allow you to easily get the crowdsale’s address later.)

Set the KaseiCoinCrowdsale contract as a minter.

Have the KaseiCoinCrowdsaleDeployer renounce its minter role.

Compile the contract by using version 0.5.5 of the compiler.

Check for errors, and debug them as needed.

Take a screenshot of the successful compilation of the contract, and then add it to the Evaluation Evidence section of your README.md file.

Deploy the Crowdsale to a Local Blockchain
In this section, you’ll deploy the crowdsale to a local blockchain by using Remix, MetaMask, and Ganache.

IMPORTANT
Record a short video or take screenshots that illustrate these steps as evidence of your deployed crowdsale contract. If you provide screenshots, add them to the README.md file of your GitHub Challenge repository. The screenshots should provide a guide that someone else can use to compile the contracts and add the KaseiCoin token to MetaMask. If you record a video, publish it either on a free hosting video platform, like YouTube or Vimeo, or in a shared Google Drive folder. Then add a public link to the video in the README.md file.

If you choose to record a video, you can record it as either an animated GIF or a screen recording. To do so, you can use any of the following tools:

On either macOS or Windows, Recordit Links to an external site.to create an animated GIF.

On macOS, the built-in QuickTime player to create a screen recording. To learn more about this tool, refer to Use QuickTime Player Links to an external site.in Apple Support.

On Windows 10 or 11, the built-in Xbox Game Bar to create a screen recording. To learn more about this tool, refer to Use Xbox Game Bar to capture game clips and screenshots on Windows Links to an external site.in the Xbox documentation.

To deploy the crowdsale to a local blockchain, complete the following steps:

Deploy the crowdsale to a local blockchain by using Remix, MetaMask, and Ganache.

Test the functionality of the crowdsale by using test accounts to buy new tokens and then checking the balances of those accounts.

Review the total supply of minted tokens and the amount of wei that the crowdsale contract has raised.

Optional: Extend the Crowdsale Contract by Using OpenZeppelin
In this optional section, you can extend the crowdsale contract to enhance its functionality. If you do so, you’ll use the following OpenZeppelin contracts:

CappedCrowdsale: Allows you to cap the total amount of ether that your crowdsale can raise.

TimedCrowdsale: Allows you to set a time limit for your crowdsale by adding an opening time and a closing time.

RefundablePostDeliveryCrowdsale: Adds the capability of refunding your investors to your crowdsale. Each time that you launch a crowdsale, you set a goal amount of ether to raise. If the goal isn’t reached, it’s a common practice to refund your investors.

NOTE
We encourage you to read more about these contracts on the Crowdsales Links to an external site.page in the OpenZeppelin documentation.

To extend your crowdsale contract with the preceding functionality, complete the following steps:

Import the three OpenZeppelin contracts into the KaseiCoinCrowdsale.sol contract, as the following code shows:

import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/crowdsale/validation/CappedCrowdsale.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/crowdsale/validation/TimedCrowdsale.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/release-v2.5.0/contracts/crowdsale/distribution/RefundablePostDeliveryCrowdsale.sol";
Note that your KaseiCoinCrowdsale contract previously inherited the Crowdsale and MintedCrowdsale contracts from OpenZeppelin. Have your KaseiCoinCrowdsale contract also inherit the following three contracts, which you just imported:

CappedCrowdsale

TimedCrowdsale

RefundablePostDeliveryCrowdsale

In the KaseiCoinCrowdsale constructor, add the following parameters:

uint goal: This variable will represent the amount of ether that you hope to raise during the crowdsale—that is, the goal of the crowdsale.

uint open: This variable will represent the opening time for the crowdsale.

uint close: This variable will represent the closing time for the crowdsale.

Complete the KaseiCoinCrowdsale constructor code by adding calls to the new contracts, as the following code shows:

constructor(
        uint256 rate, // rate in token bits
        address payable wallet, // sale beneficiary
        KaseiCoin token, // the KaseiCoin itself that the KaseiCoinCrowdsale will work with
        uint goal, // the crowdsale goal
        uint open, // the crowdsale opening time
        uint close // the crowdsale closing time
    ) public
        Crowdsale(rate, wallet, token)
        CappedCrowdsale(goal)
        TimedCrowdsale(open, close)
        RefundableCrowdsale(goal)
    {
        // constructor can stay empty
    }
IMPORTANT
The RefundablePostDeliveryCrowdsale contract itself inherits the RefundableCrowdsale contract, which requires a goal parameter. So in addition to calling the others, your KaseiCoinCrowdsale constructor must call the RefundableCrowdsale constructor. The RefundablePostDeliveryCrowdsale contract doesn’t have its own constructor, which is why it uses the RefundableCrowdsale constructor that it inherits.

If you forget to call the RefundableCrowdsale constructor, the RefundablePostDeliveryCrowdsale will fail.

Update the KaseiCoinCrowdsaleDeployer contract to allow the deployment of the updated crowdsale contract. In the constructor of the deployer contract, add a new uint parameter named goal that will allow you to set the crowdsale goal.

Recall that in the core assignment, you added an instance of the KaseiCoinCrowdsale contract to the KaseiCoin deployer contract. Because you’ve modified the KaseiCoinCrowdsale contract to support new functionality, update your previous code with the following code:

KaseiCoinCrowdsale kasei_crowdsale = new KaseiCoinCrowdsale (1, wallet, token, goal, now, now + 24 weeks);
Note that in the preceding code, you added values for the three new parameters. The goal parameter represents the amount of ether to raise during the crowdsale. The now parameter represents the crowdsale opening time. And, now + 24 weeks represents the closing time.

The now function returns the current Ethereum block timestamp in the form of seconds since the Unix epoch. The Unix epoch (also known as Unix time, POSIX time, or Unix timestamp) is an integer that represents the number of seconds that have elapsed since January 1, 1970 at midnight Universal Coordinated Time (UTC), not counting leap seconds.

Compile and test the updated contract by completing following steps:

Send ether to the crowdsale from a different account (that is, not from the account that’s raising funds). When you confirm that the crowdsale works as expected, try to add the token to your wallet and test a transaction.

Set the close time to now + 5 minutes or to any time that you want to test for a shorter crowdsale.

When sending ether to the contract, make sure that you meet the goal of the contract. Then finalize the sale by using the finalize function of the Crowdsale contract. Note that to finalize the sale, isOpen must return false. (The isOpen function comes from TimedCrowdsale and checks if the close time has passed). If you set the goal to 300 ether, for example, you might need to buy tokens from multiple accounts to meet the goal. If you run out of prefunded accounts in Ganache, you can create a new workspace.

In MetaMask, review your tokens. To do so, click Add Token, click Custom Token, and then enter the address of the token contract. Make sure to buy enough tokens to get the denomination to appear in your wallet as more than a few wei worth.
