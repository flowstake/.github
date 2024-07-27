# FlowStake

## Flowstake - Proof of Activity Network Documentation

FlowStake is an innovative platform designed to capture and record proof of physical activities as stakes, utilizing blockchain technology to ensure transparency and reliability. The platform supports activities such as running and cycling and integrates various features to provide a comprehensive user experience.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Integrations](#integrations)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Introduction

FlowStake aims to revolutionize how physical activities are tracked and verified. By using a distributed ledger, we ensure that each activity is recorded securely and transparently. Our platform provides a social network-like experience where users can interact, compete, and attest to each other's activities.

## Features

- **User Registration and Account Management**: User registration, social signup, account creation, and wallet abstractions.
- **Proof of Stake Smart Contracts**: Choose and utilize "Proof of Stake" smart contracts to "bet on yourself" and motivate athletic achievements.
- **Activity Tracking**: GPS and heartbeat data tracking for running and cycling.
- **Biometric Data Capture**: Integration with wearable devices to capture heart rate and other biometric data.
- **Leaderboards**: Leaderboards for classic running events (5k, 10k, 13.1mi, 26.2mi) and personal records (PRs).
- **Social Interaction**: Activity profile, social media feed of user activities, friend interactions, and collective attestations.
- **Attestation**: Peer-to-peer attestation, RFID chips/race bibs, NFC tap, and photo/video verification with 2FA codes/QR codes.
- **Blockchain Integration**: Permanent records stored on Hedera Hashgraph and Ethereum smart contracts for self-sports betting.
- **Account Management**: Secure login and account management using web3auth.io.
- **Progressive Web App**: Live data capture and mobile compatibility for iOS and Android.
- **Data Integration**: Integration with Strava as the data oracle/data source to help test the smart contracts.

## Technologies Used

- **Frontend**: React Native with Expo SDK 46
- **Backend**: Firebase for data storage
- **Blockchain**: Hedera Hashgraph and Ethereum smart contracts
- **Authentication**: web3auth.io
- **Hosting**: IPFS (InterPlanetary File System)
- **Miscellaneous**: Computer vision for activity identification

## Installation

To get started with FlowStake, follow these steps:

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/flowstake.git
    ```
2. Navigate to the project directory:
    ```sh
    cd flowstake/expo
    ```
3. Install dependencies:
    ```sh
    npm install
    ```
4. Start the development server:
    ```sh
    expo start
    ```

## Usage

1. Sign up or log in using [flowstake.com](https://flowstake.com).
2. Start tracking your activities using the GPS and heartbeat data features.
3. Verify activities through RFID chips/race bibs, NFC tap, photo/video attestation, and peer-to-peer attestation.
4. Interact with friends through the activity feed and participate in self-sports betting using Ethereum smart contracts.
5. Use Strava integration to import and verify activity data.

## Integrations

FlowStake integrates with several fitness apps and platforms to enhance the user experience and provide comprehensive activity tracking and verification.

- **Strava**: Import and verify activity data from Strava, ensuring accurate and authenticated records.
- **RunSignup**: Integration with RunSignup to facilitate participation in official running events and import race results.
- **Garmin**: Connect with Garmin devices to capture detailed biometric data such as heart rate and other fitness metrics.
- **Apple Health**: Sync with Apple Health to import activity data and biometric information from various Apple devices.
- **Google Fit**: Integration with Google Fit to ensure compatibility with a wide range of Android devices and fitness apps.

## ProofOfActivityStake - Contract Standards

### Minimum Level of Data Verification

- **Distance and Duration**: Accurate tracking of distance and duration using GPS data.
- **P2P Live Attestations**: Real-time peer-to-peer attestations during activities.
- **Identity Verification**: Photo attestations of 2FA codes or generating QR codes for verification.
- **Biometric Verification**: Capture and verification of heart rate and other biometric data using wearable devices.

### Data Preprocessing Recommendations

- **Anti-Cheating Measures**: Implement preprocessing steps to filter out irregularities or anomalies in the activity data.
- **Verification Checks**: Cross-reference activity data with Strava integration and other fitness apps to ensure authenticity.

## Contributing

We welcome contributions from the community. To contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some feature'`).
5. Push to the branch (`git push origin feature/your-feature`).
6. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For any inquiries or issues, please contact us at Flowstake@protonmail.com.

---

Feel free to modify or expand this README as needed. Let me know if you need any additional sections or details!
