# PG Life

[View this project on GitHub](https://github.com/Akumar-51/pg_life)

PG Life is a responsive web application for browsing paying guest (PG) accommodations in Indian cities. Visitors can search listings and view property details without an account. Registered users can save properties they are interested in and manage them from a personal dashboard.

This project was created as part of the Internshala Full Stack Web Development internship training.

## Features

- **Find PGs by city:** Search by city name or browse the featured cities: Delhi, Mumbai, Bengaluru, and Hyderabad.
- **Browse listings:** View property cards with rent, ratings, gender availability, and the number of interested users.
- **Sort results:** Sort a city's listings by rent (low to high or high to low) or rating (high to low).
- **View property details:** See the property's address, description, amenities, ratings, testimonials, and photos.
- **Create an account and sign in:** Register and log in through the site navigation.
- **Save properties:** Signed-in users can toggle their interest in a property from listing and detail pages. The interested-user count updates with the action.
- **Manage saved properties:** View profile information and saved properties on the dashboard, and remove a saved property there.
- **Responsive navigation and layout:** Browse the application on desktop and mobile-sized screens.

Browsing listings and details does not require an account. Signing in is required to save properties and access the dashboard.

## Technology

- PHP
- MySQL or MariaDB
- HTML and CSS
- JavaScript and AJAX
- Bootstrap (bundled in the project)
- jQuery (bundled in the project)

## Run locally

The application uses PHP sessions and MySQL, and expects to be served from a web server. XAMPP is one way to provide Apache, PHP, and MySQL/MariaDB.

1. Install and start Apache and MySQL/MariaDB.
2. Copy the repository's `PGLIFE` directory into the web server's document root, keeping the directory name `PGLIFE`.
3. Create a database named `pg_life` and import [`pg_life_database/pg_life.sql`](pg_life_database/pg_life.sql).
4. Configure the database connection in [`PGLIFE/includes/database_connect.php`](PGLIFE/includes/database_connect.php) to match your local host, username, password, and database. The included defaults are `127.0.0.1`, `root`, an empty password, and `pg_life`.
5. Open `http://localhost/PGLIFE/` in a browser.

The application contains root-relative `/PGLIFE/...` links in some pages and scripts, so it expects the `PGLIFE` directory directly under the web server document root. If you instead serve the whole repository from a subdirectory, those links may need adjusting.

## Project structure

```text
PGLIFE/
├── api/                    # Signup, login, and interested-property handlers
├── css/                    # Page and shared stylesheets
├── img/                    # City, property, amenity, and interface images
├── includes/               # Shared page components and database connection
├── js/                     # Front-end behavior and AJAX requests
├── index.php               # Home page and city search
├── property_list.php       # City property listings
├── property_detail.php     # Individual property details
├── dashboard.php           # Signed-in user's profile and saved properties
└── logout.php              # Sign out

pg_life_database/
└── pg_life.sql             # Database schema and sample data
```

## Database overview

The SQL dump creates and seeds the `pg_life` database tables for users, cities, properties, amenities, property amenities, testimonials, and saved (interested) properties. It includes sample listings for Delhi, Mumbai, Bengaluru, and Hyderabad.

## Notes

- The PHP application expects the database to be available before loading pages that query listings or user data.
- The project does not include a Composer or Node.js dependency installation step; its front-end libraries are included under `PGLIFE/`.
