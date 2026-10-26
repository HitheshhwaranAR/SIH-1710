# Smart India Hackathon Workshop
# Date:26.10.2026
## Register Number:212224040118
## Name:Hitheshhwaran A R
## Problem Title
SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations
## Problem Description
Background: Railway stations are complex environments with numerous facilities and locations such as ticket counters, platforms, restrooms, food courts, and waiting areas. Passengers often face difficulties in navigating these spaces, especially in large or unfamiliar stations. Efficient and user-friendly navigation systems are crucial for improving passenger experience, reducing congestion, and ensuring timely travel connections. Description: The problem involves developing a comprehensive navigation solution for railway stations that assists passengers in locating various facilities and destinations within the station premises. This includes creating detailed maps, providing real-time directions, and integrating features such as accessibility options for individuals with disabilities. The solution should be intuitive, easy to use, and accessible via multiple platforms, including mobile devices and digital kiosks. Key challenges include updating navigation information in real-time, ensuring accuracy, and accommodating the diverse needs of all passengers. Expected Solution: The expected solution is a multi-platform navigation system that provides detailed, real-time directions to all facilities and locations within a railway station. This system should include: A mobile application with 3D interactive maps and step-by-step navigation. Digital kiosks located throughout the station with touch-screen interfaces. Voice-guided navigation for visually impaired passengers. Regular updates to reflect changes in station layout and facility locations. Integration with existing railway apps and services for seamless user experience. The solution should enhance the overall passenger experience by reducing confusion, saving time, and improving accessibility within the station.

## Problem Creater's Organization
Ministry of Railway

## Idea
RailWayfinder: an offline-first, multi-platform indoor navigation system for railway stations.

Passengers get step-by-step directions to platforms, ticket counters, restrooms, food courts, waiting rooms and exits. These come through a mobile app with 3D maps, touch kiosks at fixed points, and voice guidance for visually impaired users. A web admin portal lets station staff update the map and facility status. This keeps data fresh when a platform changes, a lift breaks down, or a stall closes.

What sets it apart:

Works without GPS. Indoor positioning uses BLE beacons, Wi-Fi fingerprinting and QR “you are here” codes at kiosks and signboards. QR codes are the cheap fallback.
Live-aware routing. Routes respond to platform changes, delays, crowd density and out-of-service lifts or escalators, so they are not just shortest-path.
Accessibility first. Step-free routes, voice and haptic guidance, high-contrast mode, and multilingual support (English, Hindi, Tamil and other regional languages).
Integrates with existing railway apps (such as IRCTC and NTES) through APIs, so passengers can go from PNR to platform to seat without switching apps.


## Proposed Solution / Architecture Diagram

<img width="707" height="813" alt="image" src="https://github.com/user-attachments/assets/4d65890a-7452-4d5b-87d2-f200ba6cb43c" />

## Use Cases
First-time traveler in a large station finds the platform from the entrance without asking around.

Late passenger gets the fastest route to the platform with an ETA, helping them make a connection.

Visually impaired passenger gets voice-guided turn-by-turn directions with haptic cues and obstacle alerts.

Wheelchair user or senior citizen gets a step-free route through lifts and ramps, with live lift status.

Platform change or delay triggers an instant push notification and automatic re-routing.

Finding facilities such as restrooms, water, ATMs, food courts, waiting rooms, first aid and the cloak room.

Kiosk-only users with no smartphone get directions on screen or on a printed or QR slip.

Crowd management: staff see congestion heatmaps and divert passenger flow during peak hours or festivals.

Emergency evacuation pushes the nearest safe exit route to everyone’s device.

Multilingual support lets passengers use their regional language.

## Technology Stack
Layer	Technologies
Mobile app	Flutter or React Native, Mapbox / Three.js for 3D indoor maps

Kiosk UI	React (PWA) in fullscreen kiosk mode, touch-optimized

Admin portal	Next.js + Tailwind

Backend	Node.js (NestJS) or FastAPI, REST + WebSockets

Routing engine	Graph-based A* / Dijkstra (NetworkX prototype, then custom service)

Database	PostgreSQL + PostGIS, Redis for live state

Positioning	BLE beacons (iBeacon/Eddystone), Wi-Fi RTT/fingerprinting, QR codes, phone sensors (IMU)

Voice and accessibility	Android TalkBack/iOS VoiceOver support, Google TTS / Bhashini for Indian languages, haptics API

Maps and 3D	GeoJSON floor plans, Blender → glTF 3D models

Notifications	Firebase Cloud Messaging

Deployment	Docker, AWS/Azure or NIC cloud, CI/CD with GitHub Actions
Analytics	Grafana, anonymized crowd metrics


## Dependencies
Railway data APIs: NTES / IRCTC for train status, platform allocation and delays (needs Ministry of Railways or CRIS access).

Station floor plans and CAD drawings from the railway authority to build the base map and routing graph.

Hardware: BLE beacons, kiosks (touchscreens), and Wi-Fi access points on station premises. 

Indian-language TTS/translation: Bhashini or similar for regional language support.

Map and 3D SDKs: Mapbox, Three.js or similar rendering libraries.

Connectivity: station Wi-Fi or mobile data, with an offline cached map as fallback.

Cloud hosting and push notification services (Firebase).

Station staff cooperation to keep facility and closure data updated.
Privacy and compliance: the DPDP Act 2023, with no personal tracking stored and crowd data anonymized.
