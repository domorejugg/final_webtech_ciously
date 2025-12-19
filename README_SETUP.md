# Ciously - Setup Instructions

## Database Setup

1. Open phpMyAdmin in your browser (usually at `http://localhost/phpmyadmin`)

2. Import the database schema:
   - Go to the "Import" tab
   - Select the file `database/schema.sql`
   - Click "Go" to import

   OR manually create the database by running the SQL in `database/schema.sql`

3. Update database credentials in `php/config.php` if needed:
   - Default: localhost, root, no password, database name: ciously_db
   - Modify the constants if your setup is different

## File Structure

```
ciously/
├── signup.html              # Sign Up page
├── discovery-wall.html      # Discovery Wall page with sliding albums
├── index.html              # Landing page (updated with Rate button and testimonials)
├── css/
│   ├── signup.css          # Sign Up page styles
│   ├── discovery-wall.css  # Discovery Wall styles
│   └── components/
│       └── cards.css       # Updated with testimonials grid and Rate button styles
├── js/
│   ├── signup.js           # Sign Up form validation
│   ├── discovery-wall.js   # Discovery Wall animation logic
│   └── testimonials.js     # Dynamic testimonial cards generation
├── php/
│   ├── config.php          # Database configuration
│   └── signup.php          # Registration handler
└── database/
    └── schema.sql          # Database schema
```

## Features Implemented

### 1. Sign Up Page
- Matches the design with dark purple/blue gradient background
- Fields: Username, Email, Password, Confirm Password
- Form validation (client-side and server-side)
- Stores user data in MySQL database

### 2. Discovery Wall Page
- "DISCOVERY WALL" title with blue underline effect
- Sliding album covers animation (left to right, infinite loop)
- Album covers from WallPack1 and WallPack2
- Hover to pause animation
- Responsive design

### 3. Landing Page Updates
- Replaced "Agree/Disagree" buttons with single "Rate" button
- "What are people saying?" section now shows multiple testimonial cards
- Each card displays an album cover and a comment (truncated to fit space)
- Comments are dynamically generated with different album covers

## Notes

- The testimonials grid will automatically populate when the page loads via `testimonials.js`
- All comments are limited to ~180 characters to ensure they fit properly in the card space
- The old testimonial card content in index.html will be replaced when JavaScript runs
