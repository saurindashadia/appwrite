package main

import (
    "fmt"
    "github.com/appwrite/sdk-for-go/client"
    "github.com/appwrite/sdk-for-go/messaging"
)

func main() {
    client := client.New(
        client.WithEndpoint("https://<REGION>.cloud.appwrite.io/v1") // Your API Endpoint
        client.WithProject("<YOUR_PROJECT_ID>") // Your project ID
        client.WithKey("<YOUR_API_KEY>") // Your secret API key
    )

    service := messaging.New(client)
    response, error := service.UpdateVonageProvider(
        "<PROVIDER_ID>",
        messaging.WithUpdateVonageProviderName("<NAME>"),
        messaging.WithUpdateVonageProviderEnabled(false),
        messaging.WithUpdateVonageProviderApiKey("<API_KEY>"),
        messaging.WithUpdateVonageProviderApiSecret("<API_SECRET>"),
        messaging.WithUpdateVonageProviderFrom("<FROM>"),
    )

    if error != nil {
        panic(error)
    }

    fmt.Println(response)
}
