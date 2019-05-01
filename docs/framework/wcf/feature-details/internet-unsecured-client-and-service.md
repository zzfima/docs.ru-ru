---
title: Незащищенные интернет-клиент и служба
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
ms.openlocfilehash: ca6b028ef20095d6faeb125151772eedf1500fa0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038731"
---
# <a name="internet-unsecured-client-and-service"></a>Незащищенные интернет-клиент и служба
Ниже показан пример public, незащищенных клиента Windows Communication Foundation (WCF) и службы:  
  
 ![Снимок экрана, показывающий незащищенный ситуации Интернета](./media/internet-unsecured-client-and-service/public-unsecured-internet.gif)  
  
|Характеристика|Описание|  
|--------------------|-----------------|  
|Режим безопасности|Нет|  
|Transport|HTTP|  
|Привязка|<xref:System.ServiceModel.BasicHttpBinding> в коде или [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) элемент в конфигурации.|  
|Взаимодействие|С существующими службами и клиентами веб-служб|  
|Проверка подлинности|Нет|  
|Целостность|Нет|  
|Конфиденциальность|Нет|  
  
## <a name="service"></a>Служба  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо. Выполните одно из следующих действий.  
  
- Создайте автономную службу, используя код без конфигурации.  
  
- Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.  
  
### <a name="code"></a>Код  
 В следующем коде показано создание конечной точки без безопасности. По умолчанию режим безопасности <xref:System.ServiceModel.BasicHttpBinding> задан режим <xref:System.ServiceModel.BasicHttpSecurityMode.None>.  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a>Конфигурация службы  
 В следующем коде настраивается та же конечная точка с использованием конфигурации.  
  
```xml  
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
  
## <a name="client"></a>"Клиент";  
 Предполагается, что представленные ниже код и конфигурация выполняются независимо. Выполните одно из следующих действий.  
  
- Создайте автономный клиент, используя код (и код клиента).  
  
- Создайте клиент, который не определяет никаких адресов конечных точек. Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации. Пример:  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a>Код  
 В следующем коде показано базового клиента WCF, который обращается к незащищенной конечной точке.  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a>Конфигурация клиента  
 Следующий код служит для настройки клиента.  
  
```xml  
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
  
## <a name="see-also"></a>См. также

- [Типовые сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
- [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Модель безопасности для Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
