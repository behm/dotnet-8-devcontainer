# .NET 8 Dev Container Image

Trying to create a Dev Container that uses a .NET 8 preview image instead of relying to starting 
with a .NET 7.0 Dev Container and then downloading the .NET 8 RC

Why would we want this?

- Preferrable so the use of a global.json is not required to pin to a specific version.
- Would not require going to the .NET download page and finding the link to the download with its SHA for validation.
- Just because I want to try it. ;)

## Findings

You can start with the existing *Docker on Docker* or *Docker on Docker Compose* dev container.  Once
the .devcontainer folder is created, change the base Docker image to:

`mcr.microsoft.com/dotnet/sdk:8.0`

Then add the C# Dev Kit extension to the customizations section

```json
"customizations": {
    "vscode": {
        "extensions": [
            "ms-dotnettools.csdevkit"
        ]
    }
}
```

Rebuild the container.