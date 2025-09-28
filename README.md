# simple_auth

## Cách chạy
1. Install deps:
```bash
npm install
```

2. Khởi động MongoDB (local or docker).

3. Start servers:
```bash
node basic_auth.js    # port 3000
node cookie_auth.js   # port 3001
```


## Endpoints & How to test (POSTMAN)

### Basic Auth
#### 1. non-secure ("/")
GET `http://localhost:3000/`
Expected: `Welcome! Visit first public resource.`
![basic-non-secure](public/results/basic-non-secure.png)
#### 2. secure 
GET `http://localhost:3000/secure`
Authorization: Basic `admin:12345` → header:  
```
Authorization: Basic YWRtaW46MTIzNDU=
```
Expected: `You have accessed a protected resource 🎉`  
![basic-secure](public/results/basic-secure.png)

#### 3. public 
GET `http://localhost:3000/public`

Expected: `Welcome! Visit second public resource.`

![public](public/results/public.png)
---

### Cookie Auth
#### 4. login
POST `http://localhost:3001/login`
Body JSON:
```json
{ "username": "admin", "password": "12345" }
```
Expected: `Logged in!`  
![login](public/results/login.png)
![set_cookie](public/results/set_cookie.png)
#### 5. profile
GET `http://localhost:3001/profile` (cookie must be present)  
Expected: `Welcome user 1, your cookie is valid.`  
![profile](public/results/profile.png)

#### 6. logout
POST `http://localhost:3001/logout` → cookie deleted.  
Expected: `Logged out.`
![logout](public/results/logout.png)

#### 7. database mongo
Cookie in DB:  
![mongo_cookie](public/results/mongo_cookie.png)




