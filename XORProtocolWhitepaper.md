# XOR Protocol Whitepaper

Apr 2nd, 2018

## Abstract
The XOR Protocol is a financial system built on a distributed public ledger that supports a unique class
of markets and securities, which are more transparent, decentralized, democratic, and general than current
systems. Examples include simple loans, mortgage bonds, and derivative markets such as Collateral Debt
Obligations (CDO) and Credit Default Swaps (CDS). XOR uses smart contracts to model any type of loan.
Many markets can be modeled as debt contracts, thus enabling a universe of potential XOR markets with
the aforementioned benefits over their current analogs. All market transactions are recorded on a public
ledger using Distributed Ledger Technology (DLT), a more general paradigm of blockchain technologies,
in order to ensure end-to-end transparency. An additional benefit of XOR’s decentralized approach is the
elimination of parasitic fees, such as fees from third party credit ratings agencies, insurance providers, and
centralized banks. Borrowers receive superior borrowing rates and lenders receive higher ROI. Another
important aspect of XOR is self governance and modularity. Actors in the system will be able to choose
their own credit score implementations, insurance rates, risk models, and any other market variables. We
can assume that any given model will not stay relevant for infinite time, but in the future at least one type
of basic functioning model will exist. XOR aims to rectify this by allowing democratized modularity in
the creation of markets. This flexibility is important in order to ensure that the XOR Protocol can adapt to
future changes in market and real-life circumstances. In addition, XOR is designed as a protocol layer
rather than as its own system. This makes it possible to build XOR on top of any other currency system,
i.e. the Ethereum network or the Bitcoin network. As long as at least one distributed ledger exists, the
XOR Protocol can exist. XOR will open doors to fair loans and credit access to people across the world
by providing an accessible platform through which anyone in the world can create a market or invest in
markets in a way that is transparent, distributed, fair, and flexible.

## I. Introduction
### I.1 Background
The 2008 Housing Crisis is well known to have triggered a global financial meltdown. Many factors
contributed to the crisis, but one major cause was financial agencies’ lack of transparency. Lenders
were allowed to create contracts with borrowers who could not actually afford the mortgage rates
over time, creating a market of immense risk. This was compounded by additional liquidity and
market exposure from derivative instruments such as CDOs. The risk was covered up by ratings
agencies, who had the authority to incorrectly label CDO tranches. Under a system where debt
issuers pay ratings agencies to rate the strength and weaknesses of the securities they offered,
ratings agencies were incentivized to underrate the riskiness of securities, creating a system where
investors were unaware of the true riskiness of investments. When borrowers began to default on
the contracts because they could not actually afford them, the housing market collapsed, triggering
a global recession.

### I.2 Solution
XOR solves this problem by employing a distributed and self-governed system. All transactions
are stored on a distributed public ledger. This makes it impossible to misrepresent the riskiness of
contracts because there is no one central party to determine and rate such loans. Anyone can check
the ledger and verify the contents of a contract. This automatically allows for a more fair contract
system for individual users. Moreover, it becomes possible to create derivative markets (and thus
provide important liquidity to markets) in a transparent and scalable way that circumvents the
issues faced in 2008. As XOR is decentralized, anyone in the world can make any market or
derivative market. With additional governance structures, participants can democratically achieve
maximum system efficiency.

Another issue with modern financial systems is that once elements become entrenched in the
system, it becomes hard to improve upon them, even if such elements are harmful. For example,
the mechanisms for calculating FICO credit scores are entirely opaque, meaning that no credit
borrower can actually know why their score is what it is. Additionally, FICO scores reward some
unspecified amount of debt exposure, and penalize having zero debt exposure. A system that
encourages paying off debts rather than obtaining them would create a healthier financial society.
However, it is possible that a future financial system could require a different approach to personal
ratings. In this paper, we propose models that are transparent and scaleable. In spite of that, the
core premise of XOR is the acknowledgement that no matter how good a model may be, it could
become obsolete in the future. Keeping this in mind, our implementation is modular and thus
future-proof.

XOR aims to provide a general financial framework that can encompass any market type.
Examples include standard cryptocurrencies, stablecoins, physical commodities such as gold,
mortgages, car loans, etc. Ultimately, we wish to create a general and open protocol that will stand
the test of time and last for as long as the concept of finance itself.

## II. Markets
### II.1 Market Creation
A market can be initialized by anyone with access to the XOR Protocol and can be created on
top of any distributed ledger. Because XOR utilizes a smart contract architecture, markets can be
based on any asset that can be modeled as a type of monetary debt contract. Any of a market’s
parameters can be adjusted modularly, enabling a range of simple hardcoded fixed parameter
markets to fully flexible and modular markets.

### II.2 Teller Functions
A market’s interest and insurance rate calculations are carried out by a teller function, which is a
piece of arbitrary code that takes as input the parameters of a loan (maturity period, borrower
trust score, etc.) and outputs an insurance rate and interest rate. Markets are associated with a
teller function at creation time, a process that requires a fee corresponding to the cost of deploying
the function as a contract to the blockchain network. Since the function resides on the blockchain,
the code is transparent. Currently, a market cannot change its associated teller function once
created.

Users are incentivized to create markets with high accuracy teller functions: functions which
consistently output insurance and interest rates that justly reflect the underlying risk of the
loan. This is accomplished by awarding a fixed percentage of each transaction carried out on a
managed market to the market creator. Since users will only be willing to pay this transaction
fee if the teller function has been historically accurate, it is expected that markets that eventually
become popular on the XOR network will serve as industrial-grade, high-throughput mediums of
exchange between lenders and borrowers who have highly variable or even unknown risk profiles.
Market definitions themselves are modular; for example, one can swap out the fixed transaction
percentage for a variable percentage.

Having programmable teller functions ensures that the XOR Protocol will never become stale
as more intelligent implementations are discovered. Rather than accept permanence within a
financial market, the XOR Protocol encourages healthy competition in order to find the most
intelligent teller functions. For example, in theory this allows markets to not only be traded by
artificial intelligences, but also fundamentally created and managed by artificial intelligences. The
flexibility of the XOR teller system provides a testbed through which to achieve optimal financial
markets.

## III. Simple Loan Examples
In order to understand how the XOR Protocol works, we need to first understand how XOR loans
work. A loan is essentially a contract describing a debt obligation. This can be used to model
many other types of securities. For example, a stock is a trade between cash and equity. With
the advent of smart contracts, any type of financial contract can be encapsulated within the XOR
Protocol.

In this section, we will walk through the example of a basic loan, and compare it to an XOR
loan. Loans are the basic building blocks of financial markets. Most financial instruments can be
modeled as debts or derivatives of debts. It is important to note that a simple peer-to-peer loan is
a special case of a risk-mitigated market loan.

### III.1 Traditional Peer-To-Peer Loans
A simple traditional peer-to-peer loan involves one borrower and one lender. Normally, the basic
steps for securing a typical loan would be:
A simple traditional peer-to-peer loan involves one borrower and one lender. Normally, the basic
steps for securing a typical loan would be:

1. The lender assesses the risk profile of the borrower. He normally does this with by requesting
a FICO score report from a consumer reporting agency, such as Equifax. This costs money to
do. FICO scores are a blackbox and are notoriously difficult to navigate, because FICO does
not publish its algorithms.
2. If the lender accepts the loan, he has the option of purchasing insurance in case of a default.
Insurance providers pay the lender some or all of the borrowed amount back in the event of
a default. They charge extra fees on top of initial collateral.
3. The lender and borrower agree upon contract terms and proceed with the transaction. The
borrower either pays his debt back on time with interest, or he fails to do so and defaults.
This can be extended to include annuities as well.

In this system, the two primary third parties are the credit score provider and the insurance
provider.  Both parties charge extraneous fees to system participants, and both parties are
centralized and opaque.

### III.2 XOR Peer-to-Peer Loans
An XOR peer-to-peer loan is different in that it utilizes decentralized approaches to centralized
systems. This creates a fee-free structure, enabling better rates for borrowers and higher ROI for
lenders by eliminating trickle-down costs versus traditional loans, with no real disadvantages. An
XOR loan works as follows:

1. The lender asses the borrower’s risk profile by using a distributed rating mechanism (called
Trust in XOR). Trust allows for the borrower to have a risk rating by inputting a variety of
factors. System participants vote on the Trust protocol and are thus incentivized to make it
fair. Trust will be discussed in detail later in this paper.
2. Instead of purchasing insurance from an insurance provider, the lender places a collateral fee
into a collected pool with all other lenders. Lenders vote upon the parameters of the pool,
such as how Trust ratings correspond to different collateral fees, how defaults are handled,
etc. This will also be described in detail later in the paper.
3. The two parties agree upon a contract, and the anonymized contract is stored on a distributed
public ledger. This allows for total transparency of the system, enabling a rich ecosystem of
derivative markets.

### III.3 Risk Mitigated Market Loans
A natural extension of the peer-to-peer is risk mitigated market loans. Here, an initial borrow
request is split amongst multiple lenders, and each lender separately earns interest on their
lending amount. The borrower would approach the loan in the same way as he would with a
peer-to-peer loan, and lenders would approach their portion of the contract in the same way as a
peer-to-peer loan as well. In a risk mitigated market loan, all lenders share responsibilities for loan
defaults. Through the creation of a many-to-many relationship between lenders and borrowers in
each market, the default exposure for each lender is greatly reduced.

## IV. Loan Procedure
Within a given market, we have designed a procedure for processing loan contracts. It is important
to remember that loans are just a model for generic financial contracts. The loan procedure is
processed within a round. Rounds include a parameter voting stage and insurance analysis stage.
Information for both stages are processed from individual and market level risk profiles. Investors
may also process bids with Loan Intents, which are contracts of automated contract selection logic.

### IV.1 Rounds
All markets operate in rounds, which are composed of a request period followed by settlement.
During the request period, borrowers are able to request funds with a certain maturity date and
maximum interest rate they are willing to pay. Lenders are also able to file loan intents during
this period, which contain a single vote for the risk coefficient used to calculate interest rates in
the market (described in more detail below). Lenders and borrowers select markets which best fit
their needs by looking at the market parameters. As with other decentralized currencies, multiple
lenders can fulfill a single loan request, increasing market liquidity. Market creators are rewarded
for the success of their markets. During parameter voting rounds, voters that provide parameters
which are close to those voted upon will also receive rewards.

### IV.2 Parameter Voting
Lenders and borrowers look for markets that best suit their needs. It could be possible that a
borrower is looking for the highest amount of cash for the lowest interest rate, and a lender is
looking for lending the lowest amount of cash at the highest interest rate. By removing parasitic
fees, lenders and borrowers are able to reconcile their interests. Both lenders and borrowers have
the flexibility to choose markets however they want. For example, borrowers could query markets
for how quickly they can receive cash, rather than for the best financial deal.

Borrowers will always look for the highest amount of cash for the lowest interest rate. On the
other hand, lenders will always look for lending the lowest amount of cash at the highest interest
rate. While these may seem to be conflicts of interest at first, the XOR Protocol creates incentives
for both parties to participate fairly and in a mutually beneficial manner.

A market contains its own risk coefficient (to be voted upon by lenders), and every individual
contract has its own risk coefficient as well. Assuming that interest rates are a function of risk,
lenders can vote on the mapping of risk coefficients to interest rates. In addition, borrowers can
choose to accept that market or to move to a different market.

Lenders are interested in making as high a return on investment as possible, meaning that they
want to gain as much as possible in direct interest while paying very little in insurance pool fees.
This further drives down the price for borrowers because lenders are incentivized to not vote on
high interests at risk of losing customers to another market.

### IV.3 Insurance
In order to hedge against defaults, lenders have the option of posting a collateral fee to the collected
insurance pool. This fee is based on the Trust of any given borrower combined with the risk profile
of the market. In general, a higher Trust would correspond with a lower insurance premium
(collateral fee) for the lender, because that borrower would be unlikely to default. Similarly, a
lower market risk factor would correspond to lower insurance premiums for all lenders. In the
event of a default, the lender is paid back based on the programed parameters of the insurance
agreement as well as the market. For example, markets may choose to process insurance payouts
over time so as to avoid rapidly deteriorating the shared insurance pool. This insurance structure
is modular at the market level, thus allowing for total flexibility and control. In many markets,
such as in risk-mitigated markets, an insurance pool may not be relevant. XOR simply presents
the choice of implementing an insurance model.

When a contract is created, the XOR Open Loan system forces a low interest rate for buyers,
and low insurance fees (and thus highest possible ROI on interest) for lenders. It would make no
sense for a lender to place a bid for a contract with an unnecessarily high fee amount because that
would devalue the bid and increase his own cost to no real benefit. In the XOR Open Loan system,
everybody wins by collaborating for mutual benefit.

### IV.4 Loan Intents
To supply funds to a certain market, an investor creates a Loan Intent with the specific amount of
funds to be supplied, and the risk coefficient that the investor believes characterizes the current
risk-reward profile in the market. The Loan Intent is essentially a pre-programmed instruction to
automatically invest in a contract that meets certain programmed parameters.
If the investor is not selected to participate in the round (i.e. since the supply of credit exceeds
the demand for credit, or all contracts are fulfilled), the funds are simply returned to the investor.
To remove unnecessary manual labor from the process of supplying funds, the XOR platform
could provide a simple utility to reinvest unused funds by recreating rejected Loan Intents until
one is accepted. This process closely models a market order in stock market terminology.

### IV.5 Portfolios
Portfolios in XOR, in a manner analogous to mutual funds in the traditional financial system, allow
investors to organize their investments. Just as markets aggregate borrower requests, portfolios
aggregate a user’s loan intents. This additional layer of abstraction allows XOR to natively support
investment diversification; since each market represents a relatively consistent risk profile, holding
a portfolio with many different markets constitutes diversification.

Just like a mutual fund, it is possible for many lenders to invest in a single portfolio, which
simply means that each investor creates loan intents in the same markets and supplies funds
to each market in the same proportions. This allows layman investors who are not capable of
analyzing the individual risk-reward profiles of individual markets, as well as investors who do
not have the time to construct their own portfolio, to choose a suitable portfolio to invest in out of
the current well-performing portfolios. As with everything in XOR, the performance of a portfolio
is completely transparent; statistics on past returns and losses can be computed by any user since
historical information on the underlying markets is freely available. Finally, as portfolios represent
a group of investments in different markets, it follows naturally that portfolios can be combined
with other portfolios. This allows portfolios to be iterated upon seamlessly.
