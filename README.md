# Form Builder Application

A full-stack form builder application that allows users to create, edit, and view custom forms with drag-and-drop functionality.

## Features

- **Create Forms**: Build custom forms with various input types (Text, Email, Password, Number, Date)
- **Edit Forms**: Modify existing forms and rearrange inputs
- **View Forms**: Fill out forms with real-time validation
- **Drag & Drop**: Rearrange form inputs using drag-and-drop
- **Sections**: Group inputs into logical sections
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Input Validation**: Built-in validation for email, number, and date fields
- **Grid Layout**: Inputs displayed in a 2-column grid layout (responsive)
- **Maximum Inputs**: Supports up to 20 inputs per form

## Technology Stack

### Frontend
- React.js 18.2.0
- React Router DOM 6.15.0
- React Beautiful DnD 13.1.1 (for drag-and-drop)
- CSS3

### Backend
- Node.js
- Express.js 4.18.2
- MongoDB with Mongoose 7.5.0
- CORS 2.8.5

## Prerequisites

Before you begin, ensure you have the following installed:
- Node.js (v14 or higher)
- npm or yarn
- MongoDB (local installation or MongoDB Atlas account)

## Installation & Setup

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd form-builder
```

### 2. Backend Setup

```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create .env file
cp .env.example .env

# Edit .env file and add your MongoDB connection string
# Default: MONGODB_URI=mongodb://localhost:27017/formbuilder
```

### 3. Frontend Setup

```bash
# Navigate to frontend directory (from project root)
cd frontend

# Install dependencies
npm install
```

### 4. Database Setup

If using MongoDB locally:
```bash
# Start MongoDB service
mongod
```

If using MongoDB Atlas:
- Create a free cluster at https://www.mongodb.com/cloud/atlas
- Get your connection string
- Update the MONGODB_URI in backend/.env

## Running the Application

### Start Backend Server

```bash
# From backend directory
cd backend
npm start

# Or for development with auto-restart
npm run dev
```

The backend server will start on http://localhost:5000

### Start Frontend Development Server

```bash
# From frontend directory (in a new terminal)
cd frontend
npm start
```

The frontend will start on http://localhost:3000 and automatically open in your browser.

## Project Structure

```
form-builder/
├── backend/
│   ├── models/
│   │   └── Form.js           # MongoDB schema for forms
│   ├── routes/
│   │   └── forms.js          # API routes for CRUD operations
│   ├── server.js             # Express server configuration
│   ├── package.json
│   └── .env.example
│
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── HomePage.js       # List all forms
│   │   │   ├── HomePage.css
│   │   │   ├── CreateForm.js     # Create new form
│   │   │   ├── CreateForm.css
│   │   │   ├── EditForm.js       # Edit existing form
│   │   │   ├── ViewForm.js       # View and submit form
│   │   │   └── ViewForm.css
│   │   ├── App.js                # Main app component with routing
│   │   ├── App.css
│   │   ├── index.js
│   │   └── index.css
│   └── package.json
│
└── README.md
```

## API Endpoints

### Forms

- **GET** `/api/forms` - Get all forms
- **GET** `/api/forms/:id` - Get a single form by ID
- **POST** `/api/forms` - Create a new form
- **PUT** `/api/forms/:id` - Update a form
- **DELETE** `/api/forms/:id` - Delete a form

## Usage Guide

### Creating a Form

1. Navigate to the home page
2. Click "Create New Form"
3. Enter a form title
4. Click "Add New Input" to add fields
5. Configure each input:
   - Select input type (Text, Email, Password, Number, Date)
   - Enter a title for the input
   - Add placeholder text (optional)
   - Specify a section name (optional)
6. Drag and drop to reorder inputs
7. Click "Save Form" when done

### Editing a Form

1. From the home page, click "Edit" on any form
2. Modify the title or inputs as needed
3. Add new inputs or delete existing ones
4. Rearrange inputs using drag-and-drop
5. Click "Update Form" to save changes

### Viewing a Form

1. From the home page, click "View" on any form
2. Fill out the form fields
3. The form validates inputs based on their type
4. Click "Submit Form" to submit

## Features in Detail

### Input Types Supported
- **Text**: Free-form text input
- **Email**: Email validation
- **Password**: Masked password input
- **Number**: Numeric input with validation
- **Date**: Date picker

### Validation
- Email fields validate email format
- Number fields only accept numeric values
- Date fields require a valid date selection

### Drag and Drop
- Use the drag handle (⋮⋮) to reorder inputs
- Works in both Create and Edit modes

### Sections
- Group related inputs together
- Sections appear with a title and divider
- Optional feature for better organization

## Environment Variables

Create a `.env` file in the backend directory:

```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/formbuilder
```

## Troubleshooting

### Backend won't start
- Ensure MongoDB is running
- Check if port 5000 is available
- Verify .env file exists and contains correct values

### Frontend won't connect to backend
- Ensure backend server is running
- Check proxy setting in frontend/package.json
- Verify CORS is properly configured

### MongoDB connection errors
- Check MongoDB service is running
- Verify connection string in .env
- Ensure database permissions are correct

## Future Enhancements

Potential features for future versions:
- Store form submission responses
- Export forms to PDF
- Form templates
- Conditional logic for inputs
- File upload support
- Multi-page forms
- Form analytics
- User authentication
- Share forms via unique URLs

## License

This project is created as part of a coding assignment.

## Contact

For questions or issues, please contact the development team.
