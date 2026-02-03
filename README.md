
## Setup instructions

1. clone the project 
2. run composer install
3. create your empty database to migrate 
4. add your database configurations in .env file 
5. run php artisan key:generate
6. run php artisan migrate --seed
7. php artisan jwt:secret
8. php artisan serve

## Explanation of the payment gateway extensibility

used design patterns are Strategy Pattern and Factory Pattern :

1. each payment gateway is a strategy (CreditCardGateway,...) each one must implement PaymentGatewayInterface, this enforces each one to initialize Pay function with its own payment logic 
2. PaymentGatewayFactory is a factory pattern decides which strategy to instantiate at runtime, it designed with dynamic logic which mean there's no need to modify it when adding a new gateway 

## example :
 you need to add more gateway only you need to do is create new class implements PaymentGatewayInterface and add the gateway logic to pay and add the gateway record in table payment_gateways with correct path of the gateway class






