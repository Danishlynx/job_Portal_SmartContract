

# Job Portal Smart Contract

![License](https://img.shields.io/badge/license-MIT-green)

This is a Solidity smart contract for a job portal application. The contract allows for the management of applicants, jobs, job applications, and applicant ratings.

## Features

- Add and manage applicants with their details.
- Create and manage job listings with titles and descriptions.
- Applicants can apply for jobs, and their applications are tracked.
- Admins can provide ratings to applicants.
- Ratings for applicants are stored on the blockchain.

## Table of Contents

- [Getting Started](#getting-started)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Getting Started

To interact with this smart contract, you can deploy it to a compatible blockchain network (e.g., Ethereum). You will need a development environment set up with Solidity and access to a blockchain network.

### Prerequisites

- Solidity development environment
- Ethereum-compatible blockchain network

### Deployment

1. Clone this repository to your local machine.
2. Compile the Solidity smart contract using your preferred development environment.
3. Deploy the contract to your chosen blockchain network.

## Usage

### Smart Contract Functions

- `addApplicant`: Allows the admin to add a new applicant.
- `getApplicantDetails`: Retrieves applicant details based on the applicant ID.
- `addJob`: Allows the admin to add a new job listing.
- `getJobDetails`: Retrieves job details based on the job ID.
- `applyForJob`: Applicants can use this function to apply for a job.
- `provideRating`: Admins can provide ratings to applicants.
- `fetchApplicantRating`: Retrieves an applicant's rating.

### Examples

Here's an example of how to interact with the smart contract using web3.js (JavaScript library for Ethereum):

```javascript
// Add a new applicant
jobPortalContract.methods.addApplicant("John Doe", "Developer").send({ from: adminAddress });

// Get applicant details
const applicantDetails = await jobPortalContract.methods.getApplicantDetails(applicantId).call();

// Add a new job
jobPortalContract.methods.addJob("Software Engineer", "Job description").send({ from: adminAddress });

// Apply for a job
jobPortalContract.methods.applyForJob(jobId).send({ from: applicantAddress });

// Provide a rating to an applicant
jobPortalContract.methods.provideRating(applicantId, 5).send({ from: adminAddress });

// Fetch applicant rating
const applicantRating = await jobPortalContract.methods.fetchApplicantRating(applicantId).call();
