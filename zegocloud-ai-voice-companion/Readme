# Building an AI Voice Companion Using ZEGOCLOUD Conversational AI APIs

**Author:** Hasan Mukhtar\
**Technology Stack:** Node.js, Express.js, Kotlin, Android Studio,
ZEGOCLOUD SDK, REST APIs\
**Documentation Type:** API Integration & Technical Implementation
Guide\
**Project:** AI Voice Companion -- Android Application

------------------------------------------------------------------------

## 1. Project Overview

This project demonstrates the development of an AI-powered voice
companion for Android using ZEGOCLOUD's Conversational AI services.

The application enables users to communicate with an AI agent through
real-time voice conversations. It combines speech recognition, a Large
Language Model (LLM), text-to-speech (TTS), and real-time communication
(RTC) functionality.

The implementation uses a Node.js backend to communicate with ZEGOCLOUD
services and an Android application developed using Kotlin to provide
the user interface and manage voice sessions.

### Key Features

-   Real-time voice interaction between users and an AI agent.
-   Customizable AI personality through LLM system prompts.
-   Speech recognition for processing user input.
-   Text-to-speech functionality for generating AI responses.
-   Secure token generation for application authentication.
-   Live conversation updates displayed in the Android interface.
-   Start and stop controls for managing voice sessions.

### System Architecture

The application follows a client-server architecture:

1.  **Android Client:** Handles the user interface, microphone
    permissions, RTC connection and conversation display.
2.  **Node.js Backend:** Manages API requests, credentials, token
    generation and AI agent registration.
3.  **ZEGOCLOUD Services:** Provide real-time communication and
    conversational AI capabilities.
4.  **AI Processing Services:** Handle speech recognition, language
    processing and speech generation.

The backend acts as an intermediary between the Android application and
the external services, keeping sensitive credentials away from the
client application.

------------------------------------------------------------------------

## 2. ZEGOCLOUD Project Configuration

The first step is configuring a project in the ZEGOCLOUD developer
console.

### Procedure

1.  Create or sign in to a ZEGOCLOUD developer account.
2.  Create a new project and select the video and voice calling
    solution.
3.  Choose the UI Kit or SDK integration approach.
4.  Open the project dashboard and locate the application credentials.
5.  Enable the In-App Chat service through Service Management.
6.  Navigate to the Conversational AI documentation and review the
    voice-call quick-start instructions.

The project dashboard provides credentials such as:

-   **App ID:** Identifies the application.
-   **App Sign:** Application-related credential.
-   **Server Secret:** Sensitive credential used by the backend for
    authorized operations.

For this implementation, the App ID and Server Secret are configured on
the backend.

> **Security consideration:** Server secrets must never be exposed in
> Android source code, public repositories, or client-side configuration
> files. They should be stored in environment variables and excluded
> from version control.

------------------------------------------------------------------------

## 3. Backend Development and API Configuration

The backend is developed using Node.js and Express.js. It manages
communication with ZEGOCLOUD services and provides endpoints that the
Android application can access.

### 3.1 Project Structure

The backend project contains the following main files:

  File               Responsibility
  ------------------ --------------------------------------------------------
  `.env`             Stores environment variables and sensitive credentials
  `package.json`     Defines project metadata and dependencies
  `tokenHelper.js`   Handles secure token generation
  `index.js`         Implements server configuration and API routes

### 3.2 Environment Variables

The `.env` file stores configuration values required by the backend.

These include:

-   ZEGOCLOUD App ID.
-   Server Secret.
-   AI Agent API base URL.
-   Local server URL.
-   Application port.

Environment variables allow credentials and configuration settings to
remain separate from the application source code.

### 3.3 Backend Dependencies

The project uses the following Node.js packages:

  Package      Purpose
  ------------ ------------------------------------------------
  Express.js   Creates the backend HTTP server and API routes
  Axios        Sends HTTP requests to external APIs
  dotenv       Loads environment variables
  Nodemon      Automatically restarts the development server

The built-in Node.js Crypto module is also used for cryptographic
operations.

### 3.4 Authentication and Token Generation

Authentication is an important part of the integration because both the
Android client and AI agent must join the appropriate communication
session.

A dedicated token helper module is implemented to generate
authentication tokens.

The process involves:

1.  Receiving the application ID, user identifier and server secret.
2.  Preparing the token payload with relevant identity and expiration
    information.
3.  Generating the required cryptographic values.
4.  Encrypting and formatting the token according to the provider's
    expected structure.
5.  Returning the generated token for authorized session access.

The backend also generates request signatures for API communication.
These signatures include timestamp and random nonce information to help
protect requests against replay attacks.

The implementation follows the provider's documented authentication
format.

------------------------------------------------------------------------

## 4. AI Agent Registration and Configuration

The next step is registering an AI agent through the ZEGOCLOUD
Conversational AI API.

The agent is configured with three main components:

### 4.1 Automatic Speech Recognition (ASR)

ASR converts the user's spoken input into text so that the language
model can process it.

The project uses an ASR provider configured through the agent settings.
The selected configuration is intended to support recognition of
different speaking accents.

### 4.2 Large Language Model (LLM)

The LLM processes recognized text and generates conversational
responses.

The project uses a configurable language model and a system prompt to
define the agent's behavior.

For example, the system prompt specifies:

-   The agent's name and role.
-   Its conversational personality.
-   The preferred response style.
-   A short response-length limit.
-   Appropriate use of emojis.

This configuration makes the AI agent's behavior customizable without
changing the Android application's core implementation.

### 4.3 Text-to-Speech (TTS)

The TTS component converts the generated text into spoken audio.

The project configures a supported speech-generation provider and
selects a voice suitable for the companion application.

Together, ASR, LLM and TTS form the conversational processing pipeline.

### 4.4 Registering the Agent

The backend sends the agent configuration to the provider using the
documented API operation.

The configuration contains the selected ASR, LLM and TTS settings.

After successful registration, the backend stores the returned agent
identifier.

Saving this identifier avoids unnecessary repeated registration when
starting subsequent conversations.

------------------------------------------------------------------------

## 5. Creating and Managing Voice Sessions

Once the AI agent has been registered, the backend provides an endpoint
that the Android application calls to initiate a conversation.

### Session Initialization Workflow

1.  The Android application sends a start-call request to the backend.
2.  The request includes the room ID, user ID and user stream
    information.
3.  The backend retrieves the registered AI agent identifier.
4.  A unique identifier is generated for the AI agent's session.
5.  The backend generates an authentication token for the agent.
6.  The session configuration is prepared with the required room and
    stream information.
7.  The backend sends the create-agent-instance request to ZEGOCLOUD.
8.  The provider returns an agent instance identifier.
9.  The backend returns the relevant session information to the Android
    application.

The session configuration also controls conversation synchronization,
event callbacks and interruption behavior.

For example, interruption mode allows the AI agent to stop speaking when
the user begins talking, supporting a more natural conversational
experience.

### Backend API Responsibilities

The backend exposes application endpoints for:

-   Generating a user authentication token.
-   Initiating an AI agent session.
-   Returning session information to the Android client.

These endpoints separate application-side operations from privileged
provider API requests.

------------------------------------------------------------------------

## 6. Android Client Integration Using Kotlin

The Android application is developed in Kotlin using Android Studio.

The ZEGOCLOUD SDK provides the real-time communication functionality,
while the backend API handles authentication and AI session
initialization.

### 6.1 Android Permissions and Dependencies

The application requires permissions for:

-   Internet access.
-   Network state access.
-   Microphone recording.

The required SDK repository and dependency are added to the Gradle
configuration using the provider's integration documentation.

An HTTP client library is also integrated to communicate with the
Node.js backend.

### 6.2 Establishing a Voice Connection

The application initializes the communication engine using the
configured App ID.

It then configures audio processing features:

-   **Acoustic Echo Cancellation (AEC):** Reduces echo during
    conversations.
-   **Automatic Gain Control (AGC):** Adjusts microphone input levels.
-   **Active Noise Suppression (ANS):** Reduces unwanted background
    noise.

The application requests an authentication token from the backend before
joining the communication room.

After successful connection, it publishes the user's audio stream and
requests the backend to create the AI agent instance.

### 6.3 Processing Conversation Events

The Android client registers event handlers to monitor communication
status and incoming streams.

When the AI agent joins the room, the application subscribes to its
audio stream.

The application also processes incoming conversation messages to display
recognized speech and AI-generated responses.

The received message payload is parsed to extract the relevant command
identifier, response content and completion status.

A message buffer is maintained to collect response segments before
displaying the completed message in the conversation interface.

### 6.4 Displaying Conversation Messages

The application dynamically creates text views to display user and AI
messages.

Different visual styles are applied to distinguish between the two
participants.

The conversation container is placed inside a scrollable layout. After a
new message is added, the interface automatically scrolls to the latest
conversation entry.

The application also provides controls to start and stop voice sessions.

------------------------------------------------------------------------

## 7. Testing and Troubleshooting

After completing the backend and Android implementation, both components
must be tested together.

### Backend Testing

1.  Open a terminal in the server directory.
2.  Install the required dependencies.
3.  Start the Node.js application.
4.  Verify that the server reports a successful startup.
5.  Check API responses when requesting tokens and creating AI sessions.

### Android Testing

1.  Connect an Android device to the development environment.
2.  Configure the backend URL using the computer's local IPv4 address
    when testing over Wi-Fi.
3.  Grant microphone permissions.
4.  Launch the application.
5.  Start a voice session.
6.  Verify that the AI agent joins and produces an audio response.
7.  Stop the session and verify that the communication engine is
    released.

### Common Issues

  -----------------------------------------------------------------------
  Issue                               Recommended action
  ----------------------------------- -----------------------------------
  Missing Node.js dependencies        Run the package installation
                                      command

  Invalid API credentials             Verify the App ID and Server Secret

  Token generation failure            Check the token configuration and
                                      expiration values

  Android cannot reach backend        Verify the server address, port and
                                      local network connectivity

  Microphone unavailable              Check Android runtime permissions

  AI agent does not join              Verify agent registration, session
                                      configuration and token validity

  Conversation messages are not       Inspect incoming event payloads and
  displayed                           message parsing logic
  -----------------------------------------------------------------------

For local development, Android network security settings may need to
permit HTTP traffic to the development server. Production deployments
should use HTTPS.

------------------------------------------------------------------------

## 8. Project Outcome

The completed application demonstrates an integrated AI voice
communication workflow using an Android client, a Node.js backend and
ZEGOCLOUD Conversational AI services.

The project involved practical implementation of:

-   REST API communication and backend integration.
-   Authentication and token generation.
-   Environment-based credential management.
-   AI agent registration and configuration.
-   LLM, ASR and TTS integration.
-   Android SDK integration using Kotlin.
-   Real-time audio streaming and event handling.
-   API testing and troubleshooting.

**Author's Contribution:** Independently developed and demonstrated the
technical implementation through an instructional video as part of the
ITech Aspirant channel, including backend setup, API integration,
Android client development and troubleshooting.

> **Documentation Note:** This guide is adapted from the author's
> original technical tutorial. API operation names, authentication
> formats and configuration parameters should always be checked against
> the relevant provider documentation and SDK version before
> implementation.
