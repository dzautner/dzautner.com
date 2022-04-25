---
title: "A Distributed Computation Marketplace over Blockchain"
author: [Daniel Zautner]
date: "2022-02-22"
keywords: [Distributed Computing, Blockchain, Super-computer, Cryptocurrency]
---
We describe a Blockchain based[^1], peer-to-peer network of distributed computers solving arbitrary, strictly-defined problems for a financial incentive in the form of a cryptographic currency[^2].

The computational problems are signed and posted to the blockchain in a contract describing the minimal computational unit (MCU) of the problem, the price per MCU, a method for joining the results of different Solvers, and a test for the validity of a solution.

The Solver will transmit the solutions to the Bidder off the blockchain to avoid any space-complexity issues and eliminate the potential for network flooding with bogus or trivial solutions. 

The Bidder will transmit the Solver a signature for a payout transaction upon validation.

A solution for a single MCU is used as a handshake between Bidders and Solvers, and for each following solution message, the Solver will increase the number of MCUs on a logarithmic scale.

A Bidder can delegate the validation and signing process to Validators who place a significant monetary stake for this privilege and are rewarded by the network with a dynamic fee correlating to the number of open contracts. 

Once the Bidder receives a satisfactory amount of work, they can close the contract by submitting a signed message to the blockchain. 

## 1) Introduction
Leveraging the potential computation power available in personal computing has been the focus in several projects, with "Folding@home" being the most successful one. In April 2020, "Folding@home" reached 2.43 exaflops of computation power, making it the fastest computer in history, nearly doubling the maximum computation power reached by the world's fastest super-computer[^6] and that of the human brain.

While extremely impressive, "Folding@home" and similar projects are designed to solve particular problems[^4] and offer no incentive for participation other than the social good provided by the solutions.

With modern software architecture designed to run on distributed systems such as cloud "platform-as-a-service" providers, on-demand computation power is increasingly needed to be priced by a decentralized, open, and transparent market.

A decentralized marketplace of computation power, open for any person with internet access, will democratize the world of distributed computing at scale without allowing for a malicious mediator to take hold of potentially harmful computation power.  

By offering cash in the form of cryptocurrency, the network will have a powerful incentive[^8] to provide computation power and optimize itself over time to solve problems with the most beneficial pay and de-facto in the most optimized way pricing abstract notions of computation.

The incentive to solve problems as fast as possible opens the door for Solvers to optimize the code provided by the Bidder, giving Bidders an optimization process for their code as an integral part of the system and part of its attraction. 

As the computation power of the system is expected to have a high price elasticity[^9] in a space with alternative suppliers of computation (cloud providers, traditional server farms), several checks and balances must be placed to protect the underlining currency from high volatility as the result of speculative trading of the currency.

Ideally, the free-market pricing of the system's underlining currency will directly represent the computational power in the system.


## 2) The Monetary System
We describe our unique cash system over a Blockchain. Other than a novel difficulty algorithm, the abstract implementation details are similar to most typical blockchains, and as such, this paper will not get in-depth about the structure of a block and the hashing and signing algorithms involved. 

### Naming
The currency circulating in the system is called Zi (/zī/) in the plural, and Zaus (/zʌʊ̯s/) for a single coin.
A small monetary unit  Li (/lī/) worth 1/(10^9) Zi is used for smaller transactions and fees.

### Operating on an Independent Blockchain 
Having complete control over the structure and difficulty of the network is a prerequisite requirement for the system as it allows for:
1) Independence from movements in underlining currencies (as with L2 tokens over the Ethereum Network), making the currency's value directly reflect the computational power in the network, thereby increasing Solvers' motivation to provide computation power.
2) The ability to manipulate mining difficulty creates complex incentives for miners to prioritize time-sensitive messages in the block.

The network must first and foremost be a marketplace for distributed computing.
The blockchain ledger is a means to achieve that, not the end itself. As such, all the monetary incentives in the system must orient around computation and not the secondary economy, which will rise from the existence of a new tradable good named Zi.  

### Mining 
Mining a new block is the process of purposefully manipulating an otherwise empty field called "nonce" in the block until the block's hash follows the currently defined difficulty[^1].
The block's hash follows the current difficulty levels if the hash string starts with D amount of trailing zeros where D is the current difficulty.

To avoid inconsistent mining times, a minimum of T minutes between the mining of two consecutive blocks is placed. Any block mined before T minutes has passed since mining the last block will be rejected by the network as an invalid block.

### Mining Difficulty 
The mining difficulty has two objecting forces controlling it at any given moment:
1) The need to avoid the inflation of the currency as the network's mining power increases 
2) The need to verify time-sensitive messages as fast as required by the specific message type.

The first force increases mining difficulty over time to accommodate the increasing network's mining powers, while the second leads to a decrease in difficulty as the network's need for quick message verification increases.

To solve for both opposing forces, the following equation is used to determine the current block's difficulty:

Given H<sub>b</sub> is the height of the latest block (the number of the block on the chain), and P<sub>o</sub> is the set of all open problems currently on the chain, the difficulty support function is:

$$ Difficulty = \frac{\log (H_b)}{max(\frac{|P_o|}{C_1} \cdot C_2,\hspace{5px}C_{3)}}- (C_{t}\hspace{5px}{\cdot}\hspace{5px}
T) $$

Where
- C<sub>1</sub> determines how many open problems are required to reduce the difficulty.
- C<sub>2</sub> is a constant denoting the general difficulty of the network in reverse proportion (lower values lead to more difficult networks). 
- C<sub>3</sub> is the minimum difficulty adjuster. The difficulty will never increase above Log(H<sub>b</sub>) when the value is 1.
- (C<sub>t</sub> ⋅ T) is the reduction in difficulty for every T hours without a mined block in the network.

These constants are the control knobs of the network's economy.

### Transactions
Transactions are first signed by the sender of the coins and are then sent to the network for verification. Miners will include the transactions in the mining block for the fee defined in the transaction details. The fee is reduced from the sender's balance.

Each transaction can include a fixed-length block of metadata providing visibility into 
any additional information, but ideally with an IPFS[^10] URI that contains richer data. 

Using IPFS will allow for consistency in metadata of arbitrary size without risking a high space complexity in the system.

### Initial Injection of Currency into the Economy by Mining Empty Blocks

No Blockchain-based monetary solution to the payouts problem can 
operate as long as there is insufficient currency circulating in the economy for trades and exchanges to happen.
Any financial processes involving Zi can never happen as long as no Zi is circulating in the economy. 
If no one can pay for problem-solving, a marketplace of problem-solving can not function.

As such, mining empty blocky can provide the initial liquidity required for the operations of a marketplace. 
The project will start with several miners. The mined currency will be later divided for free to projects with social benefits and a need for computation power.

### Initial Injection of Contracts into the Economy

Another prerequisite to having an active marketplace of computing power is having people willing to buy computing power. 
To get the initial gears of the system moving, the revenue from empty mining blocks will be divided for free to projects in need of immense distributed computation power.

### Initial Injection of Computing Power into the Economy

Even worse than having unused computing power laying idle in the network awaiting instructions are having a high demand for computing power but none to satisfy it. 

As part of the bootstrapping of commerce in the marketplace, a few dozen Solver nodes will be distributed all over the globe and will take any job with pay higher than 10 Li.

To give a higher chance for honest Solver nodes to solve a problem, the bootstrapping Solvers will not start working on a contract until an additional block has been mined. If the new block does not contain any handshakes to the problem, the bootstrapping Solver nodes will not take the problem until at least three consecutive blocks without a solution have been mined. 

In the unlikely case that the bootstrapping Solvers will generate surplus value after covering their operation costs, the resulting currency will be sent to the shared network fund.

### The Shared Network Fund
Any surplus value generated in the system with no apparent address will be sent to the shared network fund, this includes any profit that might be generated when bootstrapping the marketplace but is mainly used to capture stakes of burned Validators (see: Guarding the Guards - an Auditing Protocol)

The shared fund will be divided based on a network vote.

Any active node (a node with at least ten transactions in the last 30 days), at any given moment, can cast a vote for the address they wish the shared funds will be deployed to - this is done by sending a signed "Vote" message to the network and is counted once the message is included in a mined block. The message should include fees, or the miner must include the vote for free - however, the market sees fit. 

Voters can vote for any address they wish, including their own - in which case the shared fund will work as a dividend distribution mechanism.

The project maintainers will also post projects to develop the protocol and the associated addresses, giving the network members an option to use the fund to develop the protocol further.

Once the shared fund reaches the critical size of one Zi per active node (with the active node being any node with at least ten transactions in the last 30 days), the distribution of the shared fund will be initiated. 
The funds will spread between participating addresses (any address which received a vote) in direct proportion to the number of votes the address received out of the total number of votes cast. 

## 3) The Distributed Computer
Bidders describe their distributed problems in a specific way that allows for any person viewing the bidding contract to:

- View and solve a minimal computational unit (MCU) of the problem for a given input.
- Retrieve the next set of inputs for the problem
- Join multiple results.
- Validate results.

The system's transparency allows for Solvers to optimize the code described by the Bidder and receive better pay-per-MCU than the rest of the network, giving a direct financial incentive not only to solve the problem but also to optimize the solution - leaving the Bidder with a much easier task than usual. 

In addition to the Bidder-defined values, some variables are generated automatically and can be accessed by the Solver.
Specifically, these are:
- The ranges of the problem previously solved - deducted from the metadata in work payout transactions on the blockchain
- Number of active Solvers working on the problem
- Bidder's MCU budget - how many more MCUs can the Bidder afford? 

Distributed programming is enormously complex because it copes with many possible non-deterministic behaviours of tasks being done simultaneously.
While the system described can not solve the difficulty of writing and defining distributed algorithms, it can provide an easy to understand step-by-step structure for defining the parallel workflow.

We will show by example how a problem will be defined to be executed on the network. 

We will use Python as the programming language; this is done for clarity and is not a requirement. The Bidder can post any code the Solver is willing to run.

#### Example - Mandelbrot Set
The Mandelbrot set is the set of complex numbers C for which the function f<sub>c</sub>(z) = z<sup>2</sup> + c does not diverge when iterated from z = 0. i.e, for which the sequence  f<sub>c</sub>(0), f<sub>c</sub>(f<sub>c</sub>(0)), etc remains bounded in absolute value.

In this example, we will find all the Mandelbrot Set members with five decimal accuracy points.

The work unit itself is pretty easy to define, and it is reasonably apparent that the MCU of the problem is a function that accepts a complex number and returns "True" if it is a member of the Mandelbrot set and "False" if it is not.

```Python
def MCU(c):
	z = 0
	for _ in range(1, 2000):
		z = z ** 2 + c
		if abs(z) > 1000:
			return False
	return True
```

The next step we must achieve is creating a function that generates inputs to work with and divide those equally between Solvers. 
We will have to find ranges previously solved and skip them for this section. 
These are accessible as they are saved on the blockchain as transaction metadata each time a Bidder pays a Solver for work. 

For development, we will create a mock for what is a function that will be accessible on runtime on a real network:

```Python 
def get_solved_ranges():
	return list(range(0, 1000)) + \
		   list(range(3000, 4000)) + \
		   list(range(13000, 29000))
```

We emulate a situation where previous Solvers have solved for the first 1,000 iterations of the input generator and the ranges between 3,000-4,000 and 13,000-29,000.
Emulating a job that was already partially solved is a good development practice to avoid developing only for happy paths. 

To write the input generator, we can take into account the fact that the Mandelbrot set input range is (-2, 2) in the real axis on (-1, 1) on the imaginary axis[^11]. Meaning we can skip all numbers outside these ranges. 

in code, we define an input generator as follows:

```Python
def get_inputs():
	decimal_count = 5
	D = 1/(10**decimal_count)
	solved_ranges = get_solved_ranges()
	i = 0
	for real in range(-2*(10**decimal_count), 2*(10**decimal_count)):
		for imaginary in range(-1*(10**decimal_count), 1*(10**decimal_count)):
			if i not in solved_ranges:
				real_mul = round(D*real, decimal_count)
				imaginary_mul = round(D*imaginary, decimal_count)
				yield i, real_mul+(imaginary_mul * 1j)
	i += 1
```


The input generator will skip solved ranges and yield an index an associated complex number to test.

All we have left to do is get fresh inputs, apply them to the MCU and return the data to Bidder:

```Python
def work(batch_size = 10000):
	inputs = get_inputs()
	results = []

	for _ in range(batch_size):
		index, complex_number = next(inputs)
		results.append([index, complex_number, MCU(complex_number)])

	return results
```

And that is all the code from the Solver's perspective.
The only contract pieces left to describe are the unification of results, validation, and rendering.

The union is exceptionally straightforward in this case, as it is a simple union of two lists.

```Python
def union(res1, res2):
	return res1 + res2
```

Validation is a step that is wholly flexible and not strictly required. If the Bidder trusts the network to solve problems honestly, they can omit it by defining the validation as a function that always returns true.

In most cases, a simple test that randomly samples results and compares them to a local recalculated version would be sufficient. 
For NP-complete problems, this is a complete non-problem.

We will sample 1% of the results for our Mandelbrot Set bid and re-run them as validation.

```Python
def validate(results):
	for result in results:
		[index, complex_number, solution] = result
		if index % 100 == 0 and MCU(complex_number) != solution:
			return False
	return True
		
```

####  Submitting Contracts
Contracts are submitted as a form of a transaction without a receiver. 
The contract definition transaction must include:
- The problem definition
- Price per MCU
- MCU Limit - above which the Bidder stops accepting results.
- A fee for the miners to include the contract in a block.
- Metadata in the form of a fixed size field containing all metadata required to operate the contract. Ideally, this field will be an IPFS[^10] URI.
- Validation - a boolean field. When true, the validation and collection will be delegated to a Validator. 
- Validation Fee - the fee the Bidder is willing to pay for validation per MCU.

 For the contract to be valid, the submitting identity must have a minimum balance that is sufficient to cover 1,000 MCUs, the transaction fees, and if opted for validation delegation - validation fees. 

 If the contract is not valid, the miners should not include it in their block or else the entire block loses its validity. 

### Solving Problems

The Solvers will pick a problem based on heuristics for the most profitable contract. Ideally, this calculation will be done by a client - removing the need for Solvers to pick the best contract every time.

Solvers broadcast solutions by messaging the Bidder or Validator directly. This is mandatory, or else any node between the Solver and the Bidder/Validator could kidnap the result as their own and receive the payout for the solution.

To find the correct node to message, the Solver will propagate a message through the network containing:
1) Solver node IP
2) Contract address (block hash + Bidder's signature)
3) Hash concatenates Solver's public-key, current timestamp, Solver's node IP, and the contract address. 

Once the message reaches the Validator or the Bidder, they will return an identifying acknowledgement by returning the message signed by them, their public key, and their node IP. 
Once the Solver receives the acknowledgement, they will directly send results to the Bidder/Validator node.
At first, the Solver will send a solution for one MCU. The message must include:
1) Contract blockchain address
2) Solver's blockchain address
3) MCUs performed
4) The solution. 
5) An unsigned transaction object from describing a transaction the Bidder/Validator, the Contract address in the transaction's metadata together with an IPFS address containing the results, timestamp, and the price expected for the work.  

Once the work and associated fields are confirmed, the Bidder/Validator will reply with a signature of the transaction.
A transaction signed by a legible Validator will reduce funds from the original contract Bidder and not the Validator. 

Once the Solver receives proof of payment from the Bidder/Validator, they will continue sending solution messages directly to the node (off the blockchain) in an increasing fashion.

### Validators
In order to become a Validator, an active network member (Involved in more than ten transactions of any kind in the last 30 days) must place a significant stake by sending a transaction to the network from themselves to the address '000'.
The required stake is dynamic and is correlated with the number of problems with the Validator delegation opened in the last T days - the higher the number, the higher the required stake. 

$$
	Stake =  |\{C : C \in V\hspace{5px}and\hspace{5px}T - C_{t} < 30| \cdot M
$$

Where
- C is the set all Contracts
- V the set of all Contracts delegated to Validators
- T - C<sub>t</sub> the number of days since the contract has been opened
- M is a multiplier reflecting the magnitude of each open contract on the Stake price.

#### Assigning Contracts to Validators
Each Contract has one Validator assigned to it at random.
Selecting a Validator for each Contract is done by calculating the Levenshtein distance[^12] between the Contract's hash and the hash of the Validator's Stake Transaction.
The score is the Validator's Fit for the Contract.
The Validator with the highest fit is selected. 
If two Validators have the exact fit, the one who places a higher stake is selected.
If the stake placed is similar, the Validator who placed a stake earlier is assigned the Contract.

Given V<sub>a</sub> is the Validator's Stake Transaction hash and C<sub>a</sub> the Contract's hash, the Validator fit is defined as follows:

$$
\operatorname{fit}(Va, Ca) = \begin{cases}
  |Va| & \text{ if } |Ca| = 0, \\
  |Ca| & \text{ if } |Va| = 0, \\
  \operatorname{fit}\big(\operatorname{tail}(Va),\operatorname{tail}(Ca)\big) & \text{ if } Va[0] = Ca[0] \\
  1 + \min \begin{cases}
          \operatorname{fit}\big(\operatorname{tail}(Va), Ca\big) \\
          \operatorname{fit}\big(Va, \operatorname{tail}(Ca)\big) \\
          \operatorname{fit}\big(\operatorname{tail}(Va), \operatorname{tail}(Ca)\big) \\
       \end{cases} & \text{ otherwise,}
\end{cases}
$$

The Validator with the highest fit is the only network member besides the Bidder that can sign payout transactions for solutions, and only in case, the Bidder opted to have a Validator assigned. 

Validators will only receive the validation fees once the auditing protocol is completed. Until then, the validation fees will remain in escrow.

## 4) Guarding the Guards - an Auditing Protocol

One obvious danger of Validators signing their payouts is that they will abuse their position by issuing bogus transactions under their authority to issue contract payouts. 
To solve this glaring security issue, we propose an auditing process as follows:

Once a contract delegated to Validators is closed, miners must vote on the validity of the Validator's payouts.
This is done by using the Contract's validation method on a sample of results signed by a Validator and stored on IPFS.
If the IPFS address is unavailable, the result counts as invalid, and the Miner should vote accordingly.
The miners then include an additional vote message in the block, similar to the one described in "§ The Shared Network Fund", containing the address of the Contract and a binary "Valid" or "Invalid". 
When casting a vote, the Miners receive an additional fee matching the Contract's validation price for 1,000 MCUs. The fee is not reduced from the Bidder and instead is minted.

Once three blocks mined by three different miners include a vote, the network counts the number of "Valid" and "Invalid" votes.

If the Validator was found to be acting in good faith, the validation fees are released from escrow and added to the Validator's balance.

If the Validator was found to act maliciously, the validation fees for the Contract are returned to the Bidder, and the Validation Stake is transferred to the shared network fund, and the Validator loses their status can no longer validate contracts results. 

### Validators Appeal
If a Validator wishes to appeal the decision, they can do so in the first 30 days after the original vote by sending an "Appeal transaction". 
The transaction is sent to '000' and includes the contract's address, which was deemed maliciously validated. 
The price for an appeal is the current price of Validator Stake as defined in "§ Validators".
Once an appeal starts, miners will vote again on the same problem. This time, nine unique votes are required.

If the Validator wins the appeal, they receive their stake and validation fees back.
If not, the appeal fee will also move to the shared network fund.

In cases of appeal, the validation fee to the miners is paid by the Validator appealing.

## References:
[^1]: S. Nakamoto "Bitcoin: A Peer-to-Peer Electronic Cash System" 2008
[^2]: A. Serapiglia, C. Serapiglia, J. McIntyre ["Cryptocurrencies: Core Information Technology and Information System Fundamentals Enabling Currency Without Borders"](https://files.eric.ed.gov/fulltext/EJ1137148.pdf) 
[^3]: A. L. Beberg, D. L. Ensign, G. Jayachandran, S. Khaliq and V. S. Pande, "Folding@home: Lessons from eight years of volunteer distributed computing," _2009 IEEE International Symposium on Parallel & Distributed Processing_, 2009, pp. 1-8, doi: 10.1109/IPDPS.2009.5160922.
[^4]: Anne Holohan, Anurag Garg, Collaboration Online: the Example of Distributed Computing, _Journal of Computer-Mediated Communication_, Volume 10, Issue 4, 1 July 2005, JCMC10415, [https://doi.org/10.1111/j.1083-6101.2005.tb00279.x](https://doi.org/10.1111/j.1083-6101.2005.tb00279.x)
[^5]: 1.  Pande lab. ["Client Statistics by OS"](https://archive.today/20200412111010/https://stats.foldingathome.org/os). April 12, 2020.
[^6]:  _  [_No contest: Japan's Fugaku again fastest supercomputer_](http://www.asahi.com/sp/ajw/articles/13938448)
[^7]:  _  ["Brain performance in FLOPS – AI Impacts"](https://aiimpacts.org/brain-performance-in-flops/). _aiimpacts.org_. 26 July 2015. Retrieved 27 December 2017.
[^8]: Victoria A. Shaffer, Hal R. Arkes, Preference reversals in evaluations of cash versus non-cash incentives, Journal of Economic Psychology, Volume 30, Issue 6, 2009, Pages 859-872, ISSN 0167-4870,
[^9]: Jiang, Qingye & Lee, Young & Zomaya, Albert. (2016). Price Elasticity in the Enterprise Computing Resource Market. IEEE Cloud Computing. 3. 24-31. 10.1109/MCC.2016.14. 
[^10]:  Juan Benet. (2014). IPFS - Content Addressed, Versioned, P2P File System.
[^11]: Riemann Surfaces and Related Topics: Proceedings of the 1978 Stony Brook Conference [Bernard Maskit](https://en.wikipedia.org/wiki/Bernard_Maskit "Bernard Maskit"). Princeton University Press.
[^12]: В. И. Левенштейн (1965). [Двоичные коды с исправлением выпадений, вставок и замещений символов](http://mi.mathnet.ru/dan31411) [Binary codes capable of correcting deletions, insertions, and reversals]. _Доклады Академии Наук СССР_ (in Russian). **163** (4): 845–848. Appeared in English as: Levenshtein, Vladimir I. (February 1966). "Binary codes capable of correcting deletions, insertions, and reversals". _Soviet Physics Doklady_. **10** (8): 707–710.

<link
	rel="stylesheet"
	href="https://cdn.jsdelivr.net/npm/katex@0.10.0-rc.1/dist/katex.min.css"
	integrity="sha384-D+9gmBxUQogRLqvARvNLmA9hS2x//eK1FhVb9PiU86gmcrBrJAQT8okdJ4LMp2uv"
	crossorigin="anonymous"
/>

<!-- JS Fle -->
<script
	defer
	src="https://cdn.jsdelivr.net/npm/katex@0.10.0-rc.1/dist/katex.min.js"
	integrity="sha384-483A6DwYfKeDa0Q52fJmxFXkcPCFfnXMoXblOkJ4JcA8zATN6Tm78UNL72AKk+0O"
	crossorigin="anonymous"
></script>