local Servers = game.HttpService:JSONDecode(game:HttpGet("https://games.roblox.com/v1/games/4779613061/servers/Public?sortOrder=Asc&limit=100"))

for i,v in pairs(Servers.data) do
  if v.playing ~= v.maxPlayers then
      game:GetService('TeleportService'):TeleportToPlaceInstance(game.PlaceId, v.id)
  end
end
