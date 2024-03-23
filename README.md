# MICS PROCOTOL DOCUMENTATION

Massively Improving Cryptocurrency Storage Security

***

## SUMMARY

The MICS protocol makes it extremely difficult for a thief to steal cryptocurrency (including NFTs) from a wallet. MICS works by inverting the asymmetry of the effort required to maintain security versus the effort required to break security.

MICS makes the thief pay the wallet owner for the owner's poor security, and pay the owner to eventually withdraw and secure the cryptocurrency.

MICS lets the owner indefinitely delay theft attempts, while preparing to withdraw all the cryptocurrency.

<br/>

## INTRODUCTION

The MICS protocol is designed to massively improve cryptocurrency storage security by creating a vault in which cryptocurrency (including NFTs) can be deposited without restrictions, but from which it can be withdrawn only with a time delay and other restrictions.

MICS can be implemented through a smart contract, for any blockchain.

Time delayed access is an old idea, used even in early physical vaults, but MICS has extra features which make vaults far more practical than simple time-delayed vaults.

MICS works for cryptocurrencies, where there are no physical identities and no central authority that can verify identities and arbiter potential security breaches. MICS doesn't require a central authority to stop unauthorized withdraw requests, and provides a level of security far above that of an identity-based central authority.

Cryptocurrency storage security is a hard problem to solve because security is an asymmetric problem, that is, it's much easier to break security than to maintain security. Breaking security requires finding just one weak point for intrusion, whereas maintaining security requires removing all weak points.

MICS works by inverting the asymmetry of the effort required to maintain security versus the effort required to break security. This is done by letting the owner indefinitely delay theft attempts, while preparing to withdraw all the cryptocurrency. This makes it extremely difficult to steal cryptocurrency when a private key is compromised.

MICS works because it gives the owner of a vault a long time during which to detect unauthorized withdraws, and can indefinitely block a thief's access to the cryptocurrency. In the meantime, the owner has several options to withdraw all the cryptocurrency from the vault.

The design is as simple as it can be, while still able to handle multiple use-cases. If extra complexity is required, it's recommended to create and deploy custom smart contracts which are very specific. Adding complexity in a general smart contract would make it extremely difficult for people to understand how to secure their cryptocurrency. Extra complexity could mean having multiple owners, witnesses, inheritors and custodians.

In some use-cases, MICS provides more practical security than multisig.

To make MICS usable by the public at large, a UI wizard should use strict question-answer steps to guide the user to create a vault which is specifically configured for the user's context, like: single user with / without inheritor, family with shared ownership of cryptocurrency and with / without children, company with multiple people who can withdraw cryptocurrency and have to be tracked independently.

<br/>

## INVERTING SECURITY ASYMMETRY

The MICS protocol makes it extremely difficult for a thief to steal cryptocurrency (including NFTs) from a wallet. MICS works by inverting the asymmetry of the effort required to maintain security versus the effort required to break security.

MICS makes the thief pay the wallet owner for the owner's poor security, and pay the owner to eventually withdraw and secure the cryptocurrency.

MICS lets the owner indefinitely delay theft attempts, while preparing to withdraw all the cryptocurrency.

MICS lowers the cost of securing cryptocurrency to the cost of stealing cryptocurrency. Even though breaking security still requires finding just one weak point for intrusion, maintaining security no longer requires removing all weak points.

The owner of a vault has a long time during which to detect unauthorized withdraws, and can indefinitely block a thief's access to the cryptocurrency.

Even if all the private keys are compromised, and the owner can't withdraw the cryptocurrency from the vault, the thief can't do that either.

On top of this, there are upfront costs that the thief has to pay, which eventually make any theft attempt more costly than securing the cryptocurrency.

The thief has to organize a mass-theft operation, to try to steal a lot of cryptocurrency, in order to make the upfront costs worth it. The thief has to also spend time constantly making claim requests in most theft attempts because most owners would detect the unauthorized withdraws and override them.

Interacting with a smart contract usually costs gas, and this means that the thief has to spend gas for every withdraw and claim request made. While it's true that the owner has to do the same in order to override the requests of the thief, the thief has to do that for the entire mass-theft operation.

The claim cost (from the vault configuration) makes the upfront costs higher. The smart contract stores a claim request only if an amount of cryptocurrency equal with the claim cost is paid to the smart contract. This cryptocurrency is deposited in the vault and is transferred with the rest of the cryptocurrency. The entity which is able to withdraw the cryptocurrency from the vault also gets the claim cost paid by other entity.

The claim cost makes the upfront cost of trying to steal cryptocurrency much higher than the cost of securing cryptocurrency by making the thief waste money at every theft attempt of the mass-theft operation (whereas the owner wastes money only for one vault).

Consider a scenario where the owner private key of the vault gets compromised. The thief signs a withdraw request to withdraw all the cryptocurrency from the vault. The owner signs a claim request for the owner key, blocking all withdraws. At this point the thief has two options.

One option is to stop trying to steal the cryptocurrency, which means that the owner will get all the cryptocurrency.

The other option is to continue trying to steal the cryptocurrency, which means paying the claim cost for each new claim request. In turn, the owner signs claim requests to override each claim request of the thief. This reciprocal overriding can continue indefinitely, and neither the thief nor the owner get the cryptocurrency. Both the thief and the owner have to keep paying the claim cost.

The owner can simply wait for more cryptocurrency (from the claim cost paid by the thief) to accumulate in the vault. Once the owner is satisfied with the cost paid by the thief, or when the thief can no longer afford to pay the claim cost of the mass-theft operation, the owner signs a claim request for the witness, inheritor or custodian key and withdraws all the cryptocurrency from the vault.

If the thief were to focus stealing from average people, there wouldn't be much cryptocurrency to steal in any single successful attempt, and those people can afford to keep overriding the thief's claim requests indefinitely (since they have a constant wage).

If the thief were to focus stealing from rich people whose vaults contain millions of dollars and have a claim cost of thousands of dollars, a mass-theft operation with just a few thousand of repeated claim requests would cost the thief millions of dollars in upfront costs. If the thief is successful in one theft attempt, it's possible that the stolen cryptocurrency wouldn't cover the paid claim costs for the entire mass-theft operation.

A vault can be configured with a percentage with which the claim cost rises after every claim request is stored by the smart contract, increase relative to the previous claim cost. This makes stealing the cryptocurrency more and more expensive with every claim request, and a mass-theft operation becomes exponentially more expensive. Care should be taken when configuring this percentage since the claim cost also increases for the owner. To mitigate the rising cost for the owner, the smart contract can be configured to accept the initial claim cost when storing claim requests signed for the witness, inheritor or custodian key.

If the value of the cryptocurrency rises in time, the claim cost also rises (relative to a stable coin), so the upfront cost of trying to steal cryptocurrency increases. The owner has to be aware of this, and, if this cost becomes too high, the owner has to move the cryptocurrency in another vault which is configured with a lower claim cost.

This completes the inversion of the asymmetry of the effort required to maintain security versus the effort required to break security.

<br/>

## MONITORING PENDING REQUESTS

The smart contract publishes all the pending requests which are executed with a time delay. This allows the owner to take measures to safeguard the cryptocurrency, if a request is unauthorized.

The owner can use a third-party monitoring service which notifies subscribers if there is any pending request for a vault. If the owner doesn't recognize a request, it means that the request is unauthorized, so the owner has to take measures to safeguard the cryptocurrency, like cancel withdraw requests, or override claim requests.

A third-party monitoring service can be compromised, so the owners can use multiple monitoring services, or can monitor the blockchain directly.

<br/>

## VAULTS

A smart contract creates a vault in which cryptocurrency can be deposited without restrictions, but from which it can be withdrawn only with restrictions.

When the vault is created, it can be configured with the following data:

* **Vault name**: The name of the vault. This isn't unique within a blockchain. This is public information, so it shouldn't contain private information. The smart contract accepts a deposit in the vault only if the request includes the vault name. If this behavior isn't directly possible, the smart contract can implement an extra endpoint to check whether the vault name is correct, check which has to be made before a deposit is made. The purpose of the vault name is to avoid mistaken deposits from vault to vault.

* **Maximum pending requests**: The maximum number of pending withdraw requests. A practical default value would be 20.

* **Claim cost token ID**: The token ID of the cryptocurrency which has to be paid as claim cost, that is, has to be paid to the smart contract in order to store a claim request.

* **Claim cost**: Amount of cryptocurrency which has to be paid to the smart contract in order to store a claim request. This cryptocurrency is deposited in the vault and is transferred with the rest of the cryptocurrency. A practical value would be the owner's income for 1 productive / working hour. A percentage (from the stored cryptocurrency) doesn't work here if the vault contains mostly tokens other than the claim cost token ID (like NFTs), since the distribution of the value of the tokens, relative to each other, isn't known to the smart contract.

* **Claim cost raise**: A percentage with which the claim cost rises after every claim request is stored by the smart contract, increase relative to the previous claim cost. This makes stealing the cryptocurrency more and more expensive with every claim request, and a mass-theft operation becomes exponentially more expensive. Care should be taken when configuring this percentage since the claim cost also increases for the owner.

* **Apply claim cost raise only to owner**: If this is true, the smart contract accepts the initial claim cost when storing claim requests signed for the witness, inheritor or custodian key.

* **Owner key**: A public key. Most of the requests which are processed by the vault must be signed for the owner key.

* **Spender keys**: A list of public keys; may miss. The number of keys must be strictly smaller than the maximum pending requests; one spot is intended for the owner. The associated spender private keys should be under the control of the employees of a company, or of the members of a family, and should be stored separately from the owner private key in order to reduce the probability that the private keys would be compromised together. Only withdraw and cancel withdraw requests may be signed for this key.

* **Witness key**: A public key; may miss. The associated private key should be under the control of the owner, and should be stored separately from the owner private key in order to reduce the probability that the private keys would be compromised together. The witness private key can be stored by several custodians which are semi-trusted. Only claim requests may be signed for this key, requests which (upon a time-delayed execution) would transfer all the cryptocurrency from the vault to the address requested by the witness.

* **Owner time delay**: The time delay (in days) after which withdraw and claim requests signed for the owner or witness key are executed, delay starting from the moment the requests are stored by the smart contract. This allows the owner to take measures to safeguard the cryptocurrency, if a request is unauthorized. This must be at least 2 days. A practical default value would be 30 days.

* **Inheritor key**: A public key; may miss. The associated private key should be under the control of an inheritor of the owner. The inheritor private key can be stored by several custodians which are semi-trusted. Only claim requests may be signed for this key, requests which (upon a time-delayed execution) would transfer all the cryptocurrency from the vault to the address requested by the inheritor.

* **Inheritor time delay**: The time delay (in days) after which claim requests signed for the inheritor key are executed, delay starting from the moment the requests are stored by the smart contract. This must be higher than twice the owner time delay. This must be at least 30 days. A practical default value would be 360 days.

* **Custodian key**: A public key; may miss. The associated private key should be under the control of a custodian which acts on the behalf of the owner. The custodian should be an independent arbiter, and its private key should not be known to the owner. Only claim requests may be signed for this key, requests which (upon a time-delayed execution) would transfer all the cryptocurrency from the vault to the address requested by the custodian.

* **Custodian time delay**: The time delay (in days) after which claim requests signed for the custodian key are executed, delay starting from the moment the requests are stored by the smart contract. This must be higher than the owner time delay plus the inheritor time delay. This must be at least 60 days. A practical default value would be 400 days.

For security reasons, the vault configuration must never change. If the configuration has to be changed, a new vault has to be created and the cryptocurrency has to be transferred from the old vault to the new vault.

<br/>

## REQUEST SUMMARY

The smart contract exposes endpoints which accept the following requests: create vault, read vault configuration, deposit, withdraw, cancel withdraw, read pending withdraws, claim, read pending claims.

MICS requires a smart contract which can execute some actions (= the pending requests) automatically. If this isn't possible, the execution of a pending request could be triggered manually with another request (which is sent to the smart contract once the time delay passes for the pending request).

<br/>

## ADMINISTRATIVE REQUESTS

The following administrative requests are available:

* **Create vault**: Creates a vault with its configuration.

* **Read vault configuration**. Reads the vault configuration.

These requests must be signed for the owner key in order to be processed by the smart contract.

To be sure that MICS works for a new vault, a secure device must be used to generate the owner private key, and to sign the create vault request.

If it's not certain whether the device is secure, or to maximize security, other secure devices can be used to read the vault configuration and compare it with the configuration that it should have. If the configurations are the same and at least one of the used devices was secure, the vault is guaranteed to be secure even if the other devices are compromised, and MICS works as intended even if the owner private key was compromised from the start.

Important note: MICS protects a vault, but can't protect a user's perception from being subverted by a thief. For example, a thief could compromise the device of a user to such an extent that the user would see some data on the screen, but the device would send different data to the smart contract, which could mean that the vault itself could be configured with the thief's keys. This means that the user could believe that in the future he would be able to sign claim requests for his witness key, but in reality the vault would use a different witness key (which is known only to the thief). This is why it's necessary for at least one of the used devices to be secure.

<br/>

## WITHDRAW REQUESTS

The vault stores a queue with pending withdraw requests. The maximum number of requests is equal with the vault's configured maximum pending requests.

A withdraw request may be stored by the smart contract in the queue only if it's signed for the owner key or for a spender key. Once the queue is full, no further request may be stored.

A withdraw request contains a destination address where the cryptocurrency has to be transferred when the request is executed.

A pending request is executed with a delay from the time when it was stored. The delay is the owner time delay. This means that the smart contract transfers the requested cryptocurrency amount to the requested destination address only after the owner time delay passes since the request was stored.

Pending withdraw requests may not be executed if there is any pending claim request; claim requests have a higher priority.

<br/>

## CANCEL WITHDRAW REQUESTS

A pending withdraw request can be canceled with a cancel withdraw request which is signed for the owner key or for a spender key. This allows the owner and the spenders to indefinitely block any theft attempt made with withdraw requests.

If a thief makes a withdraw request, the owner and the spenders have the owner time delay period to detect and cancel the request, in which case the thief would not be able to steal the cryptocurrency.

However, the thief could make another withdraw request, the owner can cancel that as well, and so on in a cat-and-mouse game.

The owner can, in turn, make withdraw requests that the thief could cancel. This means that neither the owner nor the thief can get the cryptocurrency.

So, while the thief can't actually steal the cryptocurrency, the owner can't use it either. Not ideal, but better than powerlessly watching the cryptocurrency being stolen. In some cases this impasse might be solved by catching the thief, but this is usually unlikely to happen.

This impasse can be solved with claim requests.

<br/>

## CLAIM REQUESTS

Claim requests can transfer all the cryptocurrency from the vault to another address, when the owner private key was compromised and a thief is actively trying to use the owner private key to withdraw cryptocurrency from the vault.

A claim request contains a destination address where all the cryptocurrency from the vault has to be transferred when the request is executed.

A claim request is executed with a delay from the time when it was stored by the smart contract, which means that the cryptocurrency is transferred to the requested destination address only after the appropriate time delay passes since the request was stored.

The smart contract has 1 slot for each public key with which it can be configured: owner, witness, inheritor, custodian. When the smart contract receives a claim request, it verifies its signature and it stores the request in the slot which is associated to the public key for which the request was signed, within certain rules, possibly overriding the existing request, and later (with a time delay) executes the request within certain rules. A request which is stored in a slot is known as a pending claim request.

Pending withdraw requests may not be executed if there is any pending claim request; claim requests have a higher priority.

The rules of the claim requests are the secret sauce of MICS because they allow the owner to indefinitely block any theft attempt made with withdraw and claim requests. The rules, per slot, are:

* **Owner slot**: A request may be stored in this slot only if the witness slot is empty, or the witness slot has a pending request for the same destination address (as the request). The request stored in this slot is executed with the owner time delay from the moment it was stored, only if the witness slot is empty.

* **Witness slot**: A request may be stored in this slot without restrictions. The request stored in this slot is executed with the owner time delay from the moment it was stored, only if the owner slot has a pending request for the same destination address. This means that a rogue witness can't steal the cryptocurrency without the owner's confirmation / signature. It's fine to store the witness private key in custody so long as the owner private key isn't known to the custodian.

* **Inheritor slot**: A request may be stored in this slot without restrictions. The request stored in this slot is executed with the inheritor time delay from the moment it was stored. Since the execution time delay is much higher than that of a request stored in the owner and witness slots, a rogue inheritor can't steal the cryptocurrency without the owner noticing and withdrawing the cryptocurrency before the inheritor's request is executed.

* **Custodian slot**: A request may be stored in this slot without restrictions. The request stored in this slot is executed with the custodian time delay from the moment it was stored. Since the execution time delay is much higher than that of a request stored in the owner, witness and inheritor slots, a rogue custodian can't steal the cryptocurrency without the owner noticing and withdrawing the cryptocurrency before the custodian's request is executed.

Claim requests can be overridden, but there is no specific request to cancel them. If desired, it's safe to cancel a claim request which was signed for the same key as the cancel claim request; this can be done with another claim request whose destination address is that of the (sender) vault.

The owner and the witness slot rules are designed so that if the owner and the witness private keys are compromised, a thief wouldn't be able to steal the cryptocurrency.

If a thief were to get access only to the owner private key, both the owner and the thief would be able to use the owner private key to sign withdraw and claim requests. In this case, the owner could use another (secure) device and sign a claim request with the witness private key. So long as the witness private key isn't compromised, only the owner can sign claim requests with it.

If a thief were to get access only to the witness private key, it wouldn't be of any use because a claim request would be executed only if the owner private key were to sign a claim request for the same destination address.

If a thief were to get access to both the owner and the witness private keys, the thief would be able to indefinitely block the owner's access to the cryptocurrency. This is why the inheritor and custodian keys exist.

The inheritor and custodian can make claim requests independently from the owner so that they can act when the owner is unable to sign a claim request (for example in case of a coma or death). However, the execution time delay of their claim requests is much longer so as to allow the (able) owner to take measures to safeguard the cryptocurrency, if an unauthorized request is made by a rogue inheritor or custodian.

If a thief were to get access to both the owner and the witness private keys, and the owner would be unable to indefinitely block the thief's claim requests, the inheritor and the custodian wouldn't be able to access the cryptocurrency before the thief.

This works because each claim request signed by the owner and the thief, indefinitely overriding each other's claim requests, gets a store time (call it T) newer than the overridden claim request, so T gets higher and higher. In the meantime, the claim request signed by the inheritor or the custodian remains pending with the same store time (call it V), and at some point V will come before T and the inheritor's / custodian's claim request will be executed.

<br/>

## CLAIM COST DISTRIBUTION

The smart contract stores a claim request only if an amount of cryptocurrency equal with the claim cost is paid to the smart contract. This cryptocurrency can be distributed in one of the following ways:

* **Deposited in the vault** (default behavior). The cryptocurrency is deposited in the vault and is transferred with the rest of the cryptocurrency. The entity whose claim request is executed, be it the owner or the thief, will also get the claim cost paid by other entity. The other entity will always lose money.

* **Burnt**. Both entities which pay the claim cost will lose money, no matter whose claim request is executed. At some point, the loss incurred from the total paid claim costs will dwarf the cryptocurrency from the vault.

* **Dropped to all the vaults** (from the blockchain). The claim cost which is dropped to a vault is proportional with the amount of cryptocurrency stored by the vault, only the amount of the claim cost token.

* **Dropped to all the stakers** (from the blockchain). The claim cost which is dropped to a staker is proportional with the amount of cryptocurrency staked by the staker.

* **Transferred to the developer** of the smart contract. This is a conflict of interests, so it should never be implemented.

* **Split in half**. One half of the cryptocurrency should be distributed in one of the above ways, the other half should be distributed in another way. If half of the cryptocurrency is deposited in the vault, and half isn't, the entity whose claim request is executed, be it the owner or the thief, will also get half of the claim cost paid by other entity, so (on average) the entity whose claim request is executed doesn't lose money.

<br/>

## VAULT CASCADES

Entities which are at a high risk of being compromised (perhaps because they protect large amounts of cryptocurrency) can mitigate the risk of being fully compromised by setting up a cascade of vaults. The owner private key of each vault could have an increased level of security.

The last vault from the cascade, which has no configured inheritor and custodian keys, is called last resort custodian. This custodian acts as a last resort catch-all, identity based, centralized entity, and can afford to use the ultimate level of physical security (like signing claim requests only offline).

So long as any single vault from the cascade is not compromised, the cryptocurrency which is transferred to it is safe because it stops in that vault and is accessible only to the owner.

If the entire cascade of vaults is compromised, the cryptocurrency will not be accessible by the owner, and the only thing left to do is to stop the thief from signing claim requests. If the last resort custodian protects the world's cryptocurrency reserves and is somehow compromised, there will be nowhere for the thief to hide, and the only thing the thief could do in the meantime is to delay the ability of the last resort custodian to access the cryptocurrency.

<br/>

## INHERITANCE

MICS works for families, even in the case of death of both spouses, making unnecessary any extra recovery protocol in case of death.

Two spouses who want to be able to spend and inherit cryptocurrency as a family should create two vaults. Each vault's inheritor key should be the other vault's owner key. The cryptocurrency should be stored in one vault, while the other vault should be used only to claim the cryptocurrency from the first vault, in case the first vault was compromised.

Both spouses should have access to the owner, witness and inheritor private keys of both vaults in order to be able to easily withdraw cryptocurrency in case of emergency or death, and to be able to cancel the withdraw requests made by the other spouse or by a thief (if the owner private key is compromised), and to be able to override the claim requests made by the other spouse or by a thief (if the owner private key is compromised).

If the cryptocurrency belongs to only one spouse, only that spouse should know the witness private key. If the other spouse were to sign a claim request for the owner or inheritor key, the witness private key allows the spouse who owns the cryptocurrency to override the claim request.

The custodian key can be configured with owner key of (the vault of) a custodian which is trusted by both spouses. The custodian should be an independent arbiter, and its private key should not be known to the spouses. The custodian can intervene if there is any dispute between the spouses, and, in the meantime, the spouses override each other's claim requests indefinitely.

If the witness private key is known to both spouses, they can override each other's claim requests. However, the inheritor would be able to make a claim request and withdraw all the cryptocurrency. If the inheritor private key is also known to both spouses, they can again override each other's claim requests. However, the custodian would be able to make a claim request and withdraw all the cryptocurrency while the spouses override each other's claim requests.

The spender keys can be the owner keys of (the vaults of) the children of the family. In the case of death of both spouses, the children could sign withdraw requests for the spender keys, for mutually agreed amounts of cryptocurrency. If the children don't agree on the amount, they can indefinitely cancel each other's withdraw requests until the inheritor or custodian intervenes with a claim request.

<br/>

## REPLACING MULTISIG

In some use-cases, MICS provides more practical security than multisig.

In MICS, only the owner private key is required to access the cryptocurrency. In the case of multisig, if the threshold of signatures / keys isn't met (for example 3 out of 5) because one of the participants died or went rogue, the cryptocurrency remains inaccessible.

MICS can simulate the way of working of multisig, but inverted. For example, the owner and the witness private keys, and a spender private key, can be given to all the members of the group which owns the vault. It's important that each member of this group doesn't store both private keys on the same device which can be compromised.

Any one member of the group can sign a withdraw request, but can also cancel any withdraw requests, and can override any claim requests. This means that if any member of the group goes rogue, any other member of the group can cancel / override the withdraw and claim requests made by the rogue member.

So long as the identities of all the members of the group are know to the group, it should be possible to track down the rogue member. Still, the rogue member could make the private keys public, in which case anyone in the world could make withdraw and claim requests, which means that the group will have to cancel / override them indefinitely, or sign a claim request with the inheritor or custodian key.

<br/>

## REMAINING RISKS

If the owner and the witness private keys were compromised, a thief would be able to override all the claim requests made by the owner, making the cryptocurrency inaccessible to the owner, unless the inheritor or custodian were to make a claim request.

If a thief were to get access to both the owner and the witness private keys, and were able to make the owner lose access to the witness private key (which is possible in the case of a custodian which stores the witness private key), the thief would be able to sign a claim request and steal all the cryptocurrency from the vault (because the owner wouldn't be able to override the claim request in the absence of the witness private key). The solution is to store that private key with multiple custodians.

If a thief were to get access to both the owner and the witness private keys, and the owner would be unable to indefinitely block the thief's claim requests, the inheritor and the custodian wouldn't be able to access the cryptocurrency before the thief.

The custodian's claim requests have the lowest priority in order to mitigate the possibility that the custodian would collude with the government to steal the cryptocurrency based on an unjust or corrupt bureaucratic decision instead of a court order. However, if the owner or the inheritor were unable to sign a claim request (to withdraw the cryptocurrency) before the claim request of the custodian is executed (actually with the owner time delay before execution), the owner / inheritor would lose the cryptocurrency. This is why the custodian time delay must be very high.

<br/>

## RECOMMENDATIONS

The owner private key should not be stored with a custodian.

When a private key is stored with a custodian, especially the witness private key, it should be stored with multiple custodians. This way, if any custodian blocks the access to the private key, the key may be accessible from another custodian.

<br/>

## AUTHOR

The MICS protocol was designed by [voidsculptor.art](https://voidsculptor.art), timestamped (with DigiStamp) and published at 2024.03.19. The protocol is released in the public domain.

For long-term public comments, MICS can be found on [GitHub](https://github.com/voidsculptorart/mics/).

***
