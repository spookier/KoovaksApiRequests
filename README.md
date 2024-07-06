# Documenting Koovak's key API endpoints

This is part of a project to help [@VoltaicHQ](https://github.com/VoltaicHQ) develop Voltaic Season 3  
Due to the lack of a public API reference for Koovak's, I had to sniff requests to document these key endpoints

## API Endpoints

### 1. Get a User's Global Leaderboards Rank
- This endpoint allows you to retrieve the global leaderboard rank for a specific user  
- This is useful for tracking a player's overall performance and ranking in the game

**Example Request:**

https://kovaaks.com/webapp-backend/leaderboard/global/search/account-names?username=MattyOW

**Parameters:**
- `username`: The username of the player whose rank you want to find. Replace "MattyOW" with the desired username.

**Example Response:**
```json
{
  "status": "success",
  "data": [
    {
      "username": "MattyOW",
      "rank": 42,
      "score": 123456
    }
  ]
}
```

---

### 2. Find a Specific Scenario
- This endpoint helps you find scenarios by name
- It is crucial because the leaderboardId parameter obtained here is required to fetch a specific player's data within that scenario

**Example Request:**

https://kovaaks.com/webapp-backend/scenario/popular?page=0&max=1&scenarioNameSearch=PASU+VOLTAIC+INTERMEDIATE

**Parameters:**

- `page`: The page number to retrieve (pagination)
- `max`: The maximum number of results to return (Adjust this number as needed)
- `scenarioNameSearch`: The name of the scenario you are searching for -- Replace "PASU+VOLTAIC+INTERMEDIATE" with the desired scenario name

**Example Response:**
```json
{
  "status": "success",
  "data": [
    {
      "scenarioId": 10618,
      "scenarioName": "PASU VOLTAIC INTERMEDIATE",
      "plays": 98765
    }
  ]
}
```

---

### 3. Find a Specific Player's Data in a Scenario

- This endpoint retrieves detailed data for a specific player within a scenario, including their best score, game version, and settings


**Example Request:**
https://kovaaks.com/webapp-backend/leaderboard/scores/global?leaderboardId=10618&page=0&max=1&usernameSearch=selene

**Parameters:**

- `leaderboardId`: The ID of the scenario's leaderboard obtained from the previous endpoint
- `page`: The page number to retrieve (pagination)
- `max`: The maximum number of results to return. Adjust this number as needed
- `usernameSearch`: The username of the player whose data you want to retrieve. Replace "selene" with the desired username


**Example Response:**
```json
{
  "status": "success",
  "data": [
    {
      "username": "selene",
      "score": 654321,
      "gameVersion": "1.2.3",
      "settings": {
        "sensitivity": 3.5,
        "FOV": 103
      }
    }
  ]
}
```

---
