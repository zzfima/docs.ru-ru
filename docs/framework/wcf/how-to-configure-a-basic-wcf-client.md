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
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a><span data-ttu-id="5f6f6-102">Практическое руководство. Настройка базового клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="5f6f6-102">How to: Configure a Basic Windows Communication Foundation Client</span></span>
<span data-ttu-id="5f6f6-103">Это пятая из шести шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5f6f6-103">This is the fifth of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="5f6f6-104">Общие сведения обо всех шести задач см. в разделе [учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="5f6f6-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="5f6f6-105">В этом разделе описывается файл конфигурации клиента, который был создан с помощью функции добавления ссылки на службу [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] или [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="5f6f6-105">This topic discusses the client configuration file that was generated using the Add Service Reference functionality of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="5f6f6-106">Настройка клиента состоит из задания конечной точки, которую клиент использует для получения доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="5f6f6-106">Configuring the client consists of specifying the endpoint that the client uses to access the service.</span></span> <span data-ttu-id="5f6f6-107">Конечная точка имеет адрес, привязку и контракт, и при настройке клиента необходимо задать все эти элементы.</span><span class="sxs-lookup"><span data-stu-id="5f6f6-107">An endpoint has an address, a binding and a contract, and each of these must be specified in the process of configuring the client.</span></span>  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a><span data-ttu-id="5f6f6-108">Настройка клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="5f6f6-108">To configure a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="5f6f6-109">Откройте сформированный файл конфигурации (App.config) из проекта GettingStartedClient.</span><span class="sxs-lookup"><span data-stu-id="5f6f6-109">Open the generated configuration file (App.config) from the GettingStartedClient project.</span></span> <span data-ttu-id="5f6f6-110">В следующем примере приведено представление созданного файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5f6f6-110">The following example is a view of the generated configuration file.</span></span> <span data-ttu-id="5f6f6-111">В разделе [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) найдите [ \<endpoint >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) элемента.</span><span class="sxs-lookup"><span data-stu-id="5f6f6-111">Under the [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, find the [\<endpoint>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
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
  
     <span data-ttu-id="5f6f6-112">В этом примере настраивается конечная точка, клиент использует для доступа к службе, которая находится по следующему адресу: http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span><span class="sxs-lookup"><span data-stu-id="5f6f6-112">This example configures the endpoint that the client uses to access the service that is located at the following address: http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span></span>  
  
     <span data-ttu-id="5f6f6-113">В элементе конечной точки указано, что контракт службы `ServiceReference1.ICalculator` используется для взаимодействия между клиентом и службой WCF.</span><span class="sxs-lookup"><span data-stu-id="5f6f6-113">The endpoint element specifies that the `ServiceReference1.ICalculator` service contract is used for communication between the WCF client and service.</span></span> <span data-ttu-id="5f6f6-114">Канал WCF настроен с предоставленной системой <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="5f6f6-114">The WCF channel is configured with the system-provided <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>.</span></span> <span data-ttu-id="5f6f6-115">Этот контракт был сформирован с использованием функции добавления ссылки на службу в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5f6f6-115">This contract was generated by using Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="5f6f6-116">В сущности, это является копией контракта, определенного в проекте GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="5f6f6-116">It is essentially a copy of the contract that was defined in the GettingStartedLib project.</span></span> <span data-ttu-id="5f6f6-117"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> Привязки задает HTTP в качестве транспорта, уровень безопасности и другие сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5f6f6-117">The <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>  
  
2.  <span data-ttu-id="5f6f6-118">Дополнительные сведения о способах использования созданного клиента в этой конфигурации см. в разделе [как: использовать клиент](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="5f6f6-118">For more information about how to use the generated client with this configuration, see [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6f6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5f6f6-119">See Also</span></span>  
 [<span data-ttu-id="5f6f6-120">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5f6f6-120">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="5f6f6-121">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="5f6f6-121">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="5f6f6-122">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="5f6f6-122">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="5f6f6-123">Начало работы</span><span class="sxs-lookup"><span data-stu-id="5f6f6-123">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="5f6f6-124">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="5f6f6-124">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
