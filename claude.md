# Personal Growth Task Tracker

## Project Overview
A React-based web application for tracking daily tasks across work, planning, and personal growth dimensions. The app focuses on helping users build consistent habits across mental, physical, social, and personal growth areas while managing work and planning tasks.

## Core Features

### 1. Tab Navigation
The app has three main tabs:
- **Planner Tab**: For planning and scheduling tasks
- **Work Tab**: For daily work-related tasks
- **Personal Tab**: For personal growth tracking with 5 specialized cards

### 2. Personal Growth Cards
The Personal tab contains 5 distinct growth cards:
1. **Mental Growth**: Tasks related to learning, reading, meditation, etc.
2. **Physical Growth**: Exercise, nutrition, health-related tasks
3. **Social Growth**: Social interactions, networking, community involvement
4. **Personal Growth**: Self-improvement, hobbies, personal projects
5. **Trying New Things**: Challenges, new experiences, stepping out of comfort zone

Each card includes:
- Default tasks (pre-populated)
- User-added tasks
- Task type designation: "Permanent" (persists daily) or "Daily" (resets daily)
- Checkboxes for completion tracking

### 3. Task Management
**Planner & Work Tabs:**
- Have default tasks that persist
- Users can add daily tasks
- Daily tasks are wiped at midnight (12:00 AM)
- Checkboxes reset at midnight

**Personal Tab:**
- Default tasks in each growth card
- Users can add new tasks
- Tasks can be marked as:
  - **Permanent**: Appear every day
  - **Daily**: One-time tasks that disappear after completion or at midnight

### 4. Time-Based Reset System
- All checkboxes uncheck at 12:00 AM
- Planner and Work tabs: Daily tasks are removed at midnight
- Personal tab: Daily tasks are removed at midnight, permanent tasks persist
- Automatic daily refresh mechanism

### 5. Archive System
- Previous days' data is archived at midnight
- Users can view historical data
- Archive includes completed/uncompleted tasks from past dates
- Calendar-based navigation for viewing archived days

### 6. Social Features
- Add friends by username or ID
- View friends' Personal tabs in separate tabs
- See friends' progress and tasks (read-only view)
- Friend list management

## Technical Requirements

### Frontend Framework
- **React** (with hooks)
- Modern JavaScript (ES6+)

### State Management
- React Context API or useState/useReducer
- LocalStorage for data persistence

### Key Functionality
1. **Midnight Reset Logic**: Use `setInterval` or scheduled check to detect midnight
2. **Data Persistence**: LocalStorage to save user data, tasks, and archives
3. **Dynamic Task Creation**: Forms to add new tasks with type selection
4. **Archive System**: Date-keyed storage structure for historical data
5. **Friend System**: User profiles and friend connections (mock data or future backend integration)

### Data Structure
```javascript
{
  user: {
    id: string,
    name: string,
    friends: [userId]
  },
  planner: {
    defaultTasks: [{ id, text, checked }],
    dailyTasks: [{ id, text, checked, date }]
  },
  work: {
    defaultTasks: [{ id, text, checked }],
    dailyTasks: [{ id, text, checked, date }]
  },
  personal: {
    mentalGrowth: {
      defaultTasks: [{ id, text, checked, isPermanent }],
      userTasks: [{ id, text, checked, isPermanent, date }]
    },
    physicalGrowth: { /* same structure */ },
    socialGrowth: { /* same structure */ },
    personalGrowth: { /* same structure */ },
    tryingNewThings: { /* same structure */ }
  },
  archive: {
    "YYYY-MM-DD": { /* snapshot of all tasks for that day */ }
  }
}
```

## User Experience Guidelines

### Design Principles
- Clean, minimalist interface
- Easy checkbox interactions
- Clear visual distinction between permanent and daily tasks
- Intuitive tab navigation
- Responsive design for mobile and desktop

### Color Coding (Suggested)
- Mental Growth: Blue/Purple
- Physical Growth: Green
- Social Growth: Orange/Yellow
- Personal Growth: Pink/Red
- Trying New Things: Teal/Cyan

### Interaction Patterns
- Click checkbox to mark task complete
- Add button in each section for new tasks
- Modal or inline form for task creation
- Delete/edit icons for user-created tasks
- Badge indicators for permanent vs. daily tasks

## Development Guidelines

### Code Organization
```
src/
  components/
    Tabs/
      PlannerTab.jsx
      WorkTab.jsx
      PersonalTab.jsx
      FriendTab.jsx
    Cards/
      GrowthCard.jsx
    Tasks/
      TaskItem.jsx
      TaskForm.jsx
    Archive/
      ArchiveViewer.jsx
  context/
    AppContext.jsx
  hooks/
    useMidnightReset.js
    useLocalStorage.js
  utils/
    dateUtils.js
    archiveUtils.js
  App.jsx
  index.js
```

### Best Practices
- Use functional components with hooks
- Keep components small and focused
- Extract reusable logic into custom hooks
- Comment complex logic (especially midnight reset)
- Use meaningful variable names
- Handle edge cases (date changes, timezone issues)

### Testing Considerations
- Test midnight reset logic (use mock dates)
- Verify localStorage persistence
- Check task addition/deletion
- Validate archive system
- Test friend viewing features

## Future Enhancements (Optional)
- Backend integration for true multi-user support
- Push notifications for daily resets
- Streak tracking for consistent task completion
- Analytics dashboard for growth tracking
- Export data to CSV/JSON
- Dark mode toggle
- Customizable growth categories
- Goal setting and progress tracking

## Getting Started

1. Initialize React app: `npx create-react-app planner-app`
2. Install additional dependencies if needed (e.g., date-fns, uuid)
3. Set up folder structure as outlined above
4. Implement core functionality in order:
   - Basic tab navigation
   - Task display and checkbox interaction
   - Task creation forms
   - LocalStorage persistence
   - Midnight reset logic
   - Archive system
   - Friend features

## Notes for Claude
- Always validate date/time logic carefully
- Use UTC or local time consistently
- Test midnight reset edge cases
- Consider browser timezone differences
- Keep friend data mock/local until backend is ready
- Make the UI intuitive - this is a daily-use app
- Default tasks should be meaningful and inspirational
- Allow full customization - users should own their growth journey
