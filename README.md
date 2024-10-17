# EventLite

**EventLite** is a dynamic web application built using the **Java Spring Boot** framework, following the Model-View-Controller (MVC) architecture. It empowers users to organize their daily schedules efficiently, offering event and venue management features. Users can create, edit, and delete events, with each event associated with a specific venue that is displayed interactively on a map. Additionally, users can post tweets through a built-in Twitter integration, and the latest tweets are showcased on the homepage.

## Key Features
1. **Event Management:**
   - Create, update, and delete events.
   - Events store detailed information such as name, date, time, description, and venue.
   - Each event is linked to a venue for a seamless user experience.

2. **Venue Management:**
   - Create, edit, and remove venues.
   - Venues are displayed on an interactive map using the MapBox API.
   - Pop-up windows display venue details when clicked on the map.

3. **Twitter Integration:**
   - Post tweets to the built-in Twitter account using the Twitter4J API.
   - Display the five most recent tweets on the index page, offering a live feed to users.

4. **Interactive Map:**
   - Venues are visually represented on a map, enhancing the user experience by providing geographical context.
   - The MapBox API enables venue locations to be shown on a fully functional and responsive map interface.

5. **RESTful API:**
   - A RESTful API is provided for third-party integration, allowing external systems to interact with EventLite by creating, updating, or deleting events and venues.

## Architecture Overview

EventLite is structured around the **MVC (Model-View-Controller)** architectural pattern, ensuring clear separation of concerns between the application's components. **Spring Boot** simplifies the application setup and configuration, providing embedded servers and out-of-the-box tools for building and deploying the application.

### 1. **Model**
   - Defines the application's core data structure, including:
     - **Event Entity**: Contains fields like event name, date, description, and venue association.
     - **Venue Entity**: Represents venues with relevant attributes such as location, name, and description.
   - Acts as the backbone of the database, storing and retrieving data.

### 2. **Controller**
   - Manages HTTP requests, processes incoming data, and determines the appropriate response.
   - Retrieves data from the Model layer and inserts it into the front-end (View).
   - Handles CRUD operations for both events and venues, ensuring smooth interactions.

### 3. **View**
   - Provides the front-end UI, implemented using **Thymeleaf** templates.
   - Dynamically fetches data from the back-end to render interactive HTML pages for users.
   - Displays the event list, venue map, and Twitter timeline on the homepage.

## Technology Stack
- **Spring Boot**: Used to simplify application configuration, development, and deployment, providing an embedded Tomcat server.
- **Thymeleaf**: Enables dynamic content rendering on the front-end by accessing back-end data.
- **MapBox API**: Used to render interactive maps displaying venue locations with pop-up windows.
- **Twitter4J API**: Integrated to manage Twitter interactions, enabling tweet posting and retrieval of recent tweets.
- **RESTful API**: Exposes endpoints for managing events and venues programmatically.

## Getting Started

### Prerequisites
- Java 11+
- Maven 3.6+
- A Twitter Developer account (for Twitter4J API usage)
- A MapBox account with an API key

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/eventlite.git
   cd eventlite
   ```

2. Configure the application:
   - Set up your `application.properties` file in the `src/main/resources` directory with:
     - Database configurations.
     - MapBox API key.
     - Twitter API keys for Twitter4J integration.

3. Build the project with Maven:
   ```bash
   mvn clean install
   ```

4. Run the application using Spring Boot:
   ```bash
   mvn spring-boot:run
   ```

5. Access the application by navigating to:
   ```
   http://localhost:8080
   ```

## API Endpoints
### Event Management
- **GET** `/api/events`: Retrieve all events.
- **POST** `/api/events`: Create a new event.
- **PUT** `/api/events/{id}`: Update an existing event.
- **DELETE** `/api/events/{id}`: Delete an event by ID.

### Venue Management
- **GET** `/api/venues`: Retrieve all venues.
- **POST** `/api/venues`: Create a new venue.
- **PUT** `/api/venues/{id}`: Update an existing venue.
- **DELETE** `/api/venues/{id}`: Delete a venue by ID.

## Future Enhancements
- **User Authentication**: Add user login and role-based access control to enhance security.
- **Notification System**: Implement email or SMS notifications for event reminders.
- **Event Search**: Provide an advanced search feature to allow users to filter events by date, venue, or keywords.

## Contributing
Contributions are welcome! Feel free to open an issue or submit a pull request if you have suggestions or improvements.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
