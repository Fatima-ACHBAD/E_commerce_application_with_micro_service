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
![2][config](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/cc5286b3-eb65-4674-a681-67894ccb5b1a)<br><br>
-l'annotation @EnableConfigServer active le serveur de configuration, tandis que l'annotation @EnableDiscoveryClient active le client de découverte pour faciliter la gestion des microservices dans un environnement distribué.<br>

![3][discovery](https://github.com/Fatima-ACHBAD/E_commerce_application_with_micro_service/assets/100408189/d691b956-af8d-4485-9478-5d3b2738196e)<br><br>
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

cdc