# Making API Call with Hooks

## Add this code to Format the data that we got in the API Response

```js
const {data} = apiResponse
const formattedLeaderboardData = data.leaderboard_data.map(eachUser => ({
  id: eachUser.id,
  rank: eachUser.rank,
  name: eachUser.name,
  profileImgUrl: eachUser.profile_image_url,
  score: eachUser.score,
  language: eachUser.language,
  timeSpent: eachUser.time_spent,
}))
```

## Add this code to render LeaderboardTable

```js
return <LeaderboardTable leaderboardData={formattedLeaderboardData} />
```

## Add this code to render failure view

```js
const {errorMsg} = apiResponse
return <ErrorMessage>{errorMsg}</ErrorMessage>
```
