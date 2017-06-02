---
title: "Незащищенные интернет-клиент и служба | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
caps.latest.revision: 17
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 17
---
# Незащищенные интернет-клиент и служба
В следующей иллюстрации показан пример открытых незащищенных клиента и службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
 ![Сценарий с незащищенными клиентом Интернета и службой](../../../../docs/framework/wcf/feature-details/media/publicunsecured.gif "publicUnsecured")  
  
|Характеристика|Описание|  
|--------------------|--------------|  
|Режим безопасности|Нет|  
|Транспорт|HTTP|  
|Привязка|<xref:System.ServiceModel.BasicHttpBinding> в коде или элемент [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)в конфигурации.|  
|Взаимодействие|С существующими службами и клиентами веб\-служб|  
|Аутентификация|Нет|  
|Целостность|Нет|  
|Конфиденциальность|Нет|  
  
## Служба  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо.Выполните одно из следующих действий.  
  
-   Создайте автономную службу, используя код без конфигурации.  
  
-   Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.  
  
### Код  
 В следующем коде показано создание конечной точки без безопасности.По умолчанию режим безопасности <xref:System.ServiceModel.BasicHttpBinding> задан режим <xref:System.ServiceModel.BasicHttpSecurityMode>.  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### Конфигурация службы  
 В следующем коде настраивается та же конечная точка с использованием конфигурации.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="basicHttpBinding"  
                  bindingConfiguration="Basic_Unsecured"   
                  name="BasicHttp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="Basic_Unsecured" />  
      </basicHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## Клиент  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо.Выполните одно из следующих действий.  
  
-   Создайте автономный клиент, используя код \(и код клиента\).  
  
-   Создайте клиент, который не определяет никаких адресов конечных точек.Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.Пример:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### Код  
 Приведенный ниже код демонстрирует основной клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], который имеет доступ к незащищенной конечной точке.  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### Конфигурация клиента  
 Следующий код служит для настройки клиента.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="BasicHttpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator/Unsecured"  
          binding="basicHttpBinding"   
          bindingConfiguration="BasicHttpBinding_ICalculator"  
          contract="ICalculator"   
          name="BasicHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## См. также  
 [Типовые сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)   
 [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Модель безопасности для Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x419)