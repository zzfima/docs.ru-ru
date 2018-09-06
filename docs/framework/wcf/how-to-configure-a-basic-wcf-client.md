---
title: Практическое руководство. Настройка базового клиента Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: 2866cbd5862bf55286fc771823488cf913863de2
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855859"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a>Практическое руководство. Настройка базового клиента Windows Communication Foundation
Это пятая из шести задач, необходимых для создания базового приложения Windows Communication Foundation (WCF). Общие сведения обо всех шести задачах можно получить в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 В этом разделе рассматривается файл конфигурации клиента, который был создан с помощью функции добавления служебной ссылки из [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] или [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Настройка клиента состоит из задания конечной точки, которую клиент использует для получения доступа к службе. Конечная точка имеет адрес, привязку и контракт, и при настройке клиента необходимо задать все эти элементы.  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a>Настройка клиента Windows Communication Foundation  
  
1.  Откройте сформированный файл конфигурации (App.config) из проекта GettingStartedClient. В следующем примере приведено представление созданного файла конфигурации. В разделе [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) найдите [ \<конечной точки >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) элемент.  
  
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
  
     В этом примере настраивается конечная точка, которую клиент использует для доступа к службе, которая находится по следующему адресу: http://localhost:8000/ServiceModelSamples/Service/CalculatorService  
  
     В элементе конечной точки указано, что контракт службы `ServiceReference1.ICalculator` используется для взаимодействия между клиентом и службой WCF. Канал WCF настроен с привязкой <xref:System.ServiceModel.WSHttpBinding>, предоставленной системой. Этот контракт был сформирован с использованием функции добавления ссылки на службу в Visual Studio. В сущности, это является копией контракта, определенного в проекте GettingStartedLib. Привязка <xref:System.ServiceModel.WSHttpBinding> задает HTTP в качестве транспорта, уровень безопасности и другие данные конфигурации.  
  
2.  Дополнительные сведения о способах использования созданного клиента с помощью этой конфигурации см. в разделе [как: использовать клиент](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
## <a name="see-also"></a>См. также  
 [Использование привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Практическое руководство. Создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)
