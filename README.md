 Madadgar AI — Live Disaster Relief Dashboard

Madadgar AI is a real-time disaster relief and aid delivery monitoring dashboard designed to help relief teams visualize delivery activity, monitor affected/reached areas, and review verification and duplicate information from a centralized interface. The dashboard connects directly to Firebase Firestore and updates its statistics, delivery table, and interactive map as delivery records change 
🚨 Problem
During disaster-relief operations, delivery information can become fragmented across different records and systems. This can make it difficult for relief teams to understand:

- Where aid has already been delivered
- Which areas have been reached
- Which deliveries have been verified
- Whether duplicate delivery records exist
- How current delivery activity is changing over time

Manual monitoring can also make coordination more difficult when teams need a clear geographic and data-based overview.

 💡 Solution

Madadgar AI provides a centralized dashboard for monitoring disaster-relief deliveries in real time.

The dashboard:

- Reads delivery records directly from Firebase Firestore
- Updates dashboard statistics as Firestore data changes
- Displays delivery records in a structured table
- Visualizes delivery locations on an interactive map
- Shows verification and duplicate information when available
- Tracks delivery areas and geographic coordinates
- Supports delivery photos/images when available

The goal is to provide relief teams with a clearer, more current view of delivery activity without relying on manually refreshed data.

 ✨ Key Features

- 🔄 **Real-time Firestore synchronization** using `onSnapshot()`
- 📦 **Live delivery monitoring** from the `deliveries` collection
- 🗺️ **Interactive delivery map** with geographic markers
- 📋 **Dynamic delivery table** populated from Firestore
- ✅ **Verification status** based on available Firestore data
- ♻️ **Duplicate status** based on available Firestore data
- 📍 **Area tracking** for delivery records
- 📊 **Live dashboard statistics**
- 📷 **Photo/image support** when a delivery record contains an image URL
- 🧭 **Google Maps navigation links** where location information is available
- 📱 **Responsive dashboard interface** for different screen sizes

🗺️ How It Works

The application follows a simple real-time data flow:

```text
Firebase Firestore
        ↓
deliveries collection
        ↓
Firebase JavaScript SDK
        ↓
onSnapshot()
        ↓
Dashboard JavaScript
        ↓
 ┌──────────────┬──────────────┬──────────────┐
 ↓              ↓              ↓
Statistics    Delivery       Map Markers
              Table
        ↓
Relief Monitoring


| Technology          | Purpose                                            |
| ------------------- | -------------------------------------------------- |
| **HTML5**           | Dashboard structure and content                    |
| **CSS3**            | Styling, layout, animations, and responsive design |
| **JavaScript**      | Application logic and dynamic UI updates           |
| **Firebase**        | Cloud application services                         |
| **Cloud Firestore** | Real-time delivery database                        |
| **Leaflet**         | Interactive map framework                          |
| **MapLibre GL**     | Map rendering                                      |
| **OpenFreeMap**     | Map style/data source                              |
| **GitHub Pages**    | Static website hosting                             |

 🔥 Firebase / Firestore

Madadgar AI uses **Firebase Firestore** as its cloud database.

The dashboard listens to the `deliveries` collection in real time using Firestore's `onSnapshot()` listener. When delivery records are added or updated, the dashboard can update without manually refreshing the page.

 Firestore Collection

The main collection used by the project is:

```text
deliveries
| Field       | Purpose                                            |
| ----------- | -------------------------------------------------- |
| `area`      | Area associated with the delivery                  |
| `cnic`      | CNIC information associated with a delivery record |
| `lat`       | Latitude coordinate                                |
| `lng`       | Longitude coordinate                               |
| `latitude`  | Alternative latitude field                         |
| `longitude` | Alternative longitude field                        |
| `timestamp` | Delivery timestamp                                 |
| `time`      | Alternative time field                             |
| `photo`     | Delivery photo URL when available                  |
| `image`     | Alternative image URL                              |
| `verified`  | Verification information when available            |
| `duplicate` | Duplicate information when available               |


🗺️ Live Map

The dashboard displays delivery locations on an interactive map.

The map uses:

MapLibre GL
OpenFreeMap
OpenStreetMap/OpenMapTiles data

When valid latitude and longitude information is available in Firestore, delivery locations can be represented on the dashboard map.

Google Maps navigation links may also be used when navigation to a location is required.

🚀 Live Demo

Live Website:

https://mahjabeen903.github.io/madadgar-ai/

GitHub Repository:
https://github.com/Mahjabeen903/madadgar-ai.git

💻 How to Run Locally
Download or clone this repository.
Open the project folder.
Make sure index.html is present in the root folder.
Open index.html in a browser.
Allow the dashboard to connect to Firebase.
The dashboard will load delivery information from the Firestore deliveries collection when records are available.

For the best deployment experience, the project can be hosted using GitHub Pages.
🔐 Security Considerations

The Firebase configuration used by a web application is visible to the client and should not be treated as a private password or secret key.

The security of the Firestore database must be enforced through Firebase Authentication and Firestore Security Rules where required.

Sensitive credentials such as Firebase service-account private keys must never be committed to this repository.

The project should also avoid exposing unnecessary personal information in the public dashboard.

💡 Hackathon Value
Madadgar AI demonstrates how a lightweight web dashboard can connect a disaster-relief workflow with a real-time cloud database.

The project focuses on:

Real-time disaster relief monitoring
Delivery verification
Duplicate detection information
Geographic visualization
Centralized delivery records
Live dashboard updates
Simple and accessible web deployment

The goal is to provide relief teams with a clearer view of delivery activity and affected areas.

