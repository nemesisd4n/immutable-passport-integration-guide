# The Complete Guide to Integrating Immutable Passport

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Step 1: Create a Simple Application or git clone a repository of the simple application](#step-1-create-a-simple-application)
- [Step 2: Register Your Application on Immutable Developer Hub](#step-2-register-your-application-on-immutable-developer-hub)
- [Step 3: Install and Initialize the Passport Client](#step-3-install-and-initialize-the-passport-client)
- [Step 4: Log in a User with Passport](#step-4-log-in-a-user-with-passport)
- [Step 5: Display User Information](#step-5-display-user-information)
- [Step 6: Log Out a User](#step-6-log-out-a-user)
- [Step 7: Initiate a Transaction from Passport](#step-7-initiate-a-transaction-from-passport)
- [Conclusion](#conclusion)
- [Further Resources](#further-resources)

---

## Introduction

In the dynamic realm of blockchain technology, a beacon of innovation known as **Immutable Passport** emerges, purpose-built to revolutionize gaming applications. This ingenious tool equips developers with the means to seamlessly infuse blockchain-based authentication and transaction capabilities into their gaming projects, ushering in a new era of security and functionality.

![Immutable Passport](https://assets-global.website-files.com/646557ee455c3e16e4a9bcb9/646557ee455c3e16e4a9c260_passport_3.jpeg)

Welcome to our comprehensive guide on **Immutable Passport Integration**. Whether you're a game developer eager to fortify your application's security and enhance its flexibility, or a tech enthusiast poised to explore the possibilities of blockchain-driven gaming, this guide is your gateway to unlocking the full potential of Immutable Passport.

Within these well-crafted steps, we'll guide you through the entire journey, from creating a basic application to orchestrating transactions with Immutable Passport. By the time you've completed this guide, you'll have the skills to seamlessly integrate Immutable Passport's potent features into your gaming application, making it more robust and secure.

So, get ready to embark on a journey to unleash the capabilities of Immutable Passport, enriching your gaming application and expanding the frontiers of blockchain technology in the gaming world. Let's dive in and get started! 🎮🚀

## Prerequisites

Before you begin the integration process, ensure you have the following prerequisites:

1. A code editor for making changes to your application.
2. Node.js and npm (Node Package Manager) installed on your machine.
3. A Next.js application ready for integration or the ability to create one from scratch.

Step 1: Create a Simple Application or Clone a Repository

Before you begin integrating Immutable Passport into your application, you'll need to create a basic application using Next.js. You can do this in one of two ways:

**Option 1: Create a New Next.js Application from Scratch**

1. Create a new directory for your project:

   ```bash
   # Create a new directory for your project
   mkdir my-nextjs-app
   ```

2. Navigate to the project directory:

   ```bash
   # Navigate to the project directory
   cd my-nextjs-app
   ```

3. Initialize a new Node.js project. This will generate a `package.json` file:

   ```bash
   # Initialize a new Node.js project
   npm init -y
   ```

4. Install Next.js and React:

   ```bash
   # Install Next.js and React
   npm install next react react-dom
   ```

5. Create a "pages" directory to host your application pages:

   ```bash
   # Create a "pages" directory to host your application pages
   mkdir pages
   ```

6. Create a basic Next.js page in the "pages" directory. For example, let's create a homepage:

   **pages/index.js**: This is a basic Next.js page.

   ```jsx
   // pages/index.js
   function Home() {
     return <div>Welcome to the world of Immutable Passport Integration!</div>;
   }

   export default Home;
   ```

   **Start your Next.js application**

   ```bash
   npm run dev
   ```

   In case you get error while running the command, perform the below operations,

7. Update your `package.json` to include the "dev" script. Open the `package.json` file and add the "scripts" section like this:

   ```json
   "scripts": {
     "dev": "next dev"
   },
   ```

   Your `package.json` should look something like this:

   ```json
   {
     "name": "my-nextjs-app",
     "version": "1.0.0",
     "scripts": {
       "dev": "next dev"
     },
     "dependencies": {
       "next": "^12.0.3",
       "react": "^17.0.2",
       "react-dom": "^17.0.2"
     }
   }
   ```

8. Save the `package.json` file.

9. Start your Next.js application:

   ```bash
   npm run dev
   ```

Now you have a basic Next.js application ready to integrate Immutable Passport. If you prefer to start with a pre-built application, please refer to "Option 2" below.

By following these steps and defining the "dev" script in your `package.json`, you should be able to start your Next.js application without encountering the "Missing script: 'dev'" error.
Your application will be running at [http://localhost:3000](http://localhost:3000).

**Option 2: Clone a Repository with a Pre-built Next.js Application**

If you prefer to use a pre-built Next.js application, you can clone a repository. Replace the repository URL with the one you want to use.

1. Clone the repository:

   ```bash
   # Clone the repository
   git clone <repository-url>
   ```

2. Navigate to the project directory:

   ```bash
   # Navigate to the project directory
   cd <repository-directory>
   ```

3. Install project dependencies:

   ```bash
   # Install project dependencies
   npm install
   ```

4. Start the application:

   ```bash
   # Start the application
   npm run dev
   ```

   Your pre-built application will be running at [http://localhost:3000](http://localhost:3000).

Make sure your application is set up and running.

## Step 2: Application Registration on Immutable Developer Hub

Before you can harness the power of Immutable Passport for your application, you must undertake the essential step of registering your application within the Immutable Developer Hub. Here's a formal guide:

1. **Login to Immutable Developer Hub:**

   If you are not yet a member of the Immutable Developer Hub, you will need to create an account. This is how you can do it:

   - Navigate to the [Immutable Developer Hub website](https://hub.immutable.com/).
   - Click the "Sign In" option. If you are not a registered user, select either "Create Account" or "Sign Up" to initiate the registration process.
   - Follow the prompts on the screen to complete the registration successfully.

   Once your account is established, return to the Immutable Developer Hub homepage and sign in using your newly created credentials.

2. **Register a New Application:**

   To ensure a successful application registration, carefully follow these guidelines:

   - Locate and click on the "My Applications" or "Create New Application" option, depending on the specific interface of the Immutable Developer Hub.
   - Choose "Web Application" as the designated application type, as this is the currently available option.
   - Provide a unique and distinctive name for your application within the "Client Name" field. Ensure that it is easily recognizable.
   - In the "Logout URLs" section, input valid URLs that enable users to log out securely. These URLs should direct users to the logout feature of your application.
   - In the "Callback URLs" section, verify that your application's callback URL aligns with the information you provided during the initialization of the Passport client. This step is critical for a seamless integration process.
   - Follow the instructions presented on-screen to complete the registration process. This may include agreeing to terms and conditions or specifying additional settings based on the specific requirements of your application.

3. **Obtain Client Credentials:**

   Upon the successful registration of your application, you will receive essential client credentials required for the integration of Immutable Passport. These credentials are pivotal for authentication and authorization purposes.

   As part of this registration process, you will be assigned a "Client ID." Ensure that you save this Client ID as it is a fundamental requirement for the upcoming steps.

4. **Incorporate the Client ID into Your Application's Environment Variables:**

   For the secure storage and utilization of the Client ID within your application, it is strongly recommended that you include it in your environment variables. Here is the appropriate method:

   - Create a `.env` file in your project directory if one does not already exist.
   - Within the `.env` file, insert the following line, substituting "Your_Client_ID" with the actual Client ID received:

     ```plaintext
     IMMUTABLE_CLIENT_ID="Your_Client_ID"
     ```

   - Save the `.env` file.

   Ensure that your application is configured to effectively retrieve and utilize environment variables. The precise configuration of this process may vary according to your chosen programming language and framework. Should you require guidance on this matter, it is advisable to refer to the documentation relevant to your technology stack.

By diligently following these steps, you will have successfully registered your application on the Immutable Developer Hub and procured the indispensable Client ID, the key to the integration of Immutable Passport into your application. Safeguard your credentials meticulously and adhere to the recommended best practices for the management of environment variables. Your journey into the world of blockchain gaming is now underway! 🚀🔐

## Step 3: Install and Initialize the Passport Client

In your application, you'll need to install the necessary dependencies and initialize the Passport Client to interact with Immutable Passport. Here's a code snippet example to guide you through this process:

**1. Install Required Dependencies:**

First, ensure you have the required dependencies installed. You can add these to your project's `package.json` file and install them using npm or yarn:

```bash
npm install @imtbl/sdk
npm install ethers
```

**2. Initialize the Passport Client:**

Next, you need to initialize the Passport Client.

```javascript
import { config, passport } from "@imtbl/sdk";
import { ethers } from "ethers";

// Define the Passport Client Configuration
const passportConfig = {
  clientId: process.env.IMMUTABLE_CLIENT_ID as string,
  redirectUri: "http://localhost:3000/callback",  // Set your application's callback URL
  logoutRedirectUri: "http://localhost:3000/",   // Set the URL for user logout
  scope: "openid offline_access email transact",
  audience: "platform_api",  // Specify the audience for Passport
  baseConfig: new config.ImmutableConfiguration({
    environment: config.Environment.SANDBOX, // Set the appropriate environment value (e.g., SANDBOX or PRODUCTION)
    apiKey: "", // Provide the apiKey if required by your configuration
  }),
};

// Create an instance of the Passport Client
const passportInstance = new passport.Passport(passportConfig);

// Connect to the EVM (Ethereum Virtual Machine)
const passportProvider = passportInstance.connectEvm();
```

**Explanation:**

- Make sure you replace "http://localhost:3000/callback" and "http://localhost:3000/" with the actual callback and logout URLs for your application.

- Set the appropriate environment value for `config.Environment`. Common values are `SANDBOX` for testing and `PRODUCTION` for production use.

- If your configuration requires an API key, provide it in the `apiKey` field.

By following these steps and using the provided code snippet, you'll successfully initialize the Passport Client for your application, allowing it to interact with Immutable Passport.

## Step 4: Log in a User with Passport

To log in a user, you can use the following code snippet. This code initializes the Passport provider and handles the user authentication process:

```javascript
import { passportProvider } from "@/lib/immutable";

// Define a function to initiate user authentication
const loginWithPassport = async () => {
  try {
    // Request user account access through Passport provider
    const accounts = await passportProvider.request({
      method: "eth_requestAccounts",
    });

    // If successful, the user is connected
    console.log("User Connected");
    console.log(accounts);
  } catch (error) {
    // Handle authentication errors
    errorHandling("Authentication error", error);
  }
};

// Call the login function when needed to trigger the authentication process
loginWithPassport();
```

**Explanation:**

- The code above defines the `loginWithPassport` function, which triggers the user authentication process.

- It uses `passportProvider.request` to request user account access. The `"eth_requestAccounts"` method is used for this purpose.

- If the user successfully authenticates, their Ethereum accounts will be stored in the `accounts` variable.

- You can customize the success and error handling as per your application's requirements.

By following these steps and using the provided code snippet, you'll be able to log in a user using Passport and handle the user authentication process effectively in your application.

## Step 5: Display User Information

After a user is authenticated, you can access and display their information, including the ID token and access token. Use the provided code to fetch and display user data:

Use the code snippet below to fetch and display user information:

```javascript
import { passportInstance } from "@/lib/immutable";

// Define a function to fetch and display user information
const displayUserInfo = async () => {
  try {
    // Fetch the user's profile information
    const userProfile = await passportInstance.getUserInfo();

    // Fetch the access token and ID token
    const accessToken = await passportInstance.getAccessToken();
    const idToken = await passportInstance.getIdToken();

    // Display user information in your application
    console.log("User Profile:", userProfile);
    console.log("Access Token:", accessToken);
    console.log("ID Token:", idToken);
  } catch (error) {
    // Handle errors when fetching user information
    errorHandling("Error fetching user information", error);
  }
};

// Call the function when needed to display user information
displayUserInfo();
```

**Explanation:**

- The code defines the `displayUserInfo` function, which fetches the user's profile information, access token, and ID token.

- You can customize the code to use this information as needed in your application, such as displaying the user's name, email, or other relevant data.

- Proper error handling is in place to manage any issues that may occur when fetching user information.

By following these steps and using the provided code snippet, you'll be able to fetch and display user information after authentication in your application.

## Step 6: Log Out a User

To log out a user from your application, you can use the following code:

```javascript
import { passportInstance } from "@/lib/immutable";

// Define a function to log out a user
const logoutUser = () => {
  // Trigger the Passport logout process
  passportInstance.logout();
};

// Call the function when the user initiates the logout process
logoutUser();
```

**Explanation:**

- The code above defines the `logoutUser` function, which triggers the Passport logout process.

- When the function is called, Passport will handle the user's logout process, ensuring that the user's session is terminated.

- Make sure to call this function when a user initiates the logout process in your application, such as clicking a "Log Out" button.

By following these steps and using the provided code snippet, you'll be able to implement user logout functionality in your application effectively.

## Step 7: Initiate a Transaction from Passport

To initiate a transaction using Passport, you need to provide the necessary transaction data and parameters:

Use the code snippet below to initiate a transaction using Passport:

```javascript
import { passportProvider, initiateTransaction } from "@/lib/immutable";

// Define a function to initiate a transaction
const initiatePassportTransaction = async (transactionData) => {
  try {
    // Use the 'initiateTransaction' function to send the transaction data
    const transactionHash = await initiateTransaction(transactionData);

    // Handle the transaction response, e.g., display the transaction hash
    console.log("Transaction Hash:", transactionHash);
  } catch (error) {
    // Handle errors when initiating the transaction
    errorHandling("Transaction initiation error", error);
  }
};

// Sample transaction data (customize as needed)
const transactionData = {
  to: "0xYourRecipientAddress", // Recipient's Ethereum address
  value: "0.1", // Amount to send (in Ether)
  data: "0xabcdef123456", // Transaction data (hex encoded)
  gas: 21000, // Gas limit
  // Add more parameters as needed
};

// Call the function to initiate the transaction with the provided data
initiatePassportTransaction(transactionData);
```

Please replace `"0xYourRecipientAddress"`, `"0.1"`, `"0xabcdef123456"`, and `21000` with the actual transaction details you want to use. This code serves as a template, and you can customize the `transactionData` object with your specific transaction parameters.

**Explanation:**

- In the code snippet above, we define the `initiatePassportTransaction` function, which is responsible for initiating a transaction using Immutable Passport.

- This function utilizes the `initiateTransaction` function, an essential part of the Immutable Passport library, to send the transaction data to the blockchain.

- To use this code effectively, you must customize the `transactionData` object. This object serves as a container for the specific data and parameters required for your transaction. It includes details such as the recipient's Ethereum address, the transaction value (in Ether), the data payload (hex-encoded), the gas limit, and other relevant parameters. It's crucial to tailor this object to your specific transaction needs.

- The code also incorporates error handling to gracefully manage any issues that may arise during the initiation of the transaction. Proper error handling ensures that unexpected situations are handled effectively.

By following this code and customizing the `transactionData` object with the necessary values for your use case, you can seamlessly initiate transactions using Immutable Passport within your application. This process is an integral part of interacting with blockchain technology, and ensuring that the transaction details are accurate is vital to the success of your transactions.

## Conclusion

A hearty congratulations are in order! 🚀 You've reached the finish line and successfully completed the integration of Immutable Passport into your application. It's a remarkable achievement that deserves a round of applause! 🎉🎉🎉

Throughout this guide, you've mastered the process of connecting your application to Immutable Passport, ensuring user authentication, obtaining crucial user data, and even diving into the realm of initiating transactions. Immutable Passport has now unlocked a realm of possibilities for you to explore within the Immutable protocol.

## Further Resources

To delve deeper into this exciting journey, access comprehensive documentation and official resources available at [Immutable Passport Documentation](https://docs.immutable.com/docs/zkevm/products/passport/). These resources provide a wealth of knowledge and insights.

Your commitment to this guide is greatly appreciated. Should you encounter any questions or obstacles on your path, please feel free to seek assistance from the welcoming Immutable community or dedicated support. Your journey into the world of blockchain possibilities has just begun! 🌟

---
