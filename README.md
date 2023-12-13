# Mise en oeuvre d'une architecture Micro Service avec Spring Cloud #

### Créer une application de e-commerce basée sur les micro services : ###

1. Consul Discovery
2. Spring Cloud Config
3. Spring Cloud Gateway
4. Customer-service
5. Inventory Service
6. Order Service
7. Consul Config (Billing Service)
8. Vault (Billing Service)
9. Frontend Web avec Angular
##    ##

<details>
 <summary>1-Consul</summary><br>
![1][consul](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/93c6fea1-c200-4edb-99a9-558a9d561dfb)<br>
</details>

<details>
<summary>2-Config service</summary><br>

-Ce fichier contient le lien du référentiel qui regroupe tous les fichiers de configuration d'autres services :<br>
![config](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/cc5286b3-eb65-4674-a681-67894ccb5b1a)<br><br>
-l'annotation @EnableConfigServer active le serveur de configuration, tandis que l'annotation @EnableDiscoveryClient active le client de découverte pour faciliter la gestion des microservices dans un environnement distribué.<br>

![discovery](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/d691b956-af8d-4485-9478-5d3b2738196e)<br><br>
-aprés le démmarage de config service il s'ajoute au niveau de consul.<br>

</details>

<details>
  <summary>3-Customer service</summary>
  -L'entité Customer :<br>

![entitecustomer](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/31ea6c20-61fb-4a0f-b7c4-3bdc0425c23a)<br>
-La ligne spring.config.import=optional:configserver:http://localhost:8080 dans un fichier de configuration indique que Customer-service  doit importer sa configuration depuis un serveur de configuration

distant (Config Server) .<br><br>
![configcustomer](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/f6fbdb10-42ea-41b7-b429-13819c03ebaa)<br>
Le fichier de configuration distant :<br>
![configcustomerdistant](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/ef940cfd-8d9c-46b7-b548-d6fe84705e8a)<br>

</details>


<details>
  <summary>4-inventory service</summary>

![configinventory](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/5e1765ae-17c2-43fa-9148-de2fb11a95d9)<br>
![configinventorydistant](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/f135ae5c-95ff-404e-b763-cbd24f917650)<br>
-L'entité Product :<br><br>
![entiteinventory](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/e4adf308-a30e-4166-924e-2081a2fcc2d0)<br>
![inventorysvapplication](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/66bca6de-ba2d-44f2-b6f4-60a0ef8180bf)<br>


</details>
<details>
  <summary>5-Gateway service</summary>

![gateway](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/1b0adc53-e885-4f26-9295-a5441b16f512)<br><br>
Gateway service configure une passerelle (gateway) utilisant Spring Cloud Gateway et utilise la découverte de service pour configurer dynamiquement les routes de la passerelle à partir d'un service de découverte. Cela offre une flexibilité et une évolutivité accrues dans un environnement de microservices où de nouveaux services peuvent être ajoutés sans avoir à mettre à jour manuellement la configuration de la passerelle.
![gatewayconfig2](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/c730d16d-245c-4773-92bf-2823c8321289)<br><br>
![gatewayconfig](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/d7587176-3558-4db2-8ed1-864bdcd4471a) <br><br>


</details>
<details>
  <summary>6-Order service</summary>

![order](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/7bf4f54a-c462-497d-b76f-377b27c86173)<br><br>
![customer](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/47ff892c-6c6d-46e5-95d2-33dda3b797d2)<br><br>
cette interface Feign définit les méthodes permettant d'interagir avec le service "costumer-service" via des requêtes HTTP GET:
![customer2](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/338d01ff-6376-4793-b36c-11122bc84d8d)<br><br>
L'application initialise des données de commande de manière aléatoire en utilisant des clients Feign pour récupérer des informations depuis d'autres services (customer et inventory). <br>
![customer3](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/38c9e52f-fcd9-48bb-a841-34cd86c0b0be)

</details>

<details>
  <summary>7-Billing service</summary>

démarrage du vault :
![vault2](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/cc06fd10-4cff-4457-8965-3dbc977cfb6d)<br><br>
![vault1](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/15ea6d28-cdcf-4c5b-9e08-4082821e30d5)<br><br>
-Dans le fichier de configuration, on définit le token Vault :

![vault3](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/138308cc-5548-46ec-a3c1-319379488a01)<br><br>

-Configuration des secrets avec Vault et Consul  :

</details>

<details>
  <summary>8-Client Angular:</summary>
.....
</details>

