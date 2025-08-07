# Real-Time-Dashboard-with-Azure
Build a Real-Time Dashboard with Azure SignalR, Cosmos DB, and Azure Functions
Introduction

Real-time applications are increasingly critical for modern web experiences — from live dashboards to chat apps and notifications. Azure offers powerful serverless tools to build such applications with ease.

In this article, I will show you how to build a real-time dashboard leveraging:

Azure Cosmos DB (with change feed)
Azure Functions (triggered by Cosmos DB changes)
Azure SignalR Service (to push real-time updates)
A React frontend to display live data

Architecture Overview
Our app workflow looks like this:
User or backend writes new data to Cosmos DB.
Azure Function listens to Cosmos DB change feed.
The function sends real-time notifications to connected clients via Azure SignalR Service.
React dashboard updates live upon receiving SignalR messages.

Step 1: Provision Azure Resources
First, create all necessary Azure resources via Azure CLI:

Step 2: Create Azure Function with Cosmos DB Trigger and SignalR Output Binding
The Azure Function listens to the Cosmos DB change feed and sends updated data to the SignalR hub.
Initialize Function Project

Step 3: Setup SignalR Negotiation Endpoint
For secure connections, clients need a negotiate function.
Add HTTP Trigger Function (negotiate)

Step 5: Deploy Azure Functions
func azure functionapp publish RealtimeFuncApp

Step 6: Build React Frontend with SignalR Client

Testing Your Real-Time Dashboard
Insert or update documents in Cosmos DB.
Azure Function triggers on changes, sending messages to SignalR.
React frontend instantly receives updates and displays them.

Conclusion
With Azure Cosmos DB, Functions, and SignalR, building scalable real-time dashboards is straightforward and cost-effective. You can easily extend this to support complex scenarios like role-based notifications, multiple hubs, or integration with other Azure services.

Resources
Azure Cosmos DB change feed
Azure SignalR Service
Azure Functions bindings for SignalR

you can read the article here: https://nandiniduggineni.hashnode.dev/build-a-real-time-dashboard-with-azure-signalr-cosmos-db-and-azure-functions
