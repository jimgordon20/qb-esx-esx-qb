# qb-esx-esx-qb




# 1. Initialization

QBCore
Old Method
lua
Copy code
QBCore = nil
Citizen.CreateThread(function()
    while QBCore == nil do
        TriggerEvent('QBCore:GetObject', function(obj) QBCore = obj end)
        Citizen.Wait(30)
    end
end)
New Method
lua
Copy code
local QBCore = exports['qb-core']:GetCoreObject()
ESX
Initialization
lua
Copy code
ESX = nil
Citizen.CreateThread(function()
    while ESX == nil do
        TriggerEvent('esx:getSharedObject', function(obj) ESX = obj end)
        Citizen.Wait(30)
    end
end)

# 2. Player Events

Player Loaded
QBCore
lua
Copy code
RegisterNetEvent('QBCore:Client:OnPlayerLoaded')
AddEventHandler('QBCore:Client:OnPlayerLoaded', function()
    -- Code here
end)
ESX
lua
Copy code
RegisterNetEvent('esx:playerLoaded')
AddEventHandler('esx:playerLoaded', function()
    -- Code here
end)
Job Update
QBCore
lua
Copy code
RegisterNetEvent('QBCore:Client:OnJobUpdate')
AddEventHandler('QBCore:Client:OnJobUpdate', function(job)
    PlayerData.job = job
end)
ESX
lua
Copy code
RegisterNetEvent('esx:setJob')
AddEventHandler('esx:setJob', function(job)
    PlayerData.job = job
end)
Player Unload
QBCore
lua
Copy code
RegisterNetEvent('QBCore:Client:OnPlayerUnload')
AddEventHandler('QBCore:Client:OnPlayerUnload', function()
    -- Code here
end)
ESX
lua
Copy code
RegisterNetEvent('esx:onPlayerDeath')
AddEventHandler('esx:onPlayerDeath', function()
    -- Code here
end)
