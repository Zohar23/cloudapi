# OpenAlprApi - the C# library for the OpenALPR Cloud API

No descripton provided (generated by Swagger Codegen https://github.com/swagger-api/swagger-codegen)

This C# SDK is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: 2.0.1
- SDK version: 2.0.1
- Build date: 2017-02-24T16:12:49.900-05:00
- Build package: class io.swagger.codegen.languages.CSharpClientCodegen

## Frameworks supported
- .NET 4.0 or later
- Windows Phone 7.1 (Mango)

## Dependencies
- [RestSharp](https://www.nuget.org/packages/RestSharp) - 105.1.0 or later
- [Json.NET](https://www.nuget.org/packages/Newtonsoft.Json/) - 7.0.0 or later

The DLLs included in the package may not be the latest version. We recommned using [NuGet] (https://docs.nuget.org/consume/installing-nuget) to obtain the latest version of the packages:
```
Install-Package RestSharp
Install-Package Newtonsoft.Json
```

NOTE: RestSharp versions greater than 105.1.0 have a bug which causes file uploads to fail. See [RestSharp#742](https://github.com/restsharp/RestSharp/issues/742)

## Installation
Run the following command to generate the DLL
- [Mac/Linux] `/bin/sh build.sh`
- [Windows] `build.bat`

Then include the DLL (under the `bin` folder) in the C# project, and use the namespaces:
```csharp
using OpenAlprApi.Api;
using OpenAlprApi.Client;
using Model;
```

## Getting Started

```csharp
using System;
using System.Diagnostics;
using OpenAlprApi.Api;
using OpenAlprApi.Client;
using Model;

namespace Example
{
    public class Example
    {
        public void main()
        {
            
            var apiInstance = new DefaultApi();
            var imageBytes = imageBytes_example;  // string | The image file that you wish to analyze encoded in base64 
            var secretKey = secretKey_example;  // string | The secret key used to authenticate your account.  You can view your  secret key by visiting  https://cloud.openalpr.com/ 
            var country = country_example;  // string | Defines the training data used by OpenALPR.  \"us\" analyzes  North-American style plates.  \"eu\" analyzes European-style plates.  This field is required if using the \"plate\" task  You may use multiple datasets by using commas between the country  codes.  For example, 'au,auwide' would analyze using both the  Australian plate styles.  A full list of supported country codes  can be found here https://github.com/openalpr/openalpr/tree/master/runtime_data/config 
            var recognizeVehicle = 56;  // int? | If set to 1, the vehicle will also be recognized in the image This requires an additional credit per request  (optional)  (default to 0)
            var state = state_example;  // string | Corresponds to a US state or EU country code used by OpenALPR pattern  recognition.  For example, using \"md\" matches US plates against the  Maryland plate patterns.  Using \"fr\" matches European plates against  the French plate patterns.  (optional)  (default to )
            var returnImage = 56;  // int? | If set to 1, the image you uploaded will be encoded in base64 and  sent back along with the response  (optional)  (default to 0)
            var topn = 56;  // int? | The number of results you would like to be returned for plate  candidates and vehicle classifications  (optional)  (default to 10)
            var prewarp = prewarp_example;  // string | Prewarp configuration is used to calibrate the analyses for the  angle of a particular camera.  More information is available here http://doc.openalpr.com/accuracy_improvements.html#calibration  (optional)  (default to )

            try
            {
                InlineResponse200 result = apiInstance.RecognizeBytes(imageBytes, secretKey, country, recognizeVehicle, state, returnImage, topn, prewarp);
                Debug.WriteLine(result);
            }
            catch (Exception e)
            {
                Debug.Print("Exception when calling DefaultApi.RecognizeBytes: " + e.Message );
            }
        }
    }
}
```

<a name="documentation-for-api-endpoints"></a>
## Documentation for API Endpoints

All URIs are relative to *https://api.openalpr.com/v2*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*DefaultApi* | [**RecognizeBytes**](docs/DefaultApi.md#recognizebytes) | **POST** /recognize_bytes | 
*DefaultApi* | [**RecognizeFile**](docs/DefaultApi.md#recognizefile) | **POST** /recognize | 
*DefaultApi* | [**RecognizeUrl**](docs/DefaultApi.md#recognizeurl) | **POST** /recognize_url | 


<a name="documentation-for-models"></a>
## Documentation for Models

 - [Model.Coordinate](docs/Coordinate.md)
 - [Model.InlineResponse200](docs/InlineResponse200.md)
 - [Model.InlineResponse200ProcessingTime](docs/InlineResponse200ProcessingTime.md)
 - [Model.InlineResponse400](docs/InlineResponse400.md)
 - [Model.PlateCandidate](docs/PlateCandidate.md)
 - [Model.PlateDetails](docs/PlateDetails.md)
 - [Model.RegionOfInterest](docs/RegionOfInterest.md)
 - [Model.VehicleCandidate](docs/VehicleCandidate.md)
 - [Model.VehicleDetails](docs/VehicleDetails.md)


## Documentation for Authorization

All endpoints do not require authorization.