---
title: Практическое руководство. Настройка базового клиента Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: 3f267edf87711de8a5969e3e0b577648008c5a75
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46524867"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a>Практическое руководство. Настройка базового клиента Windows Communication Foundation

Это пятая из шести задач, необходимых для создания базового приложения Windows Communication Foundation (WCF). Общие сведения обо всех шести задачах можно получить в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).

В этом разделе рассматривается файл конфигурации клиента, который был создан с помощью **Add Service Reference** средств Visual Studio или [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Настройка клиента состоит из задания конечной точки, которую клиент использует для получения доступа к службе. Конечная точка имеет адрес, привязку и контракт, и каждый из них должен быть указан при настройке клиента.

## <a name="configure-a-windows-communication-foundation-client"></a>Настройка клиента Windows Communication Foundation

Откройте сформированный файл конфигурации (App.config) из проекта GettingStartedClient. В следующем примере приведено представление созданного файла конфигурации. В разделе [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) найдите [ \<конечной точки >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) элемент.

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

В этом примере настраивается конечная точка, которую клиент использует для доступа к службе, которая находится по следующему адресу: `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`.

В элементе конечной точки указано, что контракт службы `ServiceReference1.ICalculator` используется для взаимодействия между клиентом и службой WCF. Канал WCF настроен с привязкой <xref:System.ServiceModel.WSHttpBinding>, предоставленной системой. Этот контракт был сформирован с помощью **Add Service Reference** в Visual Studio. В сущности, это является копией контракта, определенного в проекте GettingStartedLib. Привязка <xref:System.ServiceModel.WSHttpBinding> задает HTTP в качестве транспорта, уровень безопасности и другие данные конфигурации.

Дополнительные сведения о способах использования созданного клиента с помощью этой конфигурации см. в разделе [как: использовать клиент](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).

## <a name="next-steps"></a>Следующие шаги

> [!div class="nextstepaction"]
> [Практическое: использование клиента WCF](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

## <a name="see-also"></a>См. также

- [Использование привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Практическое руководство. Создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)