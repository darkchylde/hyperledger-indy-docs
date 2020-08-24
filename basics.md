
# Basics

Indy ledger is **public permissioned**. Anyone who wants to publish DID(s) needs to get the role of **TRUST ANCHOR** on the ledger.


1. Identity records (to describe ledger entity)
	a. Public data for e.g. public keys, service endpoints, credential schema and definitions
	b. Associated with *one* DID i.e. globally unique and resolvable using ledger
	c. Identity owner can own multiple DIDs (to maintain privacy but how ?)

## Types of DID(s)

1. Verinym
	a. Associated with legal identity of the identity owner. for e.g. DID of government entity
2. Pseudonym
	a. Blinded identifier used to maintain privacy in the context of ongoing digital relationship (connection)
	b. If the Psuedonym is used to maintain only one digital relationship we will call it a *Pairwise-Unique* Identifier.
	c. **Pairwise-Unique identifiers can be used to maintain secure connections between actors** (PEER DID DIF(decentralised identity foundation) SPEC)


## Types of transactions

1. **NYM**
	a. Creation of DID known to the ledger
	b. Rotation of verification keys
	c. Setting and changing of roles
	d. Some of the important fields in a NYM transaction records are `dest` (target DID), `role` (role of the user NYM record being created for) and `verkey` (target verification key)


*Note*: There [multiple supported transactions][3] in a ledger. Categorised as WRITE transactions and READ transactions.

## Verification key (For verifying the signature (Authenticity check))

Publishing with a DID verification key allows a person, organisation or thing, to verify that someone owns this DID as that person, organisation or thing is the only one who knows the corresponding signing key and any DID related operations requiring signing with this key.

## Roles

1. **TRUST_ANCHOR**
	a. Has ability to write DID(s) to the ledger
	b. TRUST_ANCHOR is a person or organisation **that ledger already knows about**
	c. This person or organisation can now help others to bootstrap (Publish DID for others)
	d. Something equivalent to a **FACILITATOR**

*Note*: Therer are multiple [roles][4] involved in indy.


[1]: https://hyperledger-indy.readthedocs.io/projects/sdk/en/latest/docs/getting-started/indy-walkthrough.html
[2]: https://identity.foundation/peer-did-method-spec/
[3]: https://github.com/hyperledger/indy-node/blob/master/docs/source/requests.md (Type of transactions in indy)
[4]: https://github.com/hyperledger/indy-node/blob/master/docs/source/auth_rules.md (Roles in indy)