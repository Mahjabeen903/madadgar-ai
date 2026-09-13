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
