

**Weekend project 2 - Group 15**

•	Form groups of 3 to 5 students

•	Complete the contracts together

•	Structure scripts to

o	Deploy everything

o	Interact with the ballot factory

o	Query proposals for each ballot

o	Operate scripts

•	Publish the project in Github

•	Run the scripts with a few set of proposals, play around with token balances, cast and delegate votes, create ballots from snapshots, interact with the ballots and inspect results

•	Write a report detailing the addresses, transaction hashes, description of the operation script being executed and console output from script execution for each step
•	(Extra) Use TDD methodology

Getting Started

Before everything, clone the project:

**git clone https://github.com/Encode-Club-Solidity-Group-14/project_week_02.git
**
Building

yarn install

yarn hardhat compile

Tests

yarn hardhat test

Coverage check

npx hardhat coverage**

Scritps Usage

**Deploy Everything**

Script: deploy.ts {list_of_proposals}

yarn ts-node --files .\scripts\deploy.ts Proposal_1 Proposal_2 Proposal_3

 

Result:
•	Token Contract deployed at 0x7E5D51Db01Bcdc9D4bcec84Deb661B463C9d2D71

•	Custom Ballot Contract deployed at 0x1cCF8f6DF5A56Cd78ECFD3d083788597F52FcBbF

**Query Proposals**

Script: query_proposal.ts {custom_ballot_address} {proposal_index_to_query}

yarn ts-node --files .\scripts\query_proposal.ts 0x1cCF8f6DF5A56Cd78ECFD3d083788597F52FcBbF 0

 


**Mint**
Script: mint.ts {token_address} {address_to_receive_minted_tokens} {amount_to_mint}
yarn ts-node --files .\scripts\mint.ts  0x7E5D51Db01Bcdc9D4bcec84Deb661B463C9d2D71 0x56D21d44F1C4c1ae0a5FF5d589CC344292A1E9c2 15

 

•	Minted transaction execution 0x7E5D51Db01Bcdc9D4bcec84Deb661B463C9d2D71
 

**Delegate**

Script: delegate.ts {token_address} {address_to_delegate}
node_modules\.bin\ts-node --files .\scripts\delegate.ts 0x7E5D51Db01Bcdc9D4bcec84Deb661B463C9d2D71 0xe328a3D1bC7C20AA851Bc85897262bD37364a7D4
 

•	Delegate transaction execution Address: 0xe328a3D1bC7C20AA851Bc85897262bD37364a7D4 Votes: 0.0

**Cast
**
Script: delegate.ts {custom_ballot_address} {token_address} {proposal_index}

ts-node --files .\scripts\cast.ts 0x1cCF8f6DF5A56Cd78ECFD3d083788597F52FcBbF 0x7E5D51Db01Bcdc9D4bcec84Deb661B463C9d2D71  0

 
•	Cast transaction execution Hash: 0x1b1bb6d474a6c799d35f26a1a67e6c5e8a32ca6bd1dfbf7c1d90e47e6fb60fdb
**Query results**

Script: delegate.ts {custom_ballot_address}

yarn ts-node --files .\scripts\query_results.ts 0x1cCF8f6DF5A56Cd78ECFD3d083788597F52FcBbF

 

Using address 0x56D21d44F1C4c1ae0a5FF5d589CC344292A1E9c2
Wallet balance 54.96486693739313
Attaching custom ballot contract interface to address 0x1cCF8f6DF5A56Cd78ECFD3d083788597F52FcBbF
Winning proposal is: Proposal_1
Done in 8.52s.  


**Create Ballot from Snapshots**

Script: create_ballot_from_snapshot.ts {token_address} {list_of_proposals}

yarn ts-node --files .\scripts\create_ballot_from_snapshot.ts 0x7E5D51Db01Bcdc9D4bcec84Deb661B463C9d2D71  New_Proposal_1 New_Proposal_2 New_Proposal_3



 
•	Custom Ballot Contract deployed at 0x42208CA16E3E7e3079F2a136D2b71102260d85C3
