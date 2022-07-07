# AppStoreConnectAPI_JWT_TOKEN_DEMO
a demo about how to generate App Store Connect API  jwt token in js

```
const jwt = require("jsonwebtoken");
const fs = require("fs");
const dayjs = require("dayjs");

generateJWTForAppstore() {
    //Generating JWT Tokens for App Store Connect API
    var privateKey = fs.readFileSync("resources/AuthKey_7BUF2NGAHQ.p8");
    var token = jwt.sign(
      {
        iss: "69a6de8d-e294-47e3-e053-1234566",
        iat: dayjs().unix(),
        exp: dayjs().add(20, "minute").unix(),
        aud: "appstoreconnect-v1",
      },
      privateKey,
      {
        algorithm: "ES256",
        header: {
          alg: "ES256",
          kid: "7BUF2NGAHQ",
          typ: "JWT",
        },
      }
    );
    return token;
  }
  ```
