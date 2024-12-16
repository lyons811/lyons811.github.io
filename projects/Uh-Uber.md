---
layout: project
type: project
image: img/UH-Uber.png
title: "UH-Uber"
date: 2024
published: true
labels:
  - Typescript
  - NextJS
summary: "A project to show proficiency everything learned in ICS 314"
---

# UH Manoa Ride Share

## Overview

UH Manoa Ride Share is a web application designed to address a critical challenge faced by UH Manoa students: the difficulties of campus commuting. With limited, expensive parking and sometimes inconvenient public transportation options, many students resort to driving alone, contributing to increased traffic, higher transportation costs, and elevated carbon emissions.

Our solution connects students who share similar routes and schedules, facilitating an efficient carpooling system that benefits both the community and the environment.

## Goals

- **Reduce Transportation Costs**: Help students save money by sharing commuting expenses
- **Ease Parking Demand**: Decrease the number of single-occupancy vehicles requiring parking on campus
- **Environmental Impact**: Lower carbon emissions by promoting shared rides
- **Community Building**: Foster connections between students through collaborative transportation
- **Enhanced Safety**: Implement features to ensure secure and reliable ride sharing

## Key Features

### 1. Welcome Page
- User registration and authentication
- Visual guide for posting/finding rides
- Student testimonials
- Community impact statistics

### 2. User Dashboard
- Profile summary with photo and basic info
- Ride preferences and ratings
- Active ride management (offered/requested)
- Real-time notifications
- Personal eco-impact statistics

### 3. Ride Posting
- Comprehensive trip detail form
- Recurring ride scheduling
- Automated cost calculator
- Route customization

### 4. Ride Search
- Advanced filtering system
- Interactive map view
- Driver preference matching
- Real-time availability updates

### 5. User Profiles
- Detailed user information
- Ride history and ratings
- Preference settings
- Community reputation system

## Special Features

### Carpool Mapping
- Dynamic route optimization
- Real-time traffic updates
- Pickup/dropoff coordination
- Travel time estimation

### Community Board
- Event-based carpooling
- Study group coordination
- Campus activity ride sharing
- Community engagement opportunities

### Safety Features
- Real-time location sharing
- Trusted contact system
- Trip monitoring
- Emergency assistance access

## Technical Implementation

Here's a code snippet demonstrating how we generate our prisma db. 
```javascript
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}

model User {
  id             Int           @id @default(autoincrement())
  email          String        @unique
  password       String
  role           Role          @default(USER)
  avatarUrl      String?
  bio            String?
  campusLocation String?
  createdAt      DateTime      @default(now())
  name           String?
  phone          String?
  pronouns       String?
  updatedAt      DateTime      @updatedAt
  offeredRides   Ride[]        @relation("DriverRides")
  bookedRides    RideBooking[]
}

model Ride {
  id             Int           @id @default(autoincrement())
  driverId       Int
  startLocation  String
  endLocation    String
  departureTime  DateTime
  availableSeats Int
  status         RideStatus    @default(PENDING)
  description    String?
  createdAt      DateTime      @default(now())
  updatedAt      DateTime      @updatedAt
  driver         User          @relation("DriverRides", fields: [driverId], references: [id])
  bookings       RideBooking[]

  @@index([driverId])
}

model RideBooking {
  id          Int        @id @default(autoincrement())
  rideId      Int
  passengerId Int
  status      RideStatus @default(PENDING)
  createdAt   DateTime   @default(now())
  updatedAt   DateTime   @updatedAt
  passenger   User       @relation(fields: [passengerId], references: [id])
  ride        Ride       @relation(fields: [rideId], references: [id])

  @@unique([rideId, passengerId])
  @@index([rideId])
  @@index([passengerId])
}

model Stuff {
  id        Int       @id @default(autoincrement())
  name      String
  quantity  Int
  condition Condition
  owner     String
}

enum Role {
  USER
  ADMIN
}

enum RideStatus {
  PENDING
  ACTIVE
  COMPLETED
  CANCELLED
}

enum Condition {
  excellent
  good
  fair
  poor
}

```

## Development Stack

- **Frontend**: Next.js, React, Tailwind CSS
- **Backend**: Node.js, PostgreSQL, Prisma ORM
- **Authentication**: NextAuth.js
- **Deployment**: Vercel
- **Version Control**: Git/GitHub

## Use Cases

### Daily Commuter
Sarah, a regular commuter to UH Manoa, uses the app to:
- Share her daily route
- Split fuel costs
- Reduce parking stress
- Connect with fellow students

### Environmental Champion
Users can:
- Track carbon footprint reduction
- Earn eco-badges
- Contribute to campus sustainability
- Promote green transportation

### Semester Schedule Matching
Rachel and Josh demonstrate how students can:
- Coordinate recurring rides
- Match class schedules
- Build reliable transportation partnerships
- Share semester-long commutes

## Project Team

- Justin Campos
- Jayda Decker
- Karina Park
- Lyon Singleton
- Baishen Wang

## Development Status

This project is currently in the initial development phase. We are:
- Setting up the development infrastructure
- Finalizing design mockups
- Planning the implementation timeline
- Building our core features

## Getting Started

### Prerequisites
- Node.js (v18 or higher)
- npm or yarn package manager
- Git
- PostgreSQL database

### Installation

1. Clone the repository:
```bash
git clone https://github.com/UH-Uber/UH-Uber-SourceCode.git
cd UH-Uber-SourceCode
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:
- Copy `.env.example` to `.env`
- Configure required variables

4. Set up the database:
```bash
npx prisma migrate dev
npx prisma generate
```

5. Start the development server:
```bash
npm run dev
```

## Project Links

- **M1 Page**: [Project Board 1](https://github.com/orgs/UH-Uber/projects/1)
- **M2 Page**: [Project Board 2](https://github.com/orgs/UH-Uber/projects/3)
- **M3 Page**: [Project Board 3](https://github.com/orgs/UH-Uber/projects/4)
- **Live Demo**: [Vercel Deployment](https://uh-uber-source-code.vercel.app/)
- **Team Contract**: [Google Doc](https://docs.google.com/document/d/1-mcSvmThZ-aZ6_CZlB_yksfq7MiZ57kAd3QDrStG7zA/edit?tab=t.0)

## Contributing

We welcome contributions! Please feel free to submit a Pull Request.

---
Last Updated: December 15, 2024