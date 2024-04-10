---
# Trivia Backend

Trivia Backend is a Node.js application built with Express and MongoDB (using Mongoose) to support the Trivia web and mobile application game.

## Features

- **Categories of Questions**: Users can choose categories of questions they want to answer.
- **Earn Points**: Users earn points by correctly answering questions, which can be withdrawn into their bank account.
- **Free Games**: Minimum of 5 free games available for users every day.
- **Premium Access**: Premium users have access to unlimited games, leaderboard, and daily login rewards in points.
- **Points Conversion**: Users can convert earned points into cash after reaching a certain threshold.

### Additional Features for Premium Users

- **Unlimited Games**: Premium users can play unlimited games.
- **Leaderboard**: Premium users have access to the leaderboard.
- **Online Multiplayer**: Premium users can play online multiplayer or solo mode.
- **Partnership Mode**: Premium users can invite a friend to play against an online player. Questions are randomly selected from 1 to 10, and the winner takes all the points.

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/maximilliansolutionltd/Trivia-Backend.git
   ```

2. Install dependencies:

   ```bash
   cd trivia-backend
   npm install
   ```

3. Set up environment variables by creating a `.env` file and adding the necessary variables (e.g., MongoDB connection URI, API keys, etc.).

4. Start the server:

   ```bash
   npm start
   ```

## API Endpoints

The backend exposes the following API endpoints:

### User Authentication and Management
- `/api/auth/register (POST)`: Register a new user with username, email, and password. Returns a JWT token for authentication.
- `/api/auth/login (POST)`: Log in an existing user with email and password. Returns a JWT token for authentication.
- `/api/auth/logout (POST)`: Log out the current user and invalidate the JWT token.
- `/api/auth/user (GET)`: Get current user details including username, email, points, membership status, etc.
- `/api/auth/forgot-password (POST)`: Send reset password instructions to the user's email.

### Game Management
- `/api/games (GET)`: Get a list of available games including free and premium games, with details like name, category, description, and point rewards.
- `/api/games/start (POST)`: Start a new game session by selecting a game ID.
- `/api/games/end (POST)`: End a game session, calculate points based on correct answers, and update user's points.

### Question Handling
- `/api/questions/categories (GET)`: Get a list of available question categories like sports, science, history, etc.
- `/api/questions/random (GET)`: Get a random question from OpenAI based on the selected category ID.
- `/api/questions/submit-answer (POST)`: Submit the user's answer for evaluation, provide feedback, and update points.
- `/api/questions/explain-answer (POST)`: Get an explanation for the correct answer from OpenAI after the user submits their answer.

### User Points and Rewards
- `/api/points/earn (POST)`: Earn points based on correct answers, daily logins, and completing tasks.
- `/api/points/convert (POST)`: Convert points into cash or virtual currency.
- `/api/points/history (GET)`: Get the user's points history including earned, spent, and converted points.

### Premium Features
- `/api/premium/upgrade (POST)`: Upgrade to premium membership with payment details.
- `/api/premium/games/unlock (POST)`: Unlock additional games for premium users.
- `/api/premium/multiplayer/invite (POST)`: Invite a friend for multiplayer mode by providing their email or username.

### Leaderboard
- `/api/leaderboard (GET)`: Get the leaderboard rankings of users based on points or game wins.

### Profile Management
- `/api/profile/update (PUT)`: Update user profile information like username, email, password, and profile picture.
- `/api/profile/delete (DELETE)`: Delete the user's account and all associated data.

### Notification Management
- `/api/notifications (GET)`: Get notifications for the user including game reminders, rewards, and announcements.
- `/api/notifications/mark-as-read (POST)`: Mark notifications as read or unread.

### OpenAI Integration
- `/api/openai/generate-question (POST)`: Generate a new question using the OpenAI API based on the provided category and difficulty level.
- `/api/openai/explain-answer (POST)`: Get an explanation for the correct answer from OpenAI based on the question and user's answer.

Refer to the API documentation or codebase for detailed information on each endpoint's functionality and usage.

## Contributing

Contributions are welcome! If you have suggestions, feature requests, or bug reports, please open an issue or create a pull request.

## License

This project is licensed under the [MIT License].

---