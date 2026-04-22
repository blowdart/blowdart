# Here lies Barry Dorrans

>[!CAUTION]
>Please report security bugs in .NET and other Microsoft projects via https://msrc.microsoft.com/report/
>
>Security bugs in .NET reported via MSRC can be eligble for the [.NET Bug Bounty](https://www.microsoft.com/en-us/msrc/bounty-dot-net-core).

- 💼 For work I try to keep .NET and its ecosystem secure through design reviews, threat models and other processes.
- 🏠 Here I write bad code including code for
  - 🦋 Wrapping [AtProto and Bluesky APIs in a .NET class library](https://github.com/blowdart/idunno.Bluesky),
  - 🔐 Random security classes for .NET, including an [SSRF protection library](https://github.com/blowdart/idunno.Security.Ssrf).
  - 🔐 [Authentication middleware](https://github.com/blowdart/idunno.Authentication) for ASP.NET Core,
  - 🔓 Examples of insecure code for demonstrations and conferences talks.

📇 You can reach me on Bluesky as [blowdart.me](https://bsky.app/profile/blowdart.me)

## Code Signing Information

### Release Build Publisher Verification

#### Release Build Signing Certificates

| Valid From | Valid To   | SHA256 Thumbprint                                                | SHA1 Thumbprint |
|------------|------------|------------------------------------------------------------------|-----------------|
| 2025-07-25 | 2026-10-23 | 40B774C2F613665D25488A568EA06F853054DEE79F1782E7DB5CD7FAEF3F6192 | A75A98B54008714D7B76C253C80C23C52E02266E |
| 2024-10-16 | 2025-10-23 | 46CC5E52519EC1176A255B2B61851A084166853ADB620AACC7FA29CC660C6221 | A64124F02C1066A788445A876CD2B6EA60B9DC39 |
| 2023-09-24 | 2024-10-23 | FF6EDE06A9E7182F82A39199D92A7FAC83E9B40E6D1BD7647BEBF97BB8AFE2A6 | 68C48F83ADFF99A573281DDAB2F5B0DF095DF118 |
| 2022-07-18 | 2023-10-18 | A236316AF1EA63A8F0668A587238741449ABC6D7491AE33291102DDCF0BB79FA | 15BD9666FF17260B0F65831765A1919B6BEBF8BF |
| 2021-10-12 | 2022-10-15 | FD05FB98368742D5415D0D9ACD3EEF2123F6C8271E0429426351BC7FB27B3AF3 | D181F9CB03B8499A5B243941B7F80C972D3ED5BC |
| 2019-09-24 | 2020-09-29 | 841FD34A7A26AF8D6F14F996C0F56EAD70EBFE65BF7ECC9AF3CB26D394F6B95F | CD2BD802254E45B37CB281229DF4DF5F7A0BD4B4 |
| 2018-02-10 | 2019-10-08 | 8263D3A7932B86087290A6F916E4E8BF773B29154285EFFC00A097F400006793 | 46FEDE9825EF9446A6DFD3E4776A2F332432A3F9 |

#### Validating .NET assemblies and Windows executables

Run the following PowerShell command on Windows to validate the signature of a file. Compare the `SignerCertificate` with the SHA1
Thumbprint column in above table to ensure it is signed with a valid certificate.

```powershell
Get-AuthenticodeSignature [-FilePath]
```

#### Validating nupkg author signatures

Run the following command on Windows or Linux with a .NET SDK installed to validate the signature of a file. Compare the `SHA256 hash` under
`Signature Type: Author` with the SHA256 Thumbprint column in above table to ensure it is signed with a valid certificate.

```powershell
dotnet nuget verify [<package-path(s)>]
```

### Pre-release Publisher Verification

Pre-release builds hosted on [MyGet](https://www.myget.org/gallery/blowdart) are signed with Azure [Artifact Signing](https://azure.microsoft.com/en-us/products/artifact-signing/),
which uses a short-lived certificate. You can verify that the certificate is issued to "CN=Barry Dorrans, O=Barry Dorrans, L=Bothell, S=Washington, C=US", with a root CA of
"CN=Microsoft Identity Verification Root Certificate Authority 2020"

To view the full certificate chain in `dotnet nuget verify` use the `-v detailed` option;

```powershell
dotnet nuget verify [<package-path(s)>] -v detailed
```
