# ExamBlazorAuth
# ServerApp
nuget ��ġ
Microsoft.AspNetCore.Authentication.JwtBearer
Microsoft.AspNetCore.Components.Authorization

# WebAssembly
## server 
nuget ��ġ (5.0.13���� ����)
Microsoft.AspNetCore.Authentication.JwtBearer

startup.cs
service jwtBearer ��ġ

LoginController.cs
�ڵ� �߰�

appsettings.json ȯ�漳��
``` json
  "JwtSecurityKey": "RANDOM_KEY_MUST_NOT_BE_SHARED",
  "JwtIssuer": "https://localhost",
  "JwtAudience": "https://localhost",
  "JwtExpiryInDays": 1
```

## shared
LoginModel, LoginResult �߰�

## client
nuget ��ġ (5.0.13���� ����)
Blazored.LocalStorage
Microsoft.AspNetCore.Components.Authorization

Program.cs
builder.Services.AddBlazoredLocalStorage();
builder.Services.AddAuthorizationCore();

ApiAuthenticationStateProvider.cs
�ڵ� �߰�

services �߰�
AuthService.cs

razor �߰�
Login, Logout

_imports.razor
``` csharp
@using WebAssemblyApp.Client.Services
@using WebAssemblyApp.Shared
@using Microsoft.AspNetCore.Components.Authorization
```

App.razor
<AuthorizeRouteView> �߰�
<CascadingAuthenticationState> �߰�