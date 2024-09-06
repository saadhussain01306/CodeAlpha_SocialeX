# SocialeX

**SocialeX** is a full-fledged social media application built using the MERN stack. The app allows users to create accounts, post stories and images, interact with other users, and engage in real-time chats. With features like secure authentication, notifications, and real-time updates, SocialeX provides a dynamic social platform experience.

## Features

- **Secure Authentication**: Users can securely sign up and log in using bcrypt for password hashing and JWT tokens for session management.
- **Post and Story Sharing**: Users can create posts and stories with captions, view posts from others, and delete their own posts.
- **Real-Time Chat**: Instant messaging with other users powered by Socket.io for real-time communication.
- **Post Interaction**: Like and comment on posts, fostering user interaction.
- **Notifications**: Receive notifications for new messages and when other users post.
- **User Feed**: Browse and engage with content shared by other users.

## Project Structure

### Client (React)
```
client/
  ├── public/               # Static assets (images, icons, index.html)
  └── src/
      ├── components/       # Reusable components (e.g., Navbar, PostCard, Story, ChatBox)
      ├── pages/            # Page components for routes (e.g., Home, Profile, PostPage)
      ├── services/         # API and socket services (e.g., AuthService, PostService)
      ├── utils/            # Utility functions (e.g., token handling, date formatting)
      ├── App.js            # Main app component
      ├── index.js          # React entry point
      └── styles/           # Global and component-specific CSS styles
```

### Server (Node.js/Express)
```
server/
  ├── controllers/          # Functions to handle the API requests (e.g., AuthController, PostController)
  ├── middleware/           # JWT verification and other middlewares
  ├── models/               # Mongoose models (e.g., User, Post, Comment, Story)
  ├── routes/               # API routes (e.g., /auth, /posts, /comments)
  ├── socket/               # Socket.io setup for real-time chat and notifications
  ├── .env                  # Environment variables (e.g., JWT secret, MongoDB URI)
  └── index.js              # Entry point for the Express server
```

## Technologies Used

- **Front-end**: React.js, Axios for API requests, Socket.io for real-time chat, and CSS for styling.
- **Back-end**: Node.js, Express.js, JWT for authentication, bcrypt for password security, and Socket.io for real-time notifications.
- **Database**: MongoDB with Mongoose for data modeling (users, posts, comments, stories).
- **Authentication**: JWT tokens for session handling, bcrypt for password encryption.

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/saadhussain01306/SocialeX.git
   cd SocialeX
   ```

2. **Install dependencies for both client and server**
   - For the client:
     ```bash
     cd client
     npm install
     ```
   - For the server:
     ```bash
     cd server
     npm install
     ```

3. **Set up environment variables**
   Create a `.env` file in the `server/` directory with the following variables:
   ```bash
   PORT=5000
   MONGO_URI=your_mongo_db_uri
   JWT_SECRET=your_jwt_secret
   SOCKET_IO_PORT=5001
   ```

4. **Run the application**
   - Start the server:
     ```bash
     cd server
     npm run dev
     ```
   - Start the client:
     ```bash
     cd client
     npm start
     ```

## API Endpoints

### Authentication
- **POST** `/auth/register`: Registers a new user.
- **POST** `/auth/login`: Logs in a user and returns a JWT token.

### Posts
- **GET** `/posts`: Retrieves all posts.
- **POST** `/posts`: Creates a new post.
- **DELETE** `/posts/:id`: Deletes a specific post.

### Stories
- **GET** `/stories`: Retrieves all stories.
- **POST** `/stories`: Creates a new story.
- **DELETE** `/stories/:id`: Deletes a specific story.

### Comments
- **POST** `/posts/:id/comments`: Adds a comment to a post.
- **GET** `/posts/:id/comments`: Retrieves comments for a post.

### Real-Time Chat (Socket.io)
- Real-time private messaging and group chats with connected users.

## Security

- Passwords are encrypted using `bcrypt` before being stored in the database.
- JWT tokens are used to authenticate users for secure access to endpoints.


## License

This project is licensed under the MIT License.
