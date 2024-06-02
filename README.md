## Start project

1. Configure environment in `.env` file
2. Install dependencies `php composer.phar install`
3. Create database `php bin/console do:da:cr`
4. Run migrations `php bin/console do:mi:mi`
5. Generate keys for JWT
6. Run dev server `./symfony serve --no-tls`
7. Ready!


### Generating Keys

To work with JWT, you need private and public keys. Generate them using OpenSSL:


``` sh
openssl genpkey -algorithm RSA -out config/jwt/private.pem -aes256
openssl rsa -pubout -in config/jwt/private.pem -out config/jwt/public.pem
```

During the generation process, you will be prompted to enter a passphrase. Use the same passphrase as the one specified in the JWT_PASSPHRASE variable.
