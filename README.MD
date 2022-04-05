# Welcome to first FunC contest by TON Foundation

There are five `.fc` files in the folder:
1. [1.fc](1.fc) - First problem "Counter"
2. [2.fc](2.fc) - Second problem "Proxy"
3. [3.fc](3.fc) - Third problem "Address Memorizer"
4. [4.fc](4.fc) - Fourth problem "Hashmaps"
5. [5.fc](5.fc) - Fifth problem "Two-owner wallet"

Each file has two parts:

* Comment with description of what the smart-contract should do.

* Code of smart-contract with one or more functions marked as `testable`.

The purpose of the contestants is to match code and description, fix bugs if provided code does not satisfy description and optimize the code. 

We ask participants to not change the signature (number, order and types of arguments and result) of `testable` functions for us to be able to evaluate their submission.

## How to submit

Solutions should be submitted as tar archive which contain up to 5 files labeled `1.fc`, `2.fc`, `3.fc`, `4.fc`, `5.fc` (each file represents a corresponding task). 

Each file will be compiled with func from [main repository](https://github.com/newton-blockchain/ton/tree/master/crypto/func). During compilation each file will be supplemented with a [stdlib - FunC standard library](https://github.com/newton-blockchain/ton/blob/master/crypto/smartcont/stdlib.fc). 

Each submission tarball should also contain `participant.json` with the following structure:
```
{
  "address" : "your-TON-wallet-address", 
  "username": "desired-username-in-public-list",
  "codeforces": "(optional)codeforces-username"
}
```

Bot for receiving submissions will be announced later on https://t.me/toncontests.

This challenge aims to attract new developers to TON ecosystem. To reduce the chances of newcomers discouraging we kindly ask skilled developers of already established TON teams to participate with "out of competition" mark.
You can set "out of competition" mark by adding to the tarball file with name `OUT`.

## How will it be checked

For each problem we have a set of test vectors which satisfy the description. 

We will automatically run those tests against the `testable` functions. 

If functions of one task pass all the tests, this task is considered "solved". 

For "solved" tasks gas-usage of each test is recorded, sum of gas used by all tests is the second-order metric which will allow us to determine the winner amongst people with equal number of solved tasks.

Winners are determined as follows:

* Person who solved more tasks will be ranked higher then person who will solve less (regardless of optimization).

* For evaluation of gas-usage each problem has a weight which in general inversely correlated with average gas-usage, thus 10 gas units optimization of the function which consume 100 gas units will be scored higher than 10 gas units optimization of the function which consume 10000 gas units.

* Get methods will not be measured for gas usage: since such methods are executed locally, in contrast to on-chain execution, they are much less sensitive to gas consumption.
Thus efficiency or inefficiency of get-methods will not affect the ranking (ofc if those getmethods are not called from testable functions)

## Docs

We recommend participant to check out https://ton.org/docs in particular "Basic concepts" and "Smart Contracts" sections. 

Additional and detailed information is available in [whitepapers](https://ton.org/docs/#/docs).

Examples of standard smart contracts can be found [here](https://github.com/newton-blockchain/ton/tree/master/crypto/smartcont).

Developer Chats - https://t.me/tondev_eng, https://t.me/tondev.

Introduction - https://telegra.ph/Its-time-to-try-something-new-Asynchronous-smart-contracts-03-25.

## How to compile and test

We recommend using the [toncli](https://github.com/disintar/toncli) - open source tool written by community developers.

This tool allows you to work with FunC smart contracts on Ubuntu, MacOS or Windows - compile them and run local tests. Also many other things, but in this contest you don't need to deploy contracts to the network.

Playground toncli + 1st contest task you can find [here](https://github.com/disintar/task-1-playground).

If for some reason you don't want to use the tool you can use the FunC compiler and Fift scripts [directly](https://ton.org/docs/#/smart-contracts/?id=func).

For syntax highlighting you can use [TON IDEA Plugin](https://plugins.jetbrains.com/plugin/18541-ton-development) or [Sublime Text Plugin](https://github.com/savva425/func_plugin_sublimetext3).
