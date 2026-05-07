# CLDV6211-A-PART2
# EventEase Part 2 Submission Notes

## Feature checklist

- ASP.NET Core MVC project with separate Models, Views, and Controllers for Venues, Events, and Bookings.
- SQL LocalDB connection stored in `appsettings.json`; the app runs EF Core migrations on startup so data persists after restarting the app.
- Venue and event image uploads are stored in the Azurite blob container named `venue-images`.
- Booking creation and editing prevent double bookings by checking whether another booking at the same venue overlaps the selected event date range.
- Venue and event deletion is blocked when active bookings exist.
- Booking list is a consolidated view that joins booking, venue, and event details.
- Booking search supports Booking ID, Booking Reference, and Event Name.
- UI styling has been updated for clearer screenshots and a stronger booking-specialist workflow.

## Code attribution

The project was scaffolded as an ASP.NET Core MVC application in Visual Studio 2022. The MVC structure follows Microsoft's description of the Model-View-Controller pattern, where controllers handle user requests, models represent application data, and views render the user interface (Microsoft, 2025a). Entity Framework Core is used for LocalDB persistence and relationship rules, including restricted delete behaviour to avoid removing records that are still referenced by bookings (Microsoft, 2021). Azure Blob Storage code uses the `Azure.Storage.Blobs` client library and `BlobContainerClient`/`BlobClient` APIs to create the local container and upload image files (Microsoft, 2024). Azurite is used as the local Azure Storage emulator because Microsoft recommends it for local Blob, Queue, and Table Storage development (Microsoft, 2025b).

## Reference list

Microsoft, 2021. *Cascade Delete - EF Core*. [online] Available at: <https://learn.microsoft.com/en-us/ef/core/saving/cascade-delete> [Accessed 6 May 2026].

Microsoft, 2024. *Quickstart: Azure Blob Storage client library for .NET*. [online] Available at: <https://learn.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-dotnet> [Accessed 6 May 2026].

Microsoft, 2025a. *Overview of ASP.NET Core MVC*. [online] Available at: <https://learn.microsoft.com/en-us/aspnet/core/mvc/overview> [Accessed 6 May 2026].

Microsoft, 2025b. *Install and run the Azurite emulator for Azure Storage*. [online] Available at: <https://learn.microsoft.com/en-us/azure/storage/common/storage-install-azurite> [Accessed 6 May 2026].

Microsoft, 2025c. *Connect an emulator to Azure Storage Explorer*. [online] Available at: <https://learn.microsoft.com/en-us/azure/storage/common/storage-explorer-emulators> [Accessed 6 May 2026].

