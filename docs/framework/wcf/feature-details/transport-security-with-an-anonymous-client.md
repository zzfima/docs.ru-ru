---
title: Безопасность транспорта с анонимным клиентом
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 2b52a32db1f1ac02f9204198a4cda5d4cb157486
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="transport-security-with-an-anonymous-client"></a>Безопасность транспорта с анонимным клиентом
В этом сценарии [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для обеспечения конфиденциальности и целостности используется безопасность транспорта (HTTPS). Сервер должен пройти проверку подлинности с использованием сертификата SSL, и клиенты должны доверять сертификату сервера. Проверка подлинности клиента не выполняется никаким механизмом и, следовательно, клиент является анонимным.  
  
 Пример приложения см. в разделе [безопасность транспорта WS](../../../../docs/framework/wcf/samples/ws-transport-security.md). Дополнительные сведения о безопасности транспорта см. в разделе [Общие сведения о безопасности транспорта](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).  
  
 Дополнительные сведения об использовании сертификата со службой см. в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) и [как: Настройка порта с SSL-сертификата](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
 ![Использование безопасности транспорта с анонимным клиентом](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Режим безопасности|Transport|  
|Взаимодействие|С существующими веб-службами и клиентами|  
|Проверка подлинности (сервера)<br /><br /> Проверка подлинности (клиента)|Да<br /><br /> На уровне приложения (без поддержки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)])|  
|Целостность|Да|  
|Конфиденциальность|Да|  
|Transport|HTTPS|  
|Привязка|<<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>|  
  
## <a name="service"></a>Служба  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо. Выполните одно из следующих действий.  
  
-   Создайте автономную службу, используя код без конфигурации.  
  
-   Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.  
  
### <a name="code"></a>Код  
 В следующем коде показано создание конечной точки с использованием безопасности транспорта:  
  
 [!code-csharp[c_SecurityScenarios#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
 [!code-vb[c_SecurityScenarios#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]  
  
### <a name="configuration"></a>Конфигурация  
 В следующем коде настраивается та же конечная точка с использованием конфигурации. Проверка подлинности клиента не выполняется никаким механизмом и, следовательно, клиент является анонимным.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>"Клиент";  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо. Выполните одно из следующих действий.  
  
-   Создайте автономный клиент, используя код (и код клиента).  
  
-   Создайте клиент, который не определяет никаких адресов конечных точек. Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации. Например:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a>Код  
 [!code-csharp[c_SecurityScenarios#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
 [!code-vb[c_SecurityScenarios#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]  
  
### <a name="configuration"></a>Конфигурация  
 Вместо кода для настройки службы можно использовать следующую конфигурацию.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Безопасность транспорта WS](../../../../docs/framework/wcf/samples/ws-transport-security.md)  
 [Общие сведения о безопасности транспорта](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 [Модель безопасности для Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
