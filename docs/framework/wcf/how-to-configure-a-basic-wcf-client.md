---
title: Практическое руководство. Настройка базового клиента Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: 3f267edf87711de8a5969e3e0b577648008c5a75
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46323643"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a><span data-ttu-id="42ce3-102">Практическое руководство. Настройка базового клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="42ce3-102">How to: Configure a Basic Windows Communication Foundation Client</span></span>

<span data-ttu-id="42ce3-103">Это пятая из шести задач, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="42ce3-103">This is the fifth of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="42ce3-104">Общие сведения обо всех шести задачах можно получить в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="42ce3-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="42ce3-105">В этом разделе рассматривается файл конфигурации клиента, который был создан с помощью **Add Service Reference** средств Visual Studio или [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="42ce3-105">This topic discusses the client configuration file that was generated using the **Add Service Reference** functionality of Visual Studio or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="42ce3-106">Настройка клиента состоит из задания конечной точки, которую клиент использует для получения доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="42ce3-106">Configuring the client consists of specifying the endpoint that the client uses to access the service.</span></span> <span data-ttu-id="42ce3-107">Конечная точка имеет адрес, привязку и контракт, и каждый из них должен быть указан при настройке клиента.</span><span class="sxs-lookup"><span data-stu-id="42ce3-107">An endpoint has an address, a binding, and a contract, and each of these must be specified in the process of configuring the client.</span></span>

## <a name="configure-a-windows-communication-foundation-client"></a><span data-ttu-id="42ce3-108">Настройка клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="42ce3-108">Configure a Windows Communication Foundation client</span></span>

<span data-ttu-id="42ce3-109">Откройте сформированный файл конфигурации (App.config) из проекта GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="42ce3-109">Open the generated configuration file (App.config) from the GettingStartedClient project.</span></span> <span data-ttu-id="42ce3-110">В следующем примере приведено представление созданного файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="42ce3-110">The following example is a view of the generated configuration file.</span></span> <span data-ttu-id="42ce3-111">В разделе [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) найдите [ \<конечной точки >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) элемент.</span><span class="sxs-lookup"><span data-stu-id="42ce3-111">Under the [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, find the [\<endpoint>](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>

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

<span data-ttu-id="42ce3-112">В этом примере настраивается конечная точка, которую клиент использует для доступа к службе, которая находится по следующему адресу: `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="42ce3-112">This example configures the endpoint that the client uses to access the service that is located at the following address: `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`.</span></span>

<span data-ttu-id="42ce3-113">В элементе конечной точки указано, что контракт службы `ServiceReference1.ICalculator` используется для взаимодействия между клиентом и службой WCF.</span><span class="sxs-lookup"><span data-stu-id="42ce3-113">The endpoint element specifies that the `ServiceReference1.ICalculator` service contract is used for communication between the WCF client and service.</span></span> <span data-ttu-id="42ce3-114">Канал WCF настроен с привязкой <xref:System.ServiceModel.WSHttpBinding>, предоставленной системой.</span><span class="sxs-lookup"><span data-stu-id="42ce3-114">The WCF channel is configured with the system-provided <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="42ce3-115">Этот контракт был сформирован с помощью **Add Service Reference** в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="42ce3-115">This contract was generated by using **Add Service Reference** in Visual Studio.</span></span> <span data-ttu-id="42ce3-116">В сущности, это является копией контракта, определенного в проекте GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="42ce3-116">It is essentially a copy of the contract that was defined in the GettingStartedLib project.</span></span> <span data-ttu-id="42ce3-117">Привязка <xref:System.ServiceModel.WSHttpBinding> задает HTTP в качестве транспорта, уровень безопасности и другие данные конфигурации.</span><span class="sxs-lookup"><span data-stu-id="42ce3-117">The <xref:System.ServiceModel.WSHttpBinding> binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

<span data-ttu-id="42ce3-118">Дополнительные сведения о способах использования созданного клиента с помощью этой конфигурации см. в разделе [как: использовать клиент](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="42ce3-118">For more information about how to use the generated client with this configuration, see [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="42ce3-119">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="42ce3-119">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="42ce3-120">Практическое: использование клиента WCF</span><span class="sxs-lookup"><span data-stu-id="42ce3-120">How to: Use a WCF client</span></span>](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

## <a name="see-also"></a><span data-ttu-id="42ce3-121">См. также</span><span class="sxs-lookup"><span data-stu-id="42ce3-121">See also</span></span>

- [<span data-ttu-id="42ce3-122">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="42ce3-122">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="42ce3-123">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="42ce3-123">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="42ce3-124">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="42ce3-124">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="42ce3-125">Начало работы</span><span class="sxs-lookup"><span data-stu-id="42ce3-125">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="42ce3-126">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="42ce3-126">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)