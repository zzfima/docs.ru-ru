---
title: Практическое руководство. Настройка базового клиента Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: c03bf37c737a19b0a90f12e7ad5db78b75323f5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499279"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a>Практическое руководство. Настройка базового клиента Windows Communication Foundation
Это пятая из шести шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF). Общие сведения обо всех шести задач см. в разделе [учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md) раздела.  
  
 В этом разделе описывается файл конфигурации клиента, который был создан с помощью функции добавления ссылки на службу [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] или [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Настройка клиента состоит из задания конечной точки, которую клиент использует для получения доступа к службе. Конечная точка имеет адрес, привязку и контракт, и при настройке клиента необходимо задать все эти элементы.  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a>Настройка клиента Windows Communication Foundation  
  
1.  Откройте сформированный файл конфигурации (App.config) из проекта GettingStartedClient. В следующем примере приведено представление созданного файла конфигурации. В разделе [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) найдите [ \<endpoint >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) элемента.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
          <!-- specifies the version of WCF to use-->  
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <!-- Uses wsHttpBinding-->  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <!-- specifies the endpoint to use when calling the service -->  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration>   
    ```  
  
     В этом примере настраивается конечная точка, клиент использует для доступа к службе, которая находится по следующему адресу: http://localhost:8000/ServiceModelSamples/Service/CalculatorService  
  
     В элементе конечной точки указано, что контракт службы `ServiceReference1.ICalculator` используется для взаимодействия между клиентом и службой WCF. Канал WCF настроен с предоставленной системой <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>. Этот контракт был сформирован с использованием функции добавления ссылки на службу в Visual Studio. В сущности, это является копией контракта, определенного в проекте GettingStartedLib. <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> Привязки задает HTTP в качестве транспорта, уровень безопасности и другие сведения о конфигурации.  
  
2.  Дополнительные сведения о способах использования созданного клиента в этой конфигурации см. в разделе [как: использовать клиент](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
## <a name="see-also"></a>См. также  
 [Использование привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Практическое руководство. Создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)
