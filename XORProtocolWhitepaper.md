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

## V. Trust Protocol
A robust Trust score protocol is required in order to allow lenders to verify borrowers without a
third party underwriter. The two situations that are possible are that a borrower has a Trust score
on the system, and the borrower does not have Trust. In the event that the borrower does not have
Trust, the system has to initialize a score. We propose a combination of parameter fitting user
input data and a process of Social Staking. Through Social Staking, borrowers are encouraged to
verify other borrowers. As with everything else in XOR, the Trust protocol is modular and can be
tuned per market. In addition, a given market’s Trust protocol will be transparent, creating a more
fair system. Higher Trust directly translates to increased buying power and a better risk profile.

### V.1 Trust
Trust is the decentralized and transparent XOR analog to a credit score. High Trust indicates that
a borrower is highly trustable on the network. This means that the borrower’s opinion on vetting
low/no credit customers is highly valuable. As a reward for having high Trust, the borrower will
have access to more capital and better interest rates from lenders. A high Trust score indicates a
low risk profile for that borrower. Borrowers can increase their Trust by paying back loans and by
correctly verifying other borrowers through the Social Staking system. Trust can be determined
by parameter fitting user inputted data such as existing FICO scores, evidence of education, and
any other factor that could have association with an increased likelihood of repaying a debt. In
addition, Trust can be supplemented by Social Stakers.

### V.2 Social Staking
Social Staking is a process through which a borrower can increase his Trust by having other
borrowers stake his position. In the event that the original borrower pays the loan back, Trust
increases for all participating Stakers, and if a borrower defaults, Trust decreases for Stakers. This
creates a system where Stakers are incentivized to accurately assess fellow borrowers.

In the event of a customer without Trust requesting a loan, there are two primary options. The
first is that the customer posts a loan request, and the contract is treated as extremely high risk. In
this situation, the borrower would receive a low amount of cash and high interest. On the lender
side, the lender will post a high collateral fee to the insurance pool, but will also gain high return
on investment from the high interest.

Another option for a customer without Trust is to receive initial verification from borrowers
who have Trust. In this scheme, having a high number of verifiers as well as verifiers with high
Trust Scores will improve the customer’s initial Trust.

## VI. Cryptoeconomics
The cryptoeconomic model for the XOR Protocol provides a framework for a revenue model and
system valuation. We introduce the XOR Value Token (XVT) as the representation of the XOR
Protocol’s value. In addition, we introduce the concept of a stablecoin with which to settle the loan
contracts themselves. In addition, we present the possibility of using atomic swaps so that lenders
and borrowers can use any atomic swappable cryptocurrency. We also describe the interaction
between XVT and governance rights within the XOR Protocol. It is important to note that XVT
and the proposed contract stablecoin are not necessarily the same token, although loans could be
processed with XVT as the currency medium if necessary.

### VI.1 XOR Value Token (XVT)
The XOR Value Token (XVT) represents the net value of the entire XOR Protocol. Because the
XOR Protocol can be built on top of any distributed ledger, XVT’s value encompasses the value of
all of those ledgers’ XOR Protocol layers. This is the model used by most other cryptocurrency
companies, ex. Bitcoin, Ethereum, etc.

The Ethereum Foundation provides most of the inspiration for XVT’s model. As the value of
XOR itself grows, so too will the value of XVT, which can be used in the XOR Protocol in ways
described below. A portion of XVT will be kept aside for the initial members who worked on
XOR. A second portion will be kept for running XOR’s company itself, as a coffer. The rest of the
tokens, the vast majority, will be purchased by investors and system participants.

### VI.2 Contract Stablecoin
Price fluctuations can be extreme in cryptocurrencies. To combat this, some members of the
cryptocurrency community are working on stablecoin implementations. Stablecoins are usually
aggregates of other coins with low price fluctuations, statistically adjusted so as to provide minimum
movement. Makerdao’s stablecoin DAI is pegged against USD at a rate of 1:1. Stablecoins
are important in XOR loan contracts because they provide certainty to a loan. For example, if a
non-stablecoin is used, its value could increase percentage wise beyond the interest rate of the
loan before the lending period is over. In this situation, the lender loses money. Stablecoins can
help to prevent this situation.

### VI.3 Atomic Swaps
Atomic swaps allow for the exchange of two cryptocurrencies using the same hashing algorithm
without requiring a trusted third party, provided that a bridge between the two currencies has
been built. This provides liquidity to cryptocurrency markets and allows for some degree of
equivalency between different currencies. We can employ atomic swaps within XOR so as to
support contracts that exchange different cryptocurrencies. XOR will support other systems of
interoperability beyond atomic swaps.

### VI.4 Token Acquisition and Usage
XVT will be used as the functional currency on XOR. There are several examples of uses of XVT
that provide value to XVT. It is important to note that this list does not encompass all use cases
for XVT.

1. When creating a market, the market creator can receive a portion of transactions or otherwise
generate revenue off the implemented revenue model, as discussed above. To encourage
participants in the market, the market creator can lock some XVT into the insurance pool as
a hedge against his market’s failure. A greater amount of XVT leads to a decreased market
riskiness.
2. Within any type of market, lenders can lock XVT in the insurance pool so as to increase their
voting rights. In general a greater amount of XVT will correspond with greater voting rights,
but this model can be nonlinear and decided upon by the market creator or the voters.
3. Borrowers can lock XVT into the market or a contract as collateral. This essentially allows
for the possibility of secured loans, versus unsecured loans as described in this paper above.
In certain markets, borrowers can also have voting rights.
4. XVT itself can be used as the currency of choice for contracts.
5. For both lenders and borrowers, XVT can be incorporated into the Trust computation. This
is because an actor with a high stake in the XOR system is more likely to be trustworthy.
XVT can also be used to stake others. In this system, a borrower would essentially use his
Social Stakers’ XVT as a staked social collateral for increased Trust.
6. When creating Loan Intents, lenders can lock an amount of XVT as the transfer currency.
This can be extended to the concept of portfolios as well.

### VI.5 Governance
Governance is how choices are made in a system. Examples of governance systems include
unweighted voting, weighted voting, ring voting (where a random subsection of a group is
chosen at the voting), node/supernode (where supernodes have voting powers but nodes vote for
supernodes, much like a Republic), and many other structures. Governance is important to the
XOR Protocol because many of the modular parameters need to be governed by the distributed
user group. XOR’s governance system itself can be modular so as to reflect the most relevant style
for the market and time.

## VII. Identity and Legal Considerations
In order to be able to use the protocol, it is necessary to implement a robust Proof of Identity
system so as to be able to legally reconcile any possible bad acts. Without Proof of Identity, a
financial system is vulnerable to attacks where one user can create multiple identities and increase
his borrowing power.

### VII.1 Proof of Identity
Proof of Identity is a complicated problem that many blockchain companies are attempting to
solve. uPort is a company that is developing an open source and decentralized identity system
on the Ethereum network. uPort works by storing personal keys on your smartphone and uses
a smart contract to lock that information and provide recoverability in the event that a person
loses their key. This is an advantage over traditional public/private key paradigms, where losing
a private key essentially means losing access to the information protected by that key. Other
companies such as Cambridge Blockchain LLC and Civic also have variations on Proof of Identity.
For customers in countries which heavily document their citizens such as the US, simply uploading
a government ID would potentially suffice as Proof of Identification.

It is again important to note that because XOR is designed to be modular, any identity system
can be swapped in or out. For example, in the future, perhaps biometric identifiers will become
the new bank-grade standard. We want to make sure that XOR is flexible enough to handle these
types of situations.

### VII.2 Legal Considerations
Contracts have to be legally reconcilable in order for lenders and borrowers to be able to safely
participate. For example, in the event that a borrower borrows money and tries to disappear, it
has to be possible for lenders to pursue legal action. This requires Proof of Identity as well as a
strong legal protocol.

XOR currently plans to use the OpenLaw protocol to handle automation and reconciliation
of legal contracts. OpenLaw allows for the decentralized and autonomous generation of legal
contracts. It has flexible functionality, including cross-border functionality where lenders and
borrowers from different countries can select the appropriate jurisdiction. Combined with blockhain
notarizing and Proof of Identity, XOR will be able to provide a framework for customers
to assess and reconcile legal issues. The OpenLaw contract can be encapsulated within the
lending/borrowing contract itself.
