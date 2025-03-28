# Decentralized Data Processing Backend Service

## Project Overview

This backend service is a specialized data processing and management system designed to work with decentralized data sources, primarily leveraging IPFS (InterPlanetary File System) and MongoDB for data storage and retrieval. The service is focused on fetching, processing, and storing task-related data with built-in retry and queue mechanisms.

### Key Features
- Automatic task data retrieval from decentralized sources
- IPFS content extraction and processing
- MongoDB data storage
- Round-based processing with retry logic
- Configurable task tracking

### Use Cases
- Decentralized data indexing
- Blockchain and Web3 data processing
- Automated task data synchronization
- Resilient data extraction pipelines

## Getting Started

### Prerequisites
- Node.js (v14+ recommended)
- MongoDB
- IPFS access
- Web3 storage account

### Installation
1. Clone the repository
```bash
git clone https://github.com/your-repo/koiitoadot.git
cd koiitoadot
```

2. Install dependencies
```bash
yarn install
```

3. Configure environment variables
Copy `.env.example` to `.env` and fill in the required values:
```
TASK_ID=your_task_id
MONGODB_URI=mongodb://localhost:27017/your_database
```

### Running the Service
Start the service in development mode:
```bash
yarn start
```

## Project Structure
```
├── api/                # API endpoint implementations
│   ├── saveDataToMongoDB.js
│   └── sendData.js
├── helpers/            # Utility and helper functions
│   ├── cleanData.js
│   ├── dataFromCid.js
│   └── getTaskData.js
├── mdbScripts/         # MongoDB utility scripts
│   ├── collectionCopier.js
│   ├── removeDuplicates.js
│   └── uniqueIndexCreator.js
├── index.js            # Main application entry point
└── queue.js            # Queue management for data processing
```

## Technologies Used
- Node.js
- Express.js
- MongoDB
- Web3.storage
- IPFS
- Axios
- Async Queue Management

## Core Workflow
1. Retrieve task data for a specific task ID
2. Extract data from IPFS using content identifiers (CIDs)
3. Process and clean the retrieved data
4. Save processed data to MongoDB
5. Automatically manage processing rounds
6. Handle retry mechanisms for data retrieval

## Authentication
This service uses environment-based configuration. Ensure secure storage of:
- Task ID
- MongoDB connection strings
- Web3 storage credentials

## Deployment Considerations
- Use environment-specific configurations
- Implement robust error handling
- Consider containerization with Docker
- Set up appropriate MongoDB replica sets for scalability

## Error Handling
The service includes built-in retry mechanisms:
- Automatic retry on data retrieval failures
- Configurable wait times between retry attempts
- Logging of processing rounds and status

## Monitoring
- Console logs provide real-time processing information
- Track current processing round
- Log retry attempts and wait times

## License
This project is licensed under the ISC License.

## Contributing
1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## Contact
For more information, please contact the repository maintainers.