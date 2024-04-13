# Documenting Koovak's key API endpoints

### - To get an user's global leaderboards rank
*(replace "MattyOW" with the user you're searching for)*  
https://kovaaks.com/webapp-backend/leaderboard/global/search/account-names?username=MattyOW

---

### - To find a specific scenario
#### Notes:
- **This endpoint is crucial because the "leaderboardId" parameter is required to find a specific player's data within the retrieved scenario later on**  
- The order in which scenarios are returned when queried is determined by the number of entries for each scenario (most played to lowest)  
- Scenarios with a greater number of plays will be fetched and returned first  
- If the provided scenario name does not exactly match the available scenarios, the API will return the closest, most played scenario that contains the requested keywords  
- The example provided limits the return list to 1 result, but this can be adjusted by modifying the "max=1" parameter  

*(replace "PASU+VOLTAIC+INTERMEDIATE" with the scenario you're searching for)*  
https://kovaaks.com/webapp-backend/scenario/popular?page=0&max=1&scenarioNameSearch=PASU+VOLTAIC+INTERMEDIATE

---

### To find a specific player's data in a scenario (best score, game version, settings...)
#### Notes:
- After retrieving the desired scenario using the previous API endpoint, you can then use the "leaderboardId" parameter to fetch a specific player's data within that scenario  
- In the example URL provided, replace "10618" with the "leaderboardId" of the scenario you want to search, and replace "selene" with the username of the player you're looking for  

https://kovaaks.com/webapp-backend/leaderboard/scores/global?leaderboardId=10618&page=0&max=1&usernameSearch=selene

###
