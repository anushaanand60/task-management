# Task Board - Task Management Application

![Task Board Screenshot](https://github.com/anushaanand60/task-management/raw/main/images/Task_Management.png)

A comprehensive task management board application that enables users to organize tasks across three status columns: To Do, In Progress, and Done. Users can create, update, delete, and drag-and-drop tasks to manage their workflow efficiently.

## Live Demo

Access the deployed application at:  
[https://task-management-sigma-mauve.vercel.app](https://task-management-sigma-mauve.vercel.app)

## Features

### Task Organization
- **Column-based workflow**: View tasks in categorized columns (To Do, In Progress, Done)
- **Drag and drop**: Intuitive interface for updating task status
- **Real-time counters**: Task count displayed for each column

### Task Management
- **Create tasks**: Add new tasks with title and optional description
- **Edit tasks**: Modify existing tasks through a form interface
- **Delete tasks**: Remove tasks with confirmation prompts
- **Status updates**: Change task status through UI or drag-and-drop

### User Experience
- **Loading indicators**: Visual feedback during API operations
- **Error handling**: Clear messaging for failed operations

## Technologies Used

### Frontend
- React with Vite
- Tailwind CSS
- React Beautiful DnD
- React hooks (useState, useEffect) for state management
- Axios for API calls

### Backend
- Python with Flask
- Flask-CORS
- RESTful API with JSON responses
- In-memory data storage

## Project Structure

```
task-management/
│
├── backend/                # Python backend
│   └── api.py              # Flask server with RESTful endpoints
│
├── frontend/               # React frontend
│   ├── public/             # Public assets
│   ├── src/
│   │   ├── api/            # API services
│   │   │   └── tasksApi.js # API service for tasks
│   │   ├── components/     # React components
│   │   │   ├── AddTaskForm.jsx    # Form for creating new tasks
│   │   │   ├── EditTaskForm.jsx   # Form for editing existing tasks
│   │   │   ├── TaskBoard.jsx      # Main board component
│   │   │   ├── TaskCard.jsx       # Individual task card component
│   │   │   └── TaskColumn.jsx     # Column component
│   │   ├── pages/          # Page components
│   │   │   ├── Index.jsx   # Main page component
│   │   │   └── NotFound.jsx # 404 page component
│   │   ├── App.css
│   │   ├── App.jsx         # Main application component
│   │   ├── index.css
│   │   └── main.jsx        # Entry point
│   ├── .gitignore
│   ├── package.json
│   ├── tailwind.config.js
│   └── vite.config.js
```

## Setup and Installation

### Prerequisites
- Node.js
- Python
- npm or bun package manager

### Clone the Repository
```bash
git clone https://github.com/yourusername/task-management.git
cd task-management
```

### Frontend Setup
1. Navigate to frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Create environment configuration:
```bash
echo "VITE_API_URL=https://task-management-idiz.onrender.com" > .env
```
For local development, use:
```bash
echo "VITE_API_URL=http://localhost:8000" > .env
```

4. Start development server:
```bash
npm run dev
```
The frontend will be available at http://localhost:8080.

### Backend Setup
1. Navigate to backend directory:
```bash
cd backend
```

2. Create and activate virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install Python dependencies:
```bash
pip install flask flask-cors
```

4. Start the backend server:
```bash
python api.py
```
The backend will be available at http://localhost:8000.

## Deployment

| Component | Platform | URL |
|-----------|----------|-----|
| Frontend  | Vercel   | [https://task-management-sigma-mauve.vercel.app](https://task-management-sigma-mauve.vercel.app) |
| Backend   | Render   | [https://task-management-idiz.onrender.com](https://task-management-idiz.onrender.com) |

## Implementation Details

### Backend (Flask)

The backend is built with Flask and provides a simple RESTful API for task management.

- **In-memory Data Storage**: Uses a Python list to store task objects
- **Comprehensive Logging**: Uses Python's logging module to track API calls and responses
- **Error Handling**: Returns appropriate HTTP status codes (404, 400) with error messages
- **Cross-Origin Support**: Implemented with CORS to allow frontend requests
- **Request Logging**: Logs all incoming request headers and bodies for debugging

### Frontend

#### State Management

The application uses React Context API for state management. The TaskContext provides:

- Tasks data
- Loading and error states
- Functions for CRUD operations
- Function for moving tasks between columns

#### Drag and Drop

React Beautiful DnD is implemented through several components:

- **DragDropContext**: Wraps the main board component and manages drag events
- **Droppable**: Each column (`TaskColumn`) is a drop target with unique droppable ID
- **Draggable**: Each task card (`TaskCard`) is a draggable item with unique ID
- **Status Update**: When a task is dragged to a new column, its status is updated via API

#### Component Architecture

- **TaskBoard**: Main component that renders columns and handles drag-and-drop logic
- **TaskColumn**: Represents a status column (To Do, In Progress, Done) with droppable area
- **TaskCard**: Individual task item with draggable functionality and action buttons
- **AddTaskForm**: Form component for creating new tasks within a specific column
- **EditTaskForm**: Form component for modifying existing tasks

## Usage

- **View Tasks**: Tasks are displayed in three columns: To Do, In Progress, and Done.
- **Create a Task**: Click the "Add Task" button in any column to create a new task.
- **Edit a Task**: Click on a task card to open the edit modal.
- **Delete a Task**: Click the delete icon on a task card.
- **Move a Task**: Drag a task card from one column and drop it into another.

## Demo Video

Watch the demo video here: [Task Board Demo Video](https://drive.google.com/file/d/1Xo_AJI8Go4l934IWPvOSL54GmcOs-GPE/view?usp=sharing)

## Future Enhancements

### Planned Features
1. **User Authentication**
   - Secure login system
   - User-specific task boards

2. **Enhanced Task Management**
   - Priority levels (Low/Medium/High)
   - Due dates and deadlines

3. **Advanced UI**
   - Dark mode support
