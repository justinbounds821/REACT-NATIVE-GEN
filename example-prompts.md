# Example Prompts for React Native Generator

## Simple Apps

### 1. Todo List App
```json
{
  "prompt": "Create a todo list app with the following features:\n- Add new todos\n- Mark todos as complete/incomplete\n- Delete todos\n- Filter by all/active/completed\n- Clean modern UI with animations\n- Use local storage for persistence",
  "projectName": "TodoMaster"
}
```

### 2. Weather App
```json
{
  "prompt": "Build a weather app that:\n- Shows current weather for user's location\n- 5-day forecast\n- Search for cities\n- Beautiful weather animations\n- Temperature unit toggle (C/F)\n- Weather alerts if available",
  "projectName": "WeatherNow"
}
```

### 3. Calculator App
```json
{
  "prompt": "Create a calculator app with:\n- Basic operations (+, -, ×, ÷)\n- Scientific mode with advanced functions\n- History of calculations\n- Dark/light theme toggle\n- Haptic feedback on button press",
  "projectName": "CalcPro"
}
```

## Medium Complexity Apps

### 4. Fitness Tracker
```json
{
  "prompt": "Develop a fitness tracking app featuring:\n- Workout logging (sets, reps, weight)\n- Exercise library with categories\n- Progress charts and statistics\n- Workout plan creator\n- Timer for rest periods\n- Calendar view of workouts\n- Export data functionality",
  "projectName": "FitTracker"
}
```

### 5. Recipe Manager
```json
{
  "prompt": "Build a recipe management app with:\n- Add/edit/delete recipes\n- Categories (breakfast, lunch, dinner, dessert)\n- Ingredients list with quantities\n- Step-by-step cooking instructions\n- Prep/cook time\n- Serving size calculator\n- Search and filter\n- Favorite recipes\n- Shopping list generator",
  "projectName": "RecipeBook"
}
```

### 6. Expense Tracker
```json
{
  "prompt": "Create an expense tracking app including:\n- Add income/expenses with categories\n- Monthly budget setting\n- Visual charts (pie, bar) for spending\n- Transaction history with search\n- Recurring transactions\n- Export to CSV\n- Multiple currency support\n- Budget alerts",
  "projectName": "ExpenseManager"
}
```

## Complex Apps

### 7. Social Media Feed
```json
{
  "prompt": "Build a social media feed app with:\n- User authentication screens (login/signup)\n- Main feed with posts (text, images)\n- Like and comment functionality\n- User profiles with follower counts\n- Create new posts with image picker\n- Pull to refresh\n- Infinite scroll\n- Share posts\n- Dark mode support\n- Push notification UI",
  "projectName": "SocialConnect"
}
```

### 8. E-Learning Platform
```json
{
  "prompt": "Develop an e-learning app featuring:\n- Course listing with categories\n- Video player for lessons\n- Course progress tracking\n- Quiz/assessment screens\n- Notes taking during lessons\n- Bookmarks for important content\n- Search functionality\n- User profile with achievements\n- Offline content download UI\n- Discussion forum UI",
  "projectName": "LearnHub"
}
```

### 9. Music Player
```json
{
  "prompt": "Create a music player app with:\n- Library view (songs, albums, artists, playlists)\n- Now playing screen with album art\n- Playback controls (play, pause, next, previous, shuffle, repeat)\n- Progress bar with seek\n- Queue management\n- Create and edit playlists\n- Search functionality\n- Recently played\n- Equalizer UI\n- Sleep timer\n- Mini player at bottom",
  "projectName": "MusicFlow"
}
```

## Specialized Apps

### 10. Meditation App
```json
{
  "prompt": "Build a meditation app including:\n- Guided meditation sessions list\n- Timer with bell sounds\n- Breathing exercises with visual guide\n- Daily reminders\n- Progress tracking (streak counter)\n- Calming background sounds\n- Session history\n- Mood tracker\n- Beautiful, minimalist UI with calming colors",
  "projectName": "MindfulMe"
}
```

### 11. Plant Care App
```json
{
  "prompt": "Create a plant care app with:\n- Add plants with photos\n- Care schedules (watering, fertilizing)\n- Plant identification using camera\n- Care tips database\n- Reminder notifications UI\n- Plant health diary\n- Weather integration for care tips\n- Community forum UI\n- Plant wish list",
  "projectName": "PlantPal"
}
```

### 12. Travel Planner
```json
{
  "prompt": "Develop a travel planning app featuring:\n- Trip creation and management\n- Itinerary builder (day by day)\n- Places to visit with map integration\n- Budget tracker for trips\n- Packing lists\n- Document storage (tickets, bookings)\n- Weather forecast for destinations\n- Currency converter\n- Offline mode indicators\n- Share trip with friends UI",
  "projectName": "TravelMate"
}
```

## UI/UX Focused Prompts

### 13. Animated Onboarding
```json
{
  "prompt": "Create an app with beautiful animated onboarding:\n- 4-5 onboarding screens\n- Smooth transitions between screens\n- Skip and next buttons\n- Progress indicators\n- Animated illustrations\n- Get started button on last screen\n- After onboarding, show a simple home screen\nFocus on smooth animations and modern design",
  "projectName": "OnboardingDemo"
}
```

### 14. Component Library
```json
{
  "prompt": "Build a component showcase app displaying:\n- Custom button variations (primary, secondary, outlined, sizes)\n- Input fields with validations\n- Cards with different layouts\n- Modal/dialog examples\n- Loading states and skeletons\n- Toast notifications\n- Tab navigation examples\n- Custom switches and checkboxes\n- Animated components\nMake it a reference for UI components",
  "projectName": "UIKit"
}
```

### 15. Dashboard App
```json
{
  "prompt": "Create a dashboard app with:\n- Stats cards with icons and numbers\n- Charts (line, bar, pie) using mock data\n- Recent activity list\n- Quick action buttons\n- User profile section\n- Dark/light theme toggle\n- Responsive grid layout\n- Pull to refresh\n- Beautiful gradients and shadows",
  "projectName": "DashboardPro"
}
```

## Google Docs Example

For longer, more detailed requirements, create a Google Doc with content like:

```
# My Awesome App Requirements

## Overview
I want to build a comprehensive task management app that goes beyond simple todos.

## Features

### Task Management
- Create tasks with title, description, due date, priority
- Subtasks support
- Tags/labels for organization
- Drag and drop to reorder
- Bulk actions (delete, complete, move)

### Projects
- Group tasks into projects
- Project templates
- Progress visualization
- Team member assignment UI

### Calendar Integration
- Calendar view of tasks
- Drag tasks to different dates
- Week/month views
- Today widget

### Notifications
- Due date reminders
- Custom notification times
- Daily summary

### Analytics
- Productivity charts
- Completion rates
- Time tracking
- Weekly/monthly reports

### UI Requirements
- Clean, modern interface
- Smooth animations
- Gesture support
- Customizable themes
- Tablet optimization

### Technical Requirements
- Offline support UI
- Data sync indicators
- Export functionality
- Search with filters
- Performance optimized for large datasets
```

Then use:
```json
{
  "useGoogleDoc": true,
  "googleDocId": "YOUR_GOOGLE_DOC_ID_HERE",
  "projectName": "TaskMasterPro"
}
```

## Tips for Better Results

1. **Be Specific**: The more details you provide, the better the output
2. **Mention UI/UX**: Describe the look and feel you want
3. **List Features Clearly**: Use bullet points for features
4. **Include Technical Requirements**: Mention specific libraries if needed
5. **Describe User Flows**: Explain how users will interact with the app

## Note on Limitations

- The generator creates UI/frontend code only
- Backend/API integration code is not included (but UI for it is)
- Database operations are mocked
- Authentication is UI-only
- Focus is on creating beautiful, functional UI components