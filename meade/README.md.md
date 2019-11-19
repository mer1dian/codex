# Gateway
0.8.2

[www.freighttrust.com](www.freighttrust.com)




## Outline

* Base Client 
* Drag and drop a file to load it
* Ctrl/Cmd + S to save the source file
* Support Github Flavored Markdown syntax
* Support many languages highlight in editor and preview mode

## Legal Notice


```markdown
* BSD-3-Clause License 
We also re-distribute other licenses including GPLv2, packages are identified in their respective directory with flag, 'GPL2-,APACHE-,...` 

Please read our Contributers License Agreement for contributions consiting more than 5 commits, or are otherwise "substantive in material effort" i.e. patenable work.

This software may contain export restricted cryptographic work, and as such may not be available legally in your jurisidiction 


"FREIGHT TRUST & CLEARING CORPORATION"

```

## Contact

https://freighttrust.com

https://t.me/freighttrust 

https://twitter.com/freighttrustnet

admin@freighttrust.com

### keys.openpgp.org
 

 admin@freighttrust.com  8B9B067C295049CA784D68F1995F1C84DCED4D6A 


## Table of Contents

* Network Summary
* Network resources (soft & hard)
* Network interaction
* Network scaling 
* Sources & Appendix



Network Topology & Design

#### Defining Mechanics and Principles of Network

> PRINCIPLE OF MAXIMAL AUTONOMY: The purpose of a planning
network is to provide tools for local planning, rather than
primarily to provide  centralized control of the planning at
different nodes. 

> PRINCIPLE OF REDUNDANCY OF POTENTIAL COMMAND: Power resides
where information resides.
 
> PRINCIPLE OF EVENTS OF LOW PROBABILITY....the fundamental purpose
of a system should not be jeopardized, nor its fundamental
objectives significantly compromised, in order to accommodate
events of extremely low probability

> LAW OF REGULATORY MODELS....every good regulator of a system must
be (contain) a model of that system.  



#### Geoproximity Routing (Traffic Flow Only)
Geoproximity routing lets Amazon Route 53 route traffic to your resources based on the geographic location of your users and your resources. You can also optionally choose to route more traffic or less to a given resource by specifying a value, known as a bias. A bias expands or shrinks the size of the geographic region from which traffic is routed to a resource.

To use geoproximity routing, you must use Route 53 traffic flow. You create geoproximity rules for your resources and specify one of the following values for each rule:

* If you're using AWS resources, the AWS Region that you created the resource in

* If you're using non-AWS resources, the latitude and longitude of the resource

To optionally change the size of the geographic region from which Route 53 routes traffic to a resource, specify the applicable value for the bias:

To expand the size of the geographic region from which Route 53 routes traffic to a resource, specify a positive integer from 1 to 99 for the bias. Route 53 shrinks the size of adjacent regions.

To shrink the size of the geographic region from which Route 53 routes traffic to a resource, specify a negative bias of -1 to -99. Route 53 expands the size of adjacent regions.

The following map shows four AWS Regions (numbered 1 through 4) and a location in Johannesburg, South Africa that is specified by latitude and longitude. [docs.aws.amazon.com](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html#routing-policy-geo)

[image](./dns-map-aws.png)

DNS Records 

NAPTR & DDDS
NAPTR Record Type
A Name Authority Pointer (NAPTR) is a type of record that is used by Dynamic Delegation Discovery System (DDDS) applications to convert one value to another or to replace one value with another. For example, one common use is to convert phone numbers into SIP URIs.

The Value element for an NAPTR record consists of six space-separated values:

Order
Preference
Flags
Service 
Regexp
Replacement

DDDS: Enabling Barcode to Wallet Address 
[RFC 3404](https://tools.ietf.org/html/rfc3404#section-4.4)


Certificate Authority and CAA

##### Network Rewards and Incentives

formula: 



The “base” (ie. uncle rate of a 0-gas block) is consistently ~6.7%
## 2.0 Installing


### Setting up client 

Step one: 

SSH into AWS/GCP account


Downloads 
```
General availability client: RHEL/CentOS 7.4-7.7
disallowed: other distros (no ubuntu). 

Reference Build Vanilla 
http://linuxsoft.cern.ch/cern/centos/7/rt/CentOS-RT.repo

```
#### 

 - [ ] java
 - [ ] node.js
 - [ ] virtual box
 - [ ] docker
 - [ ] lxc
 - [ ] rust
 - [ ] mosh
 - [ ] 
 - [ ] wget/curl/zsh
 - [ ] &&
 - [ ] &&&

prep terminal
ssh into instance on aws / gcp


##### 1. prep terminal 

$ sudo dnf install mosh

```
$ cd /etc/yum.repos.d
wget http://download.virtualbox.org/virtualbox/rpm/rhel/virtualbox.repo
```

##### 2. Install docker & docker-machine

```
$ install  docker-ce & docker-machine
base=https://raw.githubusercontent.com/docker/machine/v0.16.0
for i in docker-machine-prompt.bash docker-machine-wrapper.bash docker-machine.bash
do
```
```
$ sudo wget "$base/contrib/completion/bash/${i}" -P /etc/bash_completion.d
done 
```


<br>

⚠️  Issue with cgroup while installing docker? try: 
```
$ sudo yum install cgroup-lite
```


##### 3. Install node/npm
```
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.1/install.sh | bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

##### 4. Install  oracle JavaVM 13.0.1 
This is a link to our S3 Bucket, if you can not access it please use Oracles Website to download it.

*Please use at least 11.0.5 Oracle JVM/JDK for optimal performance*
```
$ yum install -y https://maidenlane.s3.amazonaws.com/jdk-13.0.1_linux-x64_bin.rpm(https://maidenlane.s3.amazonaws.com/jdk-13.0.1_linux-x64_bin.rpm)
```


##### 6. Download Hyperledger Besu Client base image 
```
$ docker pull hyperledger/besu:latest (1.3.5-SNAPSHOT)

```


##### 5. Start Client
```
$ bin/besu
```



##### 6. Import private key from initial validator genesis 
Your Private Key is tied to your Ethereum Foundation (Ethereum Main Network) Wallet Address. 
```
$ mv 0x1234ABCD.key /user/install-dir/besu/config
```
##### 7. Import private key from initial validator genesis 
```
$ ./inspect.sh // self-check to make sure configured properly
$ ./gateway.sh // connect to network
```
..

(Placeholder)

.

####Footnotes;

recommended fusion/baseimage

[https://hub.docker.com/r/phusion/baseimage/](https://hub.docker.com/r/phusion/baseimage/)

🚧 Construction Zone 🚧 
<br> Network Users Section

### Freight Trust Protocol - BOL Protocol
This document describes the architecture and system design of a decentralized multi-cast protocol to enable legal (both contractual and property) transfer of instrumitized documentation, i.e. documents of title. BOL is designed to enable users to create, agree to, and manage documents pertaining to the supply chain industry,
without needing to rely on a physical paper document trail while still retaining all the legal qualities of a physical bearer instrument. It is in that respect to physicality, legality and extensiability that the protocol offers a robust and provable use case to industry participants versues other existing/developing solutions. 

BOL Protocol is licsneded under the BSD 3-Clause Open Source Software license. A more permissive Apache 2.0 License is available upon request. BOL does not require any other open source licenses for it to work, that is to say it does not contain any other software that utilizes a different licesnesing regime, such as GPLv2. 

# [#Definitions](#Glossary



* x509
* EIP-211 (not for publishing yet)


# Design, Architecture and Optimization

#

To a lawyer, a legal contract has a distinct meaning:

```
A contract is an agreement giving rise to obligations which are enforced or recognised by law. The
factor which distinguishes contractual from other legal obligations is that they are based on the
agreement of the contracting parties7.
For a contract to be valid, legal systems will impose certain requirements. Under English law, there
are four key elements that must (usually) be satisfied: 


(i) one of the contracting parties must make an offer to contract and the other(s)must accept that offer;
(ii) there must be ‘consideration’ for the
offer, this being some form of value that must be exchanged; 
(iii) the parties must have an intention
to form legal relations; and 
(iv) there must be certainty as to terms of the contract. 


*source* ISDA - "Smart Contracts and Distributed Ledger: A Legal Perspective"
```

Other systems of law may have other requirements – for example, under New York law, many legal contracts must be in writing and signed to become binding. Or in China where the color of the ink must be black: red or blue ink makes the signature inadmissiable. For our purposes, we will only consider the *de facto*, that is to say British Common Law for Maritime and the United States Unified Commerical Code (UCC). 


**Architectural Design**


### Functional and legal equiviliance provisions for dematerilizing shipping documents or any other bearer instrument with negotiable optionaliy

Visually replicate paper bills, preserving the often industry / custom specific layout;

> a. Replicate the function of paper bills, including a party’s ability to issue, indorse, recut or surrender the e-bill;
>
> b. Replicate the physical transfer of paper bills and, whilst all parties can view an e-bill \(in copy form\), the trading platform restricts access and indorsement to the current lawful holder \(by way of fob and access code\) as the e-bills securely move from one party to the next; and
>
> c. Can be converted into paper bills, allowing them to be finally traded with parties which have not signed up to the ETS platform. However, it is notable that paper bills cannot be converted into e-bills since none of the ETS would be prepared to investigate and effectively warrant the provenance of paper bills and the physical cargo they represent.


In designing a comprehesnvie *organism* (in the biological sense: a self regulating autonomous network is what we are striving to achieve) certain realities of business must be acknowledged. Wheres these  four principles appear to be desirable and should insofar as it is possible be pursued together in achieving our goals and more broadly the "user experience":

1. the promotion of certainty and predictability; 
2. the promotion of uniformity of application;
3. the protection of democratic ideals andensuring of jurisprudential deliberation, 
4. the retention of efficiency.


## Systems Based approach

Often when two companies deal with each other in the course of business, they will use standard form contracts. Often these standard forms contain terms which conflict \(e.g. both parties include a liability waiver in their form\). The 'battle of the forms' refers to the resulting legal dispute arising where both parties accept that a legally binding contract exists, but disagree about whose standard terms apply. Such disputes may be resolved by reference to the 'last document rule', i.e. whichever business sent the last document, or 'fired the last shot' \(often the seller's delivery note\) is held to have issued the final offer and the buyer's organisation is held to have accepted the offer by signing the delivery note or simply accepting and using the delivered goods.

<!> Two Modes: National and International

| Contract Function | Parties |
| :--- | :--- |
| Master Covenant | Mandatory, All Network Participants |
| RuleBook Agreement | Mandatory, All Commerical Orgs. |
| Master Participation Agreement | Mandatory for B2B |
| Network Operator Agreement | Mandatory for Node Operators |
| Transactional Clauses | Specific to Transaction Type |
| Amendment Clauses | Specific to Jurisdictional Area |
| Business Terms and Conditions | Unique to specific Business Entity |
| Intergration Clause | Mandatory, All Agreements |



### National excludes lex mercatoria


```
Clause <#>  – Choice of law: lex mercatoria and Unidroit Principles

This contract is governed by general principles of law generally recognized in
international trade (lex mercatoria) together with the Unidroit Principles of
International Commercial Contracts (except for Articles 2.20, 3.2.7 and 6.2.1).
```

```
Clause <#> – Network Model Clause

This contract shall be governed by the law of [State X] interpreted and supplemented
by the Freight Trust "RuleBook version v0.8.23" 

```

```
Clause 6.1
“Any questions relating to this Agreement which are not expressly or implicitly settled
by the provisions contained in this Agreement shall be governed, in the following
order:
1) by the principles of law generally recognized in international trade as applicable to
international [type of contract: e.g., distributorship, licence] contracts,
2) by the relevant trade usages, and
3) by the Unidroit Principles of International Commercial Contracts,
with the exclusion of national laws.”
This clause, which is the most frequently used clause within the ICC model contracts,
states that the contract shall be governed by the lex mercatoria and the Unidroit
Principles and provides at the same time the following hierarchical order:
1. Contract provisions,
2. general principles of law applicable to the particular type of contract in question,
3. trade usages,
4. Unidroit Principles.
```



### Replacement of a transferable document or instrument with an electronic transferable record

1. An electronic transferable record may replace a transferable document or instrument if a reliable method for the change of medium is used.

2. For the change of medium to take effect, a statement indicating a change of medium shall be inserted in the electronic transferable record.

3. Upon issuance of the electronic transferable record in accordance with paragraphs 1 and 2, the transferable document or instrument shall be made inoperative and ceases to have any effect or validity.

4. A change of medium in accordance with paragraphs 1 and 2 shall not affect the rights and obligations of the parties.



#### Meeting MLETR Requirements

> • 10\(1\)\(a\): equivalence in terms of content \(but see also Article 6 – additional  content not precluded – potential to increase functionality\).
>
>• 10\(1\)\(b\)\(i\) Mechanism for precluding “double pending”: performance obligation must >be singular.
>
>• 10\(1\)\(b\)\(ii\) Person to whom performance is due must be identifiable.
>
>• 10\(1\)\(b\)\(iii\) and 10\(2\): techniques to maintain integrity \(any changes to the >record must be identifiable\).
>
>

\(i\)**Operational Rules**: framework governing operation of the electronic system should be geared towards the achievement of desired outcomes.

\(ii\)**Data Integrity**: system must incorporate techniques to protect data from tampering and external attacks.

\(iii\) **Unauthorised access and use:** Who is permitted to enter data and method for becoming a system user are relevant considerations, as well as vulnerabilities to internal attacks.

\(iv\) **Security of hardware and software:** may bring into play worker complacency.

\(v\) **Audit: system **may need to be audited prior to going live, and regularly thereafter, to check for vulnerabilities.

\(vi\)**External Assessment and \(vii\) Industry standards**: International Organisation for Standardisation \(ISO\) provides benchmarks against which system may be assessed: Technology-specific standards, as well as general Quality, Risk Management, Business Continuity and Security Management Standards developed by ISO may apply.

#### Regulatory Environment in the U.S.A



## RuleBook v.0.8.32

| Requirement | FreightTrust | DCOs |
| :--- | :--- | :--- |
| RuleBook | Yes | Yes |
| Conflicts of Interest | Yes | Yes |
| Novation | Yes | Yes |
| Collateral \(inc. margin\) | No | Yes |
| Netting Arrangements | No | Yes |
| Dispute Resolution | Yes | Yes |
| Emergency Rules | Yes | Yes |
| Collateralized | Always 100% | up to 100% |


### **Authorized Representative**



\(a\) Each Network Participant shall designate one or more Authorized Representatives to sign all instruments, correct errors, perform such other duties as may be required under the Rules and transact all business in connection with the operations of FreightTrust. Each Network Participant must provide FreightTrust with current contact and other requested information for each of its Authorized Representatives.

\(b\) To designate an Authorized Representative, a Network Participant must provide the information requested and conform to the procedures and requirements established by Freight Trust. By agreeing to become an Authorized Representative, an individual agrees to be bound by the duties and responsibilities of an Authorized Representative and to be subject to, and comply with, the Rules and Obligations to the extent applicable.

\(c\) Freight Trust will promptly notify a Network Participant of the approval of nominated Authorized Representatives and will maintain a list of all approved Authorized Representatives for each Network Participant. Freight Trust shall promptly notif the parties involved  if Freight Trust  \(i\) declines to approve the designation, \(ii\) revokes the designation, or \(iii\) suspends the designation of an Authorized Representative or/and Network Participant.

\(d\) An Authorized Representative who is suspended remains subject to the Rules and jurisdiction throughout the period of suspension.

\(e\) To request the termination of the designation of an Authorized Representative, the Network Participant or the Authorized Representative must notify Freight Trust providing the information and complying with the procedures and requirements established by Freight Trust.

\(f\) An Authorized Representative remains subject to the Rules and the jurisdiction of Freight Trust for acts done and omissions made while registered as such, and a proceeding relating to an individual whose designation as an Authorized Representative or Network Participant and has been terminated or suspended shall occur as if the Authorized Representative were still registered as such.


## Dispute Resolution
    
 All Network Participants shall be required to arbitrate all disputes between or among themselves that relate to or arise out of any transaction submitted for *instrumentailization* in accordance with this Rule Book. For these purposes, each Network Participant shall be deemed a “Participant” for purposes of the rules set forth. Disputes involving Customers may be arbitrated in accordance to policy setforth in this Rule Book.
 
## Freight Specifics
 

### Broker/Freight Forwader
 
    Property broker surety bond or trust fund.
    
    (a) Security. A broker must have a surety bond or trust fund in effect for $75,000. The FMCSA will not issue a broker license until a surety bond or trust fund for the full limits of liability prescribed herein is in effect. The broker license shall remain valid or effective only as long as a surety bond or trust fund remains in effect and shall ensure the financial responsibility of the broker.
    
    (b) Evidence of security. Evidence of a surety bond must be filed using the FMCSA's prescribed Form BMC 84. Evidence of a trust fund with a financial institution must be filed using the FMCSA's prescribed Form BMC 85. The surety bond or the trust fund shall ensure the financial responsibility of the broker by providing for payments to shippers or motor carriers if the broker fails to carry out its contracts, agreements, or arrangements for the supplying of transportation by authorized motor carriers.

    (c) Financial institution—when used in this section and in forms prescribed under this section, where not otherwise distinctly expressed or manifestly incompatible with the intent thereof, shall mean—Each agent, agency, branch or office within the United States of any person, as defined by the ICC Termination Act, doing business in one or more of the capacities listed below:

(1) An insured bank (as defined in section 3(h) of the Federal Deposit Insurance Act (12 U.S.C. 1813(h));<br>
(2) A commercial bank or trust company;<br>
(3) An agency or branch of a foreign bank in the United States;<br>
(4) An insured institution (as defined in section 401(a) of the National Housing Act (12 U.S.C. 1724(a));<br>
(5) A thrift institution (savings bank, building and loan association, credit union, industrial bank or other);<br>
(6) An insurance company;<br>
(7) A loan or finance company; or<br>
(8) A person subject to supervision by any State or Federal bank supervisory authority.<br>
(9) Forms and Procedures<br>
<br>
(10) Forms for broker surety bonds and trust agreements. <br>
<br>
Form BMC-84 broker surety bond will be filed with the FMCSA for the full security limits under paragraph (a) of this section; or Form BMC-85 broker trust fund agreement will be filed with the FMCSA for the full security limits under paragraph (a) of this section.
<br>
(2) Broker surety bonds and trust fund agreements in effect continuously. Surety bonds and trust fund agreements shall specify that coverage thereunder will remain in effect continuously until terminated as herein provided.
<br>
<br> (i) Cancellation notice. The surety bond and the trust fund agreement may be cancelled as only upon 30 days' written notice to the FMCSA, on prescribed Form BMC 36, by the principal or surety for the surety bond, and on prescribed Form BMC 85, by the trustor/broker or trustee for the trust fund agreement. The notice period commences upon the actual receipt of the notice at the FMCSA's Washington, DC office.
<br>
<br>(ii) Termination by replacement. Broker surety bonds or trust fund agreements which have been accepted by the FMCSA under these rules may be replaced by other surety bonds or trust fund agreements, and the liability of the retiring surety or trustee under such surety bond or trust fund agreements shall be considered as having terminated as of the effective date of the replacement surety bond or trust fund agreement. However, such termination shall not affect the liability of the surety or the trustee hereunder for the payment of any damages arising as the result of contracts, agreements or arrangements made by the broker for the supplying of transportation prior to the date such termination becomes effective.
<br>
(3) Filing and copies. Broker surety bonds and trust fund agreements must be filed with the FMCSA in duplicate.


```

[53 FR 10396, Mar. 31, 1988, as amended at 75 FR 72998, Nov. 29, 2010; 78 FR 58482, Sept. 24, 2013; 78 FR 60233, Oct. 1, 2013]
```



## The system will be constructed multiple distinct components:

### Smart Contract

A BoL is in this context is an electronic document of title, meaning that a system
employed for evidencing the transfer of interests in the document must also reliably
establish the current owner of the document. In order to accomplish this, a smart
contract on an EVM-compatible network will be utilized to implement both a reference
to the document’s current owner, as well as the protocol in case of the transfer of
ownership of the document.

This shall be accomplished through the widely-used ERC721 standard and ERC721-
metadata extension. This standard shall allow parties to create, transfer, and view their
existing BoLs as tokenized assets by interacting with the BoL dapp smart contracts.
The ERC721 standard also provides simple transfer mechanisms that satisfy the
“transfer of interests” function of an electronic document of title, as well as simple
asset lookups that will establish the current owner of the BoL. The smart contracts shall
provide, among other things, the entire ERC721-compliant interface to its users.
The BOL smart contracts shall implement ownership transfer through a
function with enables transfer through the use of ECDSA signatures. This function shall
use the EVM opcode ecrecover to determine the signer of messages sent to it,
determining the intent of the current owner to transfer rights and responsibility to some
recipient. This ownership transfer mechanism is in addition to the ownership transfer
mechanism described in the ERC721 standard. <v2 protocol insert here>

Additional considerations are fully considered in devloping and designing the solution set for the protocol. Specifically in the ways that the software will interact and respond when performing out-of-scope ("crashing/failing"):

```
• Smart contracts may depend on other systems to fulfill contract terms. These other systems may
have vulnerabilities that could prevent the smart contract from functioning as intended.

• Some smart contract platforms may be missing critical system safeguards and customer
protections.

• Where smart contracts are linked to a blockchain, forks in the chain could create operational
problems.

• In case of an operational failure, recourse may be limited or non-existent – complete loss of a
virtual asset is possible.

• Poor governance. Smart contracts may require attention, action, and possible revision subject to
appropriate governance and liability mechanisms.
```

The  BOL Protocol shall implement a token creation function, named a designated trading facility, which allows token creation by providing an ECDSA signature, IPFS file hash/Other Distributed File Systems and intended recipient to the contracts. The ECDSA signature will sign the IPFS or other file hash and intended recipient, as well as a nonce to guarantee uniqueness. Constructs of the contract, called **optionality** enables additional functionality to be integrated programtically into the protocol at an 'atomic' level. It should be noted that for cross-border transactions there is a second component involved, a Instutionally offerd 'Lex as a Service', i.e. a legal regime for arbitration and adjuidication in which a designated couterparty is also party to transactions to ensure a reliable and deterministic business logic to transaction disputes. 

Additionally, the smart contracts shall implement upgradability mechanisms adhering to
the widely-used proxy library contract abstraction. This abstraction shall expose the
entirety of the ERC721 interface through a smaller proxy contract, as well as several
administrative functions. The proxy contract shall act as a simple call forwarder, and
will delegate all execution to the appropriate implementing contract. The administrative
functions included shall allow a privileged user (in this case, a party chosen by Block 


The BoL shall be created as a digital document of title, and should include the fields and
properties typically associated with bills of lading. This specification is out of the scope
of this document, but typically includes (among other things): a cargo manifest, a
unique ID, identifying information on the shipper and carrier, information on the origin
and destination of the cargo, and more. The BoL shall be represented as a PDF, XML, or
other widely-used document format.

The BOL shall be created by the carrier through some web interface, and presented to
the shipper. The shipper will provide an ECDSA signature of the document, carrier’s
identity, and shipper’s nonce to the carrier, signifying their intent to transfer ownership
and responsibility of the BoL and associated cargo to the carrier for the purpose of the
shipment of the cargo. The document shall be stored in fault-tolerant storage, and a hash of the document provided to the shipper as a receipt, along with any other contractual obligations required. Both the shipper and carrier should be
able to use this hash to query the IPFS network and receive the BoL in return.
The hash of the document along with the aforementioned ECDSA signature shall be
submitted to the BoL dapp smart contracts in order to mint a unique BoL token to the
carrier. This token will serve as a record of the ownership of the BoL. 


> Note: In the United States of America the Federal Bills of Lading Act provides that a common
carrier issuing a nonnegotiable bill of lading must put "nonnegotiable" or "not negotiable" on the bill, although this requirement does not apply to an informal memorandum or acknowledgmentA bill of lading as ordinarily issued is signed by the carrier only and it need not be signed by the shipper. Its terms and conditions are binding even though the bill is unsigned by the shipper, the signing of the bill only making it easier to prove the shipper was fully informed of its terms and assented thereto. In the case of goods received for transportation by rail or other land carriage, the bill of lading may be signed by the agent of the carrier who has authority to receipt for freight and to contract for its transportation 
>

.
#### Assigning a BOL to a Driver
The BoL shall be assigned by the carrier to a driver for the purpose of the shipment of
the cargo. The ownership transfer shall occur either through the standard ERC721
ownership transfer function, or through a specialized transfer function which, like the
token creation function, requires the carrier to provide an ECDSA signature of the IPFS
file hash, driver identity, and carrier nonce.


> Since a bill of lading acknowledges the receipt of goods for carriage, the delivery of the goods to the carrier should precede the execution of the bill, and the agent of a transportation company does not have the right to sign bills of lading until the goods have been actually delivered into the possession of the company. In practice, however, the delivery of the goods to be shipped and the delivery of a bill of lading for such goods are regarded as simultaneous acts. With respect to a private contract of carriage, the bills of lading are not required to describe the condition of the goods.
>
 Delivering a BoL and Associated Cargo
The BoL shall be transferred to the recipient by the driver along with the delivered cargo.
The ownership transfer shall occur either through the standard ERC721 ownership
transfer function, or through a specialized transfer function which, like the token
creation function, requires the driver to provide an ECDSA signature of the IPFS file
hash, shipper identity, and driver nonce.

### Design Rationale

**Efficiency**<br>
The considerations made when designing the system’s architecture were primarily
efficiency-based, sacrificing having the entire implementation in EVM smart contracts
for a more resilient system based on IPFS. The architecture allows parties involved in
the creation of, use of, and management of BoL documents to access them through the
worldwide IPFS network, as well as ensure that the documents they received are valid
through the EVM-compatible network.

**Flexibility**<br>
The system is additionally designed with flexibility in mind. By allowing Block Array to
manage implementations on-chain, the system is able to ensure it is well-defined, but
malleable. Technical standards change often, especially in a growing industry: this
architecture keeps on-chain information to a minimum, choosing instead to implement
a protocol on-chain and keep important information in IPFS.

**Ease of Use**<br>
The system can easily be designed to maximize simplicity of use for interested parties.
The signature and submission mechanisms can be implemented simply and safely
using MetaMask and a web interface. By ensuring BoLs use widely-used document
formats, the BoL can also be presented as a print document (or viewed in digital form).
By implementing the ECDSA-signature ownership transfer mechanism, the interested
parties do not need to interact with the EVM-compatible network. Instead, a third party
can submit these requests for them, eliminating the requirement for all parties involved
to own Ether (or a similar cryptocurrency). Together, these elements can create a
system that is secure, reliable, and transparent: without the involved parties being aware
of its existence.


## v.2.0.5 


Contract Instrument Semi-NFT

|  |  |
| :--- | :--- |
| ERC1400 | v2 |
| ERC1643 Document Managment |  v2 |
| ERC1154 | v1 |
| EIP 1077: Executable Signed Messages | v1 |
| EIP 1775 | v2 |
| "Atlas" Kernel | v2 |
|  ECANS | Yes |

**ERC777 implementation - Advanced token standard for asset transfers**

* Empowerment of operators with the ability to send tokens on behalf of other addresses.
* Setup of send/receive hooks to offer token holders more control over their tokens.
* Use of ER820\(eips.ethereum.org/EIPS/eip-820\) to notify contracts and regular addresses when they receive tokens.
* Backwards compatible with ERC20.

**ERC1400 implementation - Partially fungible token standard**

* Differentiated ownership / transparent restrictions.
* Controller operations \(force transfer\).
* On-chain restriction checking with error signalling, off-chain data injection for transfer restrictions and issuance / redemption semantics.
* Document management.
* Backwards compatible with ERC20 and ERC777.

**Ethereum Registration Authority / Trusted Certificate Authority**

```
Data Field for Signature Injection <Triggering_Event>

function transferWithData(address recipient, uint256 value, bytes data)
```

**ERC1643 implementation**

AddressID specifices which package is used for that operation/interogatives and subordinate clauses

Enables Agreement to be as homogonized or unique as needed, thereby extending possiblity of liquidity for layer 2+ applications.
<br>


## Definitions and Specifications 

<br>
a **registry** is a deployed contract which manages a collection of packages.

a **package** is a collection of releases

a **package** is identified by a unique string name and unique bytes32 packageId within a given registry

a** release** is identified by a bytes32 releaseId which must be unique for a given package name and release version string pair.

a** releaseId **maps to a set of data that includes a manifestURI string which describes the location of an EIP 1123 package manifest. This manifest contains data about the release including the location of its component code assets.

a **manifestURI** is a URI as defined by RFC3986 which can be used to retrieve the contents of the package manifest. In addition to validation against RFC3986, each manifestURI must also contain a hash of the content as specified in the EIP 1123.

a l**ibrary** is a staticc set of standard contracts like SafeMath. **libsol **is the authoratative library.

the **Kernel** compromises interlocking contracts that execute operations by invocation or trigger

```
Registry -> Package [libsol, kernel...] -> Release [specific contract updates] -> latest release
```

**Stand Alone:**    Package has no external dependencies \(i.e. no build\_dependencies\), contains all contract data needed without reaching into another package.

**Dependent:   ** Package does not contain all necessary contract data \(i.e. has build\_dependencies\), must reach into a package dependency to retrieve data.

**Inheritable**:    Contract doesn’t provide useful functionality on it’s own and is meant to serve as a base contract for others to inherit from.

**Reusable: **   Contract is useful on it’s own, meant to be used as-is. This applies only to kernel level contracts.

**Deployed Contract/Library:**

```
 Refers to an instance of a contract/library that has already been deployed to a specific address on a chain.
```

**Package Dependency:**

```
 External dependency directly referenced via the build\_dependencies of the package.
```

**Deep Dependency:**

```
 External dependency referenced via the build\_dependencies of a package dependency 
 (or by reaching down dependency tree as far as necessary\).
```

| &lt;/&gt; | Action |
| :--- | :--- |
| defaultOperator | Freight Trust, _Network Operations _ |
| AuthorizedOperator | 3rd Party \(e.g. Invoice Factoring, Insurance, etc\) |
| RevokedOperator | Default: 0 |
| setManager | Deployed On-Contracts, _Network Operations_ |
| getAttributeTypeID | interger |
| hasAttribute | string |
| symbol | Self Describing Contract Parameters |
| documentationIdentification | <string_prefix]little einden |


| legalAgreement | ... |
| masterAgreement | ... |
| tradeAgreement | . |
| uniqueAgreement | . |
| effectiveDate | . |
| eventDate | . |
| eventQualifier | . |
| eventIdentifier | . |
| lineage | . |
| contractKeyUID | . |
|  |  |

Object	Description
event_time	The exact time (UNIX time stamp) the event occurred.
event_type	The type of event that occurred.
event_hash	The unique hash of the event that occurred.
meta.related_document_hash	The unique document hash this event is associated with.
meta.related_user_id	The user identification this event is associated with. (Sender User ID)
meta.related_business_id	The business ID this event is associated with. (Sender Business ID)
meta.related_app_id	If this event is sent as part of a webhook notification for a specific app, this will contain the associated App ID.
signer.id	The signer ID this event is associated with.
signer.name	The name of the signer this event is associated with.
signer.email	The email address of the signer this event is associated with.
signer.role	The role of the signer this event is associated with. (Templates only)
signer.order	The signer order sequence number of the signer this event is associated with.

<br>

======================



```
No Claim to Orig. U.S. Govt. Works. <br>
Caselaw provided by Thomson Reuters. 33-34B © 2019 All rights reserved.

No Claim to Orig. Ethereum Improvement Proposals <br>
Ethereum.org 
```

````
Protocol Contracts and Platform Applications audited and secured by Authio.
Alexander Wade, Authio.org 
<br>
Specifications, Design and Legal implemented by FreightTrust.
Sam Bacha, Freight Trust & Clearing Corporation.
````


<br>
Clients

Extentions

Resources

Links

API for Applications 

WebSocket

JSON-RPC

ABI for Contract Library

ABI for In-Protocol Library

Metatransactions

OPCODES

Additional OPCODES

```
(c) 2019 - Freight Trust & Clearing Corp. (CC-3)
```

<br>

<br>
## teeDai 
*Trusted Execution Environment (inter)side (change)chain*


##### Creating the SterlingOS 
*a performant & scalable bare metal configuration for Intel x86 SGX1 clustering*


Hardware working on:

PowerEdge R230 BiOS 2.4+ 1270 R230 Xeon 

Currently SGX1 coverage, as no cloud provider has SGX2 out-of-the-box + bios support.

Base Distro
RHEL/CentOS 7.5

requires [https://github.com/mesalock-linux](https://github.com/mesalock-linux)


<br>
####  ⛔️ End User Notice ⛔️ 


Adjusting these settings can result in an unstable system. 

###### **These are root only and assumes root knows what they are doing.**


 ⚠️ very small values in sched_rt_period_us can result in an unstable
   system when the period is smaller than either the available hrtimer
   resolution, or the time it takes to handle the budget refresh itself.

 ⚠️ very small values in sched_rt_runtime_us can result in an unstable
   system when the runtime is so small the system has difficulty making
   forward progress (NOTE: the migration thread and kstopmachine both
   are real-time processes).

Realtime scheduling is all about determinism, a group has to be able to rely on
the amount of bandwidth (eg. CPU time) being constant. In order to schedule
multiple groups of realtime tasks, each group must be assigned a fixed portion
of the CPU time available.

#### Network Wide Settings

### System wide settings & procedure 
------------------------
Make sure you have

[SGX Hardware Support](https://github.com/ayeks/SGX-hardware)

[Intel Product Specifications check to see if your specific make supports](https://ark.intel.com/content/www/us/en/ark.html)


``> Intel SGX driver installed and /dev/isgx works``

``> gdb 7.11.1``

##### Development libraries needed:

```
$ yum install 
		libcgroup 
        libcgroup-tools 
        libcurl4-openssl-dev 
    	libssl-dev`
```

``` 
[baiduxlabs/sgx-rust](https://hub.docker.com/r/baiduxlab/sgx-rust) 

```

```
#!/bin/sh

# Error out on undefined variables to catch typos or other errors such as env
# vars not being defined when you expected it (not enough systems do this!)
set -u

# exec replaces the process; prevents needless /bin/sh from dangling around.
exec prog \
    -a "$A"          `# Always include A from environment, error out if unset`  \
    -b "${B:-d}"     `# Include B from environment, use "d" if unset` \
    "${C:+-c "$C"}"  `# Only pass -c $C if $C is set, pass nothing at all if unset` \
    "$@"             `# Include all argument passed to the shell script`

```


⛔️ **rustup** for install, **MUST NOT** use package managers, i.e. yum, rpm, apt

<br>

The system wide settings are configured under the /proc virtual file system:

/proc/sys/kernel/sched_rt_period_us:
  The scheduling period that is equivalent to 100% CPU bandwidth

/proc/sys/kernel/sched_rt_runtime_us:
  A global limit on how much time realtime scheduling may use.  Even without
  CONFIG_RT_GROUP_SCHED enabled, this will limit time reserved to realtime
  processes. With CONFIG_RT_GROUP_SCHED it signifies the total bandwidth
  available to all realtime groups.

  * Time is specified in us because the interface is s32. This gives an
    operating range from 1us to about 35 minutes.
  * sched_rt_period_us takes values from 1 to INT_MAX.
  * sched_rt_runtime_us takes values from -1 to (INT_MAX - 1).
  * A run time of -1 specifies runtime == period, ie. no limit.




##### Disable "irqbalance daemon"

procedure 
<br>
```
$ service irqbalance status
> irqbalance (pid PID) is running...
```

**if irqbalance daemon is running, disable..**
```
$ service irqbalance stop
> Stopping irqbalance: [ OK ]
```
Use chkconfig to ensure that irqbalance does not restart on boot.
```
$ chkconfig irqbalance off
```


#### Binding Processes to CPUs using the taskset utility

< backlog >

#### Determinstic Filesystem 

<Procedure verification needed>

Disabling atime, 
Configuring tmpwatch [tmpwatch controls how often /tmp is cleaned out]
``` 
**wio needs further verification**
```
🚧 Construction Zone 🚧 

#### Hardware clock system timestamping (suprasynchron)

> Procedure Verified

Multiprocessor systems such as NUMA or SMP have multiple instances of hardware clocks. During boot
time the kernel discovers the available clock sources and selects one to use. For the list of the available
clock sources in your system, view the


> /sys/devices/system/clocksource/clocksource0/available_clocksource file:

```
# cat /sys/devices/system/clocksource/clocksource0/available_clocksource
tsc hpet acpi_pm

```
+ The clock source currently in use can be inspected by reading the

> /sys/devices/system/clocksource/clocksource0/current_clocksource file:

```
# cat /sys/devices/system/clocksource/clocksource0/current_clocksource
tsc

```

###### "suprasynchron" - defining hardware clocksource for consistantcy of block-time and real-time

Select clock source from list given by:

> /sys/devices/system/clocksource/clocksource0/available_clocksource file

Must choose **HPET**

```
$ echo hpet > /sys/devices/system/clocksource/clocksource0/current_clocksource


```


##### SGX Driver
```
$ curl --output /tmp/driver.bin https://download.01.org/intel-sgx/linux-2.3.1/ubuntu18.04/sgx_linux_x64_driver_4d69b9c.bin
/usr/bin/env bash /tmp/driver.bin
depmod
modprobe isgx
```
verify install: ```dmesg``` should show ``` Intel SGX Driver v0.11``` install was successful 


##### configure libsecp256k

configure the libsecp256k1 library by going into 

```
$ cd src/trusted/libs/


```
+ aesmd daemon 
```
$ docker run --rm -it -v /run/aesmd:/run/aesmd --device /dev/isgx <AWS ECR LINK>
```


#### Building Client 

(I)   Protocol
(II)  Servlet 
(III) Enclavelet



<gradle vs maven>

Notes:
Maven pom.xml config

define JVM configuration via ${maven.projectBasedir}/.mvn/jvm.config


 -Xmx2048m -Xms1024m -XX:MaxPermSize=512m -Djava.awt.headless=true

Maven pom.xml

MAVEN_OPTS=-XX:MaxRAM=3572m -Xmx1g
-XX:MaxRAM=3572m -Xmx8g



# Sources & Datasets

<br>
Sources:
	Section, Topic, Author 
Tools:

Tiago P. Peixoto, **“The graph-tool python library”**, figshare. (2014) DOI: 10.6084/m9.figshare.1164194 [sci-hub, @tor]


**High Throughput Byzantine Fault Tolerance. DSN’04.
**
Ramakrishna Kotla and Mike Dahlin. 

**Monoxide: Scale out Blockchains with Asynchronous Consensus Zones. NSDI'19**
Wang, Jiaping, and Hao Wang. 

**Untangling blockchain: A data processing view of blockchain systems. TKDE'17**
Dinh, Tien Tuan Anh, et al. 


**Blockchains from a distributed computing perspective. Communications of the ACM**
Maurice Herlihy

**Tan: BlockBench: A Framework for Analyzing Private Blockchains. SIGMOD'17**
T. Dinh, J. Wang, G. Chen, R. Liu, B. Chin Ooi, K.-L. 


**Achieving One Billion Key-Value Requests per Second on a Single Server. IEEE Micro'16**
Sheng Li, Hyeontaek Lim, Victor W. Lee, Jung Ho Ahn, Anuj Kalia, Michael Kaminsky, David G. Andersen, Seongil O, Sukhan Lee, Pradeep Dubey. 

**DARE: High-Performance State Machine Replication on RDMA Networks HPDC'15
**
Marius Poke, Torsten Hoefler.

**Fast and general distributed transactions using RDMA and HTM. EuroSys'16**
Yanzhe Chen, Xingda Wei, Jiaxin Shi, Rong Chen, Haibo Chen. 
 
**Research for practice: distributed consensus and implications of NVM on database management systems. Commun. ACM’16**
Peter Bailis, Joy Arulraj, and Andrew Pavlo.


**Consensus in a Box: Inexpensive Coordination in Hardware  NSDI'16**
Zsolt István, David Sidler, and Gustavo Alonso, Marko Vukolić.


Special Thanks:
I. Barinov **BlockNotary** , **POA: Proof of Authority & Aura Concensus**
B. Mcelrarth **BRaided Blockchains: Braidcoin**
G. Wood. **Ethereum: A secure decentralised generalised transaction ledger** 
S. Nakamoto. **Bitcoin: A peer-to-peer electronic cash system. 2008**


------

Glossary 

-------

**Ammendment** means a change to a document/smart contract. *see Endorsement*

* Bill of Lading (“BoL”)
A bill of lading is, in this context, an electronic document of title presented to a shipper
by a carrier as a receipt for some agreement to carry cargo from one location to
another.

* Carrier
A carrier is a party approached by a shipper to transfer some cargo on their behalf. The
carrier presents the shipper with a BoL as a digital agreement under which the
transaction will be carried out. The carrier assigns some driver to deliver the cargo.

* Decentralized Application (“dapp”)
A decentralized application is an application which runs primarily (or solely) on a
network comprised of many computers, none of which have ultimate permissions over
the entirety of the system.

* Driver
A driver operates under some carrier, and delivers cargo as per the terms of the BoL
agreed upon by the carrier and shipper. The driver is responsible for the safe delivery of
the cargo, and receives the BoL prior to delivery of the cargo. Upon delivery of the cargo,
the driver receives the signature of the shipper as proof of successful delivery

* Elliptic Curve Digital Signature Algorithm (“ECDSA”)
ECDSA is an elliptic curve signature algorithm which allows parties to generate digital
signatures which can be verified to be unique, to consist of some data, and to belong to
the identity used to sign the data.


* Ethereum Virtual Machine (“EVM”)
The Ethereum Virtual Machine is a general-purpose virtual machine which runs on
distributed blockchain networks. The EVM supports many simple instructions which
operate on 256-bit values.

* Electronic Document of Title
An electronic document of title is issued by an individual who has custody of some
goods (in this case, cargo to be shipped) to an individual who has entrusted the
previous party with the goods.

**Endorsement** (a) means an amendment to an insurance policy. (b) a change to end user, cosignee or receiving party for a negotible instrument.

**Environmental restoration** means restitution for the loss, damage, or destruction of natural resources arising out of the accidental discharge, dispersal, release or escape into or upon the land, atmosphere, watercourse, or body of water of any commodity transported by a motor carrier. This shall include the cost of removal and the cost of necessary measure taken to minimize or mitigate damage to human health, the natural environment, fish, shellfish, and wildlife.

* ERC721 Standard
The ERC721 standard is a standard interface used by EVM smart contracts to define a
general implementation and interface for tokenization of unique digital assets. In this
case, the ERC721 standard acts as the method by which BoL ownership is recorded and
transferred from party to party.

**Evidence of security** means a surety bond or a policy of insurance with the appropriate endorsement attached.

**Financial responsibility **means the financial reserves (e.g., insurance policies or surety bonds) sufficient to satisfy liability amounts set forth in this subpart covering public liability.

**For-hire carriage **means the business of transporting, for compensation, the goods or property of another.
In bulk means the transportation, as cargo, of property, except Division 1.1, 1.2, or 1.3 materials, and Division 2.3, Hazard Zone A gases, in containment systems with capacities in excess of 3500 water gallons.
In bulk (Division 1.1, 1.2, and 1.3 explosives) means the transportation, as cargo, of any Division 1.1, 1.2, or 1.3 materials in any quantity.
In bulk (Division 2.3, Hazard Zone A or Division 6.1, Packing Group I, Hazard Zone A materials) means the transportation, as cargo, of any Division 2.3, Hazard Zone A, or Division 6.1, packing Group I, Hazard Zone A material, in any quantity.
Insured and principal means the motor carrier named in the policy of insurance, surety bond, endorsement, or notice of cancellation, and also the fiduciary of such motor carrier.

**Insurance premium **means the monetary sum an insured pays an insurer for acceptance of liability for public liability claims made against the insured.

**Motor carrier** means a for-hire motor carrier or a private motor carrier. The term includes, but is not limited to, a motor carrier's agent, officer, or representative; an employee responsible for hiring, supervising, training, assigning, or dispatching a driver; or an employee concerned with the installation, inspection, and maintenance of motor vehicle equipment and/or accessories.


* Nonce
A nonce is a simple data structure used to ensure transactions and signatures which
may be of the same (or similar data) are unique. In the system described below, each
party (shipper, carrier, driver) has unique nonces, which ensure their signatures are
unique to the BoL in question.

* Proxy Library Abstraction
A proxy library abstraction is a design pattern for EVM-based smart contracts which
enables the maximum flexibility for implementing applications. The abstraction
presents an interface to the user through which functions in the application are
executed. This interface is a proxy, meaning that it delegates execution to some other
smart contract, ensuring implementation can be changed if needed.

| **Payment instrument** means any electronic or written check, draft, money order, traveler’s check or other electronic or written instrument or order for transmitting or paying money, sold or issued to one or more persons, whether or not the instrument is negotiable. Payment instrument does not include any credit card voucher, any letter of credit or any instrument that is redeemable by the issuer in goods or services. |
| :--- |

**Property damage **means damage to or loss of use of tangible property.
Public liability means liability for bodily injury or property damage and includes liability for environmental restoration.
State means a State of the United States, the District of Columbia, Puerto Rico, the Virgin Islands, American Samoa, Guam, and the Northern Mariana Islands.Cancellation of insurance means the withdrawal of insurance coverage by either the insurer or the insured.


| **Stored value.**--Monetary value representing a claim against the issuer that is stored on an electronic or digital medium and is evidenced by an electronic or digital record, and that is intended and accepted for use as a means of redemption for money or monetary value or payment for goods or services. The term does not include stored value that is redeemable by the issuer exclusively in goods or services; stored value that is redeemable exclusively in goods or services limited to transactions involving a defined merchant or location or set of locations, such as a specific retailer or retail chain, college campus, or subway system; or program points, miles, or other units issued in connection with a customer affinity or rewards program, even if there |
| :--- |


* Shipper
A shipper is a party with some cargo approaches a carrier to deliver the cargo from one
location to another. The shipper and the carrier reach an agreement about the details of
the delivered cargo, and produce a BoL as a receipt to the shipper.







___


> (c) [freight trust & clearing corporation](https://freighttrust.com/)  
> licensed under bsd-3 clause & other open source licenses. 
_____________________________________________________________________________________________
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NjU0NTIwOTddfQ==
-->