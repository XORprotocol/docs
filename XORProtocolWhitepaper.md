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
### 1. Background
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

### 2. Solution
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
