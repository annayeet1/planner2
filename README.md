# Personal Growth Task Tracker

A React-based web application for tracking daily tasks across work, planning, and personal growth dimensions. Stay consistent with your growth journey across mental, physical, social, and personal development.

## Features

### 📋 Three Main Tabs
- **Planner Tab**: Plan and schedule your daily tasks
- **Work Tab**: Track work-related tasks
- **Personal Tab**: Monitor growth across 5 key dimensions

### 🌱 Personal Growth Cards
1. **Mental Growth** 🧠 - Learning, reading, meditation
2. **Physical Growth** 💪 - Exercise, nutrition, health
3. **Social Growth** 👥 - Connections, networking, community
4. **Personal Growth** 🌱 - Self-improvement, hobbies, projects
5. **Trying New Things** ✨ - Challenges and new experiences

### ⚙️ Smart Task Management
- **Default Tasks**: Pre-set tasks that appear daily
- **Daily Tasks**: One-time tasks that reset at midnight
- **Permanent Tasks**: Custom tasks that persist daily
- **Checkbox Reset**: All checkboxes automatically uncheck at midnight
- **Task Types**: Mark tasks as permanent (daily recurring) or one-time

### 🕛 Automatic Midnight Reset
- Daily tasks are removed at 12:00 AM
- All checkboxes reset at midnight
- Previous day's data is automatically archived
- Clean slate every morning

### 📚 Archive System
- View historical data from previous days
- Calendar-based navigation
- Complete task history with completion status
- Track your consistency over time

### 👥 Social Features
- Add friends to your network
- View friends' Personal Growth tabs
- See their tasks and progress (read-only)
- Stay motivated together

## Installation

1. Install dependencies:
```bash
npm install
```

2. Start the development server:
```bash
npm start
```

3. Open [http://localhost:3000](http://localhost:3000) in your browser

## Building for Production

```bash
npm run build
```

This creates an optimized production build in the `build` folder.

## How to Use

### Adding Tasks

**Planner & Work Tabs:**
- Click "Add Task" button
- Enter task description
- Task will be marked as "daily" and removed at midnight

**Personal Tab:**
- Click "Add Task" in any growth card
- Choose "Permanent" for recurring daily tasks
- Choose "One-time" for tasks that reset at midnight
- Enter task description and submit

### Managing Tasks
- ✓ Check the checkbox to mark tasks complete
- × Click the delete button to remove custom tasks
- Default tasks cannot be deleted

### Viewing Archive
- Click "View Archive" in the header
- Select a date from the list
- Review all tasks and completion status from that day

### Adding Friends
- Go to the Friends tab
- Click "Add Friend"
- Enter friend's name
- Click on a friend to view their Personal Growth cards

## Data Persistence

All data is stored locally in your browser using localStorage:
- Tasks and completion status
- Custom tasks you've added
- Friend connections
- Archive history

Your data persists across browser sessions but is specific to each browser.

## Customization

### Modifying Default Tasks

Edit the default tasks in [src/context/AppContext.js](src/context/AppContext.js):

```javascript
const DEFAULT_PLANNER_TASKS = [
  { id: 'p1', text: 'Your custom task', checked: false },
  // Add more tasks...
];
```

### Changing Colors

Modify the color scheme in [src/App.css](src/App.css) by editing the growth card classes:

```css
.growth-card.mental {
  border-left-color: #667eea; /* Change this color */
}
```

## Browser Support

Works on all modern browsers including:
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Microsoft Edge 79+

## Technical Details

- **React**: v18.2.0
- **State Management**: React Context API
- **Storage**: Browser localStorage
- **Reset Logic**: Interval-based midnight detection
- **Styling**: Pure CSS (no frameworks)

## Project Structure

```
src/
├── components/
│   ├── Tabs/
│   │   ├── PlannerTab.js
│   │   ├── WorkTab.js
│   │   ├── PersonalTab.js
│   │   └── FriendTab.js
│   ├── Cards/
│   │   └── GrowthCard.js
│   ├── Tasks/
│   │   ├── TaskItem.js
│   │   └── TaskForm.js
│   └── Archive/
│       └── ArchiveViewer.js
├── context/
│   └── AppContext.js
├── utils/
│   └── dateUtils.js
├── App.js
├── App.css
└── index.js
```

## Future Enhancements

- Backend integration for real friend connections
- Push notifications for daily reset
- Streak tracking and analytics
- Data export (CSV/JSON)
- Dark mode
- Customizable growth categories
- Goal setting and milestones

## License

This project is open source and available for personal use.

## Contributing

Feel free to fork this project and customize it for your needs!
