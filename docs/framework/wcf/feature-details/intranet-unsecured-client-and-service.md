---
title: "Незащищенные интранет-клиент и служба | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
caps.latest.revision: 20
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 20
---
# Незащищенные интранет-клиент и служба
На следующем рисунке показана простая служба [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], разработанная для предоставления приложению [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сведений о защищенной частной сети.  Безопасность не требуется, поскольку данные имеют низкий уровень важности, предполагается, что сеть в своей основе является защищенной, или безопасность обеспечивается уровнем, расположенным ниже инфраструктуры [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 ![Сценарий с незащищенными клиентом интрасети и службой](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")  
  
|Характеристика|Описание|  
|--------------------|--------------|  
|Режим безопасности|Нет|  
|Transport|TCP|  
|Привязка|<xref:System.ServiceModel.NetTcpBinding>|  
|Взаимодействие|Только [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]|  
|Аутентификация|Нет|  
|Целостность|Нет|  
|Конфиденциальность|Нет|  
  
## Служба  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо.  Выполните одно из следующих действий.  
  
-   Создайте автономную службу, используя код без конфигурации.  
  
-   Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.  
  
### Код  
 В следующем коде показано создание конечной точки без обеспечения безопасности.  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### Конфигурация  
 В следующем коде настраивается та же конечная точка с использованием конфигурации.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""   
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"   
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## Клиент  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо.  Выполните одно из следующих действий.  
  
-   Создайте автономный клиент, используя код \(и код клиента\).  
  
-   Создайте клиент, который не определяет никаких адресов конечных точек.  Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.  Например:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### Код  
 В следующем коде показан основной клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], обращающийся к незащищенной конечной точке по протоколу TCP.  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### Конфигурация  
 Следующий код конфигурации применяется к клиенту.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"   
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"   
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## См. также  
 <xref:System.ServiceModel.NetTcpBinding>   
 [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Модель безопасности для Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)