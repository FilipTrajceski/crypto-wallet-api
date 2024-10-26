# crypto-wallet-api

A secure and efficient API for managing cryptocurrency wallets, built to support popular cryptocurrencies like Bitcoin, Ethereum, and more.
The CryptoWallet API allows users to generate a wallet, check balances, buy and sell currencies and transfer crypto currencies from one to another user.
The API contains a Register and Login Endpoints using the Identity NugetPackage.Every user can have only one wallet,and with one wallet you can add a CryptoCurrency through the CryptoCurrency POST method,or through the Transaction Buy/Sell options.Also you can transfer crypto currencies from your wallet to another users wallet.

---
### Register endpoint- [POST] /api/Account

This endpoint allows the user to create an account.
The user has to input a Uniqe username.The password must be 8 characters long with at least one uppercase character,one number and one special character.
User has to confirm the password he/she created.

**Request Body**: 
```json
{
  "userName": "string",
  "password": "string",
  "confirmPassword": "string",
  "email": "string",
  "country": "string",
  "phoneNumber": "string"
}
```
Response: 200 - Registered Succesfully!
401- Bad Request.

---
### Login Endpoint - [POST] /api/Account/login

This endpoint provides a JWT Bearer token if the user is registered or has a previously created an account in the DB.
With the JWT token you can Authorize access to the other endpoints.

**Request Body**: 
```json
{
  "userName": "string",
  "password": "string"
}
```
Response: 200 - JWT token
401- Bad Request/Password error
 ---
Multi-Currency Support- You can manage up to 50 cryptocurrencies with this API. Users are required to input the value for each cryptocurrency when adding it to their wallet, as no default values are provided.

Transfer option- User can transfer a Currency from his wallet to another users wallet with some conditions.


USING THE API:
You have to clone the repo to a local folder,change the Server name of the connectionstring to your server name that you are using in SSMS(SQL Server Management Studio).Make a migration to the database and
update-database.The Connection string is located at CryptoSphere.Wallet.Api connected services in the Secrets.Json file and in the DbContext class.You can use Swagger or Postman for testing the API.

Notes:
Learning Experience: While the API is functional, it may lack advanced features or optimizations found in more established projects.

Future Improvements: I plan to continue developing this API by adding more features, improving security, and enhancing documentation.

(This API is an ongoing project as part of the Qinshift Academy Students Projects 2023/24.)


