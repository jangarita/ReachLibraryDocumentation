---
layout: default
title: Token Authentication
nav_order: 2
---

# Token Authentication Instructions

In order to access the REACH API, you must include an authorization token with your request. Currently we do not expire auth tokens so 
once you recieve one from us you'll be able to use it until we notify you of any changes 

C# Example:
```C#
        public string CallRestMethod(string url)
        {
            var client = new RestClient(url);
            client.Timeout = -1;
            var request = new RestRequest(Method.GET);
            request.AddHeader("Authorization", "Token [TOKEN GOES HERE]");
            request.AddHeader("Content-Type", "application/json");
            IRestResponse response = client.Execute(request);
            return response.Content;
        }
```