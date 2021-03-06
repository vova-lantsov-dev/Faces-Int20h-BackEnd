## How to use
Register FlickrClient in ASP.NET Core's DI as singleton.  
  
**Startup.cs:**
```
public void ConfigureServices(IServiceCollection services)
{
    ...
    
    services.AddSingleton<IFlickrClient, FlickrClient>(_ =>
    {
        return new FlickrClient(
            new FlickrClientOptions
            {
                ApiKey = "api_key",
                UserId = "118310678@N03",
                PhotosetId = "72157641322954544"
            });
    });
}
```

Then inject this client in your services or controllers. Done!