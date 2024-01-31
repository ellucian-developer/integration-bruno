# Ethos Integration Bruno Examples

Bruno is a Fast and Git-Friendly Opensource API client, aimed at revolutionizing the status quo represented by Postman, Insomnia and similar tools out there. It stores your collections directly in a folder on your filesystem and it uses a plain text markup language, Bru, to save information about API requests.

This repository contains a Bruno collection and environment. A collection is simply a group of related API requests. The collection here contains examples of how to do things in Ethos Integration like obtaining an access token, calling GET/POST/PUT/DEL on a resource and consuming change-requests. An environment is a set of key-value pairs, essentially variables, that can be shared among API requests. The environment in this repository is used to store an API key and JWT access token.

For more Bruno learning and documentation start here https://www.usebruno.com

### Getting Started

To begin, download or clone this repository onto your local machine. The required collection and environment files are provided in `.bru` format. Open the Bru application and import the collection by clicking the "Open Collection" button located in the center of the interface.

<p align="center">
    <img src="/docs/images/bru-app.jpg" />
</p>

Within the Finder application, locate the directory containing your cloned repository. Subsequently, select the desired collection for import.

<p align="center">
    <img src="/docs/images/finder.jpg" />
</p>

Upon successful import of the collection, navigate to the three dots "..." and click it to access the Settings menu. Within Settings, configure the environment and collection pre-script information as needed.

<p align="center">
    <img src="/docs/images/settings.jpg" />
</p>
<p align="center">
    <img src="/docs/images/environment.jpg" />
</p>

On the configuration popup, provide the right Ethos API Key and then hit Save

<p align="center">
    <img src="/docs/images/configure.jpg" />
</p>

After configuring the environment variables, choose `Ethos Integration` as your environment. 
Now, you are now ready to initiate API execution.

<p align="center">
    <img src="/docs/images/execute.jpg" />
</p>

### Pre-request Script
This collection contains a pre-request script to simplify calling ethos end points. The script will automatically:

- Prepend the ethos integration url to any request that needs it. For example, to call https://integrate.elluciancloud.com/persons end point - you only need to enter 'persons'. Any endpoint that does not have the `/api/{resource}` pattern you will need to enter the full url.
- Manage Authorization token. The script will get, store and use the authorization token. This requires a valid value in the variable `ethosApiKey`
- Encode query string parameters

