# Secure-EHRs-using-Hyperledger-Fabric---Blockchain

# EHR System

A secure Electronic Health Record system of patient records, that has entire patient history and health files at one stop for easy access for doctors, patients researchers etc.

---

## Problem Statement
Over decades, medical facilities have evolved elegantly. Still most of us are the witness of the fact that whenever we see a doctor, we need to put forward our medical file in front of him/her. Our file contains our previous prescriptions, medical reports, X-Rays, MRIs etc. It is a tedious task to keep record of all these.

## Aim of the Project
1. To develop a Blockchain Network to securely store medical records such the data become more useful for research institutions: The traditional method of storing medical records is to keep the data in a database server. Sometimes the data will be inaccessible if the database server is down or the data will be exposed to attackers if the database server is vulnerable. The feature of Blockchain will assure that the blocks in ledger are not modifiable
2. To synchronize the records between each system member. Each medical institution will keep their own copy in an independent database, so it is difficult to trace the latest update of the records. Blockchain is a decentralized system, it stores data distributed on multiple machines.
3. Secure, immutable and decentralized EHR database with patient as data owner of EHR data
4. Can act as a foundation for the DISHA(Digital Information Security in Healthcare, Act) bill in India
5. To provide a single point of access for the full medical history of a patient
6. Easier prescription verification for pharmacists can be enabled
7. Transparency can be increased
8. Insurance Frauds can be avoided.



## Why Blockchain?

### Security
Blockchain provides a secure way of managing records.
### Public Health
By using blockchain technology, regulatory bodies can create a shared stream of de-identified patient information.
### Managed Consent
Patients can specifically authorise any individual to access their medical information.
### Simplified Claim Processing
Blockchain technology can simplify the complex medical billing process by eliminating the series of validations and multiple third parties acting on behalf of other entities.
### Patient Generated Data
Patients will be able to easily upload and securely store their updated medical information without messing up any previous records.

## Tech Stack used for the project
* IBM’s Hyperledger Framework for Blockchain
* Hyperledger Composer based on Fabric Architecture
* Hyperledger Playground for Blockchain
* HTML, CSS, Ajax & JQuery for Website (FrontEnd)

# Instructions to run the API Backend
- Clone the repo
- CD into the cloned directory 
- First install [Hyperledger composer](https://hyperledger.github.io/composer/latest/installing/installing-prereqs.html). Then install the [development environment](https://hyperledger.github.io/composer/latest/installing/development-tools.html).
- Execute the following commands to setup your Blockchain network and generate Hyperledger Composer Rest Server:
- `composer archive create -t dir -n .`
- `composer network install --card PeerAdmin@hlfv1 --archiveFile tutorial-network@0.0.1.bna`
- `composer network start --networkName ehr --networkVersion 0.0.3 --card PeerAdmin@hlfv1 --networkAdmin admin --networkAdminEnrollSecret adminpw --file networkadmin.card`
- `composer card import --file networkadmin.card` 
- `composer-rest-server -c admin@tutorial-network -n always -u true -d y -w true`
- Goto `http://localhost:3000/explorer` to explore the REST API

# Instructions to restart the server
- Change to the directory where the docker-compose.yml file is 
- Run `docker-compose stop` to stop the Fabric Containers.
- Run `docker-compose start` to restart where you left off.
- Change to the cloned repo's directory: 
- Run this command to start the server: `composer-rest-server -c admin@tutorial-network -n always -u true -d y -w true`
- Goto `http://localhost:3000/explorer` to explore the REST API.


## License

This project is available under the MIT license. See the [LICENSE](LICENSE) file for more info.
