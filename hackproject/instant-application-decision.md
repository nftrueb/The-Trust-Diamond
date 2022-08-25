# Instant Application Decision

 
#### Table of Contents
  - [Reference](#Reference)
  - [Business Challenge](#business-challenge)
    - [Concept](#concept)
    - [Approach](#approach)
  - [Vernacular](#vernacular)
  - [Assumptions](#assumptions)
  - [Persona](#persona)
  - [Story](#story)
  - [Demo Workflow](#demo-workflow)
    - [Step 1](#step-1)
    - [Step 2](#step-2)

 
## Reference
Data from Following links has been quoted or used as a template in this use case story
* https://trustoverip.github.io/WP0010-toip-foundation-whitepaper/trust/vcred_trust_triangle/
* https://github.discoverfinancial.com/dgisolf/digital-trust-wg/blob/master/taskforces/usecases/medical-office-visit.md

## Business Challenge
In todays world Discover reaches out to any government agency or credit bureau for any information pertaining to a customer or prospective customer. There is obviously a wait time ranging from couple days to couple weeks before getting the information. Scenarios could be when applying for a new loan/credit card or existing customer having to go through credit bureau check during scenarios related to fraud on the account. 

In the future if customer can just provide the Digital credential(for verification) to Discover during the credit card application process or when his account is on hold for further information from agencies. Using the digital credential provided by the customer, Discover which is the verifier would  verify the customer with the agency which is the Issuer.

This not only is very fast way of verifying the (prospective) customer but also highly secure. This makes the life of customer, agency and Discover very easy as the Customer gets to use his card sooner and the agencies dont have to deal with providing same information again and again for the same customer on different occasions. Discover can approve the credit card or loan sooner and customer can start making purchases and use it. This will provide opportunity to do more business and provide great customer satisfaction both of which are very important to Discover.
 
### Concept
The term Trust Triangle is often used when discussing the interactions between the stakeholders of credential issuance and presentment. These stakeholders, Issuer, Holder, and Verifier, depend on one another for the exchange of trusted information.

An Issuer issues a credential to a Holder.
A Holder trusts the Issuer.
A Verifier verifies a credential presented by a Holder.

![trust-triangle](/designs/images/misc/trust-triangle.png)

First the issuer writes a Decentralized Identifier (DID) together with its public key (and any other cryptographic material needed for the issuer’s verifiable credentials) to a blockchain (or other sufficiently trusted public utility).
Second, the issuer uses its private key to digitally sign a verifiable credential it issues to a qualified holder, who stores it in her own digital wallet. Note that for privacy preservation, this entire issuance process takes place ​off-chain​.
Third, a verifier requests a digital proof of one or more credentials from the holder. If the holder consents, the holder’s wallet generates and returns the proofs to the verifier. Since the proofs contain the issuer’s DID, the verifier uses it to read the issuer’s public key and other cryptographic data from the blockchain.
In the final step, the verifier uses the issuer’s public key to verify that the proofs are valid and that the digital credential has not been tampered with.

### Approach

The goal is to demonstrate the end-to-end activities necessary for a customer to:

* Get approved for a credit card using the digital credentials from his wallet (provided by government agencies/credit bureau etc) 
* present digital  credential as proof when needing any verifications to obtain Discover product/service
*
A variation of this scenario would be to consider any situation where DFS may have a business policy that requires proof of employment or income details,  identity verification or verification from any other agency. All of those can be obtained from the source and stored in customers wallet to be used for verification when needed.

![trust-diamond-triangle](/designs/images/misc/trust-diamond-triangle.jpeg)

## Vernacular
 
1. **Digital Wallet**: A financial transaction application that runs on multiple device modalities (mobile, computer). These applications store, manage, and present payment and identity instruments.
3. **Merchant**: An entity involved in e-commerce trade.
4. **Checkout Platform**: An e-Commerce Payment Platform (web application) used by merchants to manage the consumer experience and the end-to-end processing of e-commerce transactions.
5. **Credential Verifier Utility**: A merchant would augment their Checkout Platform with support by a vendor solution that allows consumers to: (a) consent to a digital authentication challenge; (b) present a digital credential for identity verification.
6. **Issuer**: A entity that makes assertions about information and delivers digital credentials containing attestations about those assertions.
7. **Credential Generator**: A software component used by the Issuer to manage the generation of new digital credentials.
8. **Credential Issuer Utility**: An Issuer would augment their Credential Generator with support by a vendor solution that allows Issuers to publish a digital credential to consumers.
9. **Public Registry**: A public utility that allows for the registration and discovery of Decentralized Identifiers (DIDs).
 
## Assumptions

1. Use case assumes knowledge of the W3C Standards and open source software that supports the concepts outlined by the [Trust over IP Foundation](https://trustoverip.org/toip-model/).
2. Credential Issuer and Verifier Utility solutions are readily available from 3rd party vendors.
 
## Persona
 
| Actor | Role | Goals | Details |
| --- | --- | --- | --- |
| <img src="./images/persona/discover_logo.png" width="60" height="60"> | Verifier | Uses  Credential capabilities to allow customers to verify income and identification credentials. | Leverages ecosystem of Digital Trust vendors, such as  Avast, to provide digital credential verification capabilities.  |
Federal Agency | Issuer | Federal/Government agency, a provider that allows for issuing identification credentials. | Identification provider partner for (prospective) customers of DFS |
Credit Bureau | Issuer | Credit Bureau agency, a provider that allows for issuing credit score credentials or taxable income details from IRS. | Income provider partner for (prospective) customers of DFS  |
<img src="./images/persona/Boris.png" width="40" height="40"> Roger | Holder | Needs a Discover credit card and wants to present proof of identification, credit score and taxable income details in a secure manner for faster processing | (Prospective) Customer of DFS credit card carries a mobile device with a digital wallet containing verifiable credentials from a variety of issuers. |
<img src="./images/misc/avast.png" width="50" height="50"> Avast | Vendor | Allow customers to request, store, manage, and present digital credentials from their mobile devices. | Digital Trust vendor and supplier of connect.me digital wallet. |
 
## Story

### Issuance of identification Credential
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger signs in to the Government agency portal.
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger sees a feature to *Generate Secure Credential(s)*.
* The System presents the credential options.
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger selects one or more credentials and clicks OK.
* The software generates a QR code and instructional text “Scan Credentials with your Digital Wallet App”.
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger opens his <img src="./images/misc/avast.png" width="50" height="50"> Avast digital wallet, ```Connect.me```, and scans the QR code.
* The ```Connect.me``` App prompts <img src="./images/persona/Boris.png" width="40" height="40"> Roger with the messsage: “Government Agency is offering the following secure credentials, do you accept?”
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger initiates the process to accept the offer of secure credentials.
* Credentials are sent to <img src="./images/persona/Boris.png" width="40" height="40"> Roger's device and protected with the secure element of the device.

### Issuance of Income Credential
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger visits the Credit Bureau website and requests information. 
* The website displays a QR code and instructional text “Scan Request with your Digital Wallet App”.
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger opens the ```Connect.Me``` App on his device and scans the QR code.
* The ```Connect.me``` App prompts <img src="./images/persona/Boris.png" width="40" height="40"> Roger with the message: "Credit Bureau is offering the following secure credentials, do you accept?”
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger initiates the process to accept the secure credential.
* Credential is sent to  <img src="./images/persona/Boris.png" width="40" height="40"> Roger's device and protected with the secure element of the device.

### Applying for a Credit Card
* One fine day <img src="./images/persona/Boris.png" width="40" height="40"> Roger needs to apply for a 'credit card'/'personal loan'.
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger visits <img src="./images/persona/discover_logo.png" width="50" height="40"> Discover website.
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger fills the basic information needed to apply and then submits the request.
* The web page displays a QR code and instructional text “Scan Request with your Digital Wallet App”.
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger opens the ```Connect.Me``` App on his device and scans the QR code.
* The ```Connect.me``` App prompts <img src="./images/persona/Boris.png" width="40" height="40"> Roger with the message: " <img src="./images/persona/discover_logo.png" width="80" height="80"> Discover is requesting proof of identification, credit score and taxable income. Do you accept?”
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger accepts the credential request.
* Using the ```Connect.me``` App, <img src="./images/persona/Boris.png" width="40" height="40"> Roger selects the credentials in his wallet that will be used to respond to the request. 
* Credential is securely transferred to and verified by <img src="./images/persona/discover_logo.png" width="50" height="40"> Discover.
* <img src="./images/persona/Boris.png" width="40" height="40"> Roger is approved for 'credit card'/'personal loan'.

## Demo Workflow
 
### Step 1
Issuers and Verifier register their DIDs.
### Step 2
Register Schema, claim definitions and controller setup.
### Step 3
Customer Acquires proof of identification from issuer 1 ( Government Agency).
### Step 4
Customer Acquires proof of identification from issuer 2 ( Credit Bureau).
### Step 5
Customer applies for credit card and is approved instantly.


 ![sequence-diag-instant-application-decision](./designs/images/uml/seq-diagram.png)
