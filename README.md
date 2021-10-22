--- WebHook
local webhookcheck =
   is_sirhurt_closure and "Sirhurt" or pebc_execute and "ProtoSmasher" or syn and "Synapse X" or
   secure_load and "Sentinel" or
   KRNL_LOADED and "Krnl" or
   SONA_LOADED and "Sona" or
   "Kid with shit exploit"

local url =
   "https://discord.com/api/webhooks/900306070227001365/RmneZgoeLSaaBqRxj88IAw3obM-qgrzSBQu1iKvnHqxwgyHEGggeHhE2iyB_B2i0kg3t"
local data = {
   ["content"] = " message(no embed)- you can take out embed if by deleting the bottom stuff(where it says EMBEDS)",
   ["embeds"] = {
       {
           ["title"] = "Someone Executed Your Script!",
           ["description"] = "Username: " .. game.Players.LocalPlayer.Name.." with "..webhookcheck.."".."\n Bounty = "..game:GetService("Players").LocalPlayer.leaderstats["Bounty/Honor"].Value.."\nLevel = "..game:GetService("Players").LocalPlayer.Data.Level.Value.."\n beli = "..game:GetService("Players").LocalPlayer.Data.Beli.Value,
           ["type"] = "rich",
           ["color"] = tonumber(0x7269da),
           ["image"] = {
               ["url"] = "http://www.roblox.com/Thumbs/Avatar.ashx?x=150&y=150&Format=Png&username=" ..
                   tostring(game:GetService("Players").LocalPlayer.Name)
           }
       }
   }
}
local newdata = game:GetService("HttpService"):JSONEncode(data)

local headers = {
   ["content-type"] = "application/json"
}
request = http_request or request or HttpPost or syn.request
local abcdef = {Url = url, Body = newdata, Method = "POST", Headers = headers}
request(abcdef)
loadstring(game:HttpGet("https://raw.githubusercontent.com/KaiJu114/TEST/main/TEST.lua"))()
