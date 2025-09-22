# GitHub Project Details

## Project Title

**BlockProperty - Decentralized Property Registry on Hyperledger Fabric**

# BlockProperty - Decentralized Property Registry on Hyperledger Fabric

A secure, transparent, and immutable property management system built on Hyperledger Fabric blockchain technology. This application provides a decentralized platform for registering, tracking, and managing real estate properties with complete audit trails and tamper-proof records.

## 🏗️ Project Overview

BlockProperty leverages blockchain technology to revolutionize property management by providing a transparent, secure, and decentralized ledger for real estate assets. Built on Hyperledger Fabric, this application ensures data integrity, prevents fraud, and enables trusted property transactions through smart contracts (chaincode).

The system maintains comprehensive property records including ownership details, location information, property specifications, and transaction history - all secured by blockchain's immutable nature.

## ✨ Key Features

### 🏠 Property Management

- **Register New Properties**: Add properties to the blockchain with complete details
- **View All Properties**: Browse the entire property registry with full transparency
- **Search & Filter**: Find properties by unique ID or city location
- **Update Records**: Modify existing property information with audit trails
- **Ownership Tracking**: Maintain transparent ownership history

### 🔐 Blockchain Security

- **Immutable Records**: All property data secured by blockchain technology
- **Smart Contracts**: Automated property management through chaincode
- **Multi-Organization Support**: Built for consortium blockchain networks
- **Cryptographic Security**: Advanced security through Hyperledger Fabric

### 🌐 Web Interface

- **User-Friendly Dashboard**: Intuitive web interface for property management
- **Real-time Updates**: Live synchronization with blockchain network
- **RESTful API**: Complete backend API for integration
- **Responsive Design**: Cross-platform web application

## 📋 Property Data Structure

Each property in the registry contains:

| Field       | Description                            | Type   |
| ----------- | -------------------------------------- | ------ |
| **ID**      | Unique property identifier             | String |
| **Address** | Complete property address              | String |
| **City**    | City location                          | String |
| **Size**    | Property size (sqft/acres)             | String |
| **Owner**   | Current owner name                     | String |
| **Type**    | Property type (Residential/Commercial) | String |

## 🏗️ System Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Web Client    │    │   API Server    │    │   Blockchain    │
│   (Frontend)    │◄──►│   (Backend)     │◄──►│   (Fabric)      │
│                 │    │                 │    │                 │
│ • HTML/CSS/JS   │    │ • Node.js       │    │ • Chaincode     │
│ • User Interface│    │ • Express       │    │ • Ledger        │
│ • Property Forms│    │ • REST APIs     │    │ • Smart Contract│
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### Components

1. **Frontend** (`fabcar-client/`): Web-based user interface
2. **Backend** (`api-server/`): Node.js REST API server
3. **Chaincode** (`chaincode-javascript/`): Smart contracts for property management
4. **Network**: Hyperledger Fabric test network configuration

## 🚀 Quick Start

### Prerequisites

- **Node.js** (v18+ recommended)
- **Docker** & **Docker Compose**
- **Hyperledger Fabric** (v2.5+)
- **Git**

### Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/blockproperty-fabric.git
   cd blockproperty-fabric
   ```

2. **Start the Blockchain Network**

   ```bash
   ./startFabric.sh javascript
   ```

3. **Install Backend Dependencies**

   ```bash
   cd api-server
   npm install
   ```

4. **Initialize the Network**

   ```bash
   node enrollAdmin.js
   node registerUser.js
   ```

5. **Start the API Server**

   ```bash
   npm start
   ```

6. **Launch the Web Interface**
   - Open `fabcar-client/index.html` in VS Code
   - Use Live Server extension to serve the frontend
   - Access the application at `http://localhost:5500`

## 📁 Project Structure

```
blockproperty-fabric/
├── 📁 api-server/              # Backend REST API
│   ├── index.js               # Main server file
│   ├── package.json           # Dependencies
│   ├── enrollAdmin.js         # Admin enrollment
│   ├── registerUser.js        # User registration
│   ├── createProperty.js      # Property creation
│   ├── queryProperty.js       # Property queries
│   ├── updateProperty.js      # Property updates
│   └── 📁 wallet/             # User credentials
├── 📁 chaincode-javascript/   # Smart Contracts
│   ├── index.js               # Chaincode entry point
│   ├── package.json           # Chaincode dependencies
│   └── 📁 lib/
│       ├── fabcar.js          # Original fabcar contract
│       └── propertyTracker.js # Property management contract
├── 📁 fabcar-client/          # Frontend Web App
│   ├── index.html             # Main web interface
│   └── styles.css             # Styling
├── startFabric.sh             # Network startup script
├── networkDown.sh             # Network shutdown script
└── README.md                  # This file
```

## 🔧 API Endpoints

| Method | Endpoint                       | Description              |
| ------ | ------------------------------ | ------------------------ |
| GET    | `/queryAllProperties`          | Get all properties       |
| GET    | `/queryProperty/:id`           | Get property by ID       |
| GET    | `/queryPropertiesByCity/:city` | Get properties by city   |
| POST   | `/createProperty`              | Create new property      |
| PUT    | `/updateProperty`              | Update existing property |

## 🎯 Use Cases

- **Real Estate Agencies**: Maintain transparent property listings
- **Government Registries**: Official property registration systems
- **Property Investors**: Track investment portfolios
- **Legal Compliance**: Immutable audit trails for legal requirements
- **Insurance Companies**: Verify property details for coverage

## 🛠️ Technology Stack

- **Blockchain**: Hyperledger Fabric v2.5+
- **Smart Contracts**: Node.js/JavaScript
- **Backend**: Node.js, Express.js
- **Frontend**: HTML5, CSS3, JavaScript
- **Database**: CouchDB (world state)
- **Containerization**: Docker

## 📊 Network Components

- **Organizations**: Org1, Org2
- **Peers**: peer0.org1, peer0.org2
- **Orderer**: orderer.example.com
- **CA**: Certificate Authorities for each org
- **Channel**: mychannel
- **Chaincode**: PropertyContract

## 🔒 Security Features

- **Identity Management**: X.509 certificates
- **Access Control**: Organization-based permissions
- **Data Integrity**: Cryptographic hashing
- **Audit Trails**: Complete transaction history
- **Consensus**: RAFT ordering service

## 🏁 Getting Started Guide

1. Ensure Docker is running
2. Navigate to project directory
3. Execute `./startFabric.sh javascript`
4. Install API dependencies with `npm install`
5. Enroll admin and register user
6. Start the backend server
7. Open web interface with Live Server

## 🔧 Network Management

**Start Network:**

```bash
./startFabric.sh javascript
```

**Stop Network:**

```bash
./networkDown.sh
```

**Check Running Containers:**

```bash
docker ps
```

**Access CouchDB:**

- URL: http://localhost:5984/\_utils/
- Username: `admin`
- Password: `adminpw`

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

## 📞 Support

For questions, issues, or contributions, please:

- 📧 Open an issue on GitHub
- 💬 Join our community discussions
- 📖 Check the documentation

## 🙏 Acknowledgments

- **Hyperledger Fabric Community** for the blockchain framework
- **IBM** for Hyperledger Fabric development
- **Original Fabcar Sample** for the foundation code

---
## Helper Repository

[Hyperledger Fabric Fabcar Repository](https://github.com/YEASIN49/Hyperledger-Fabric-Fabcar.git)

**Built with ❤️ using Hyperledger Fabric**

_Securing property records with blockchain technology_
