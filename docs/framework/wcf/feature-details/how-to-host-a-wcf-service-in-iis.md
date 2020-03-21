---
title: Практическое руководство. Размещение службы WCF в IIS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 580b380a6c6349c6a4efa26e3eefe38bd660fa1b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184922"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="18b8d-102">Практическое руководство. Размещение службы WCF в IIS</span><span class="sxs-lookup"><span data-stu-id="18b8d-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="18b8d-103">В этой теме излагаются основные шаги, необходимые для создания службы Windows Communication Foundation (WCF), которая размещается в информационных службах Интернета (IIS).</span><span class="sxs-lookup"><span data-stu-id="18b8d-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="18b8d-104">Предполагается, что читатель знаком со службами IIS и может использовать средство управления IIS для создания приложений служб IIS и управления такими приложениями.</span><span class="sxs-lookup"><span data-stu-id="18b8d-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="18b8d-105">Для получения дополнительной информации о IIS см [Интернет информационных услуг](https://www.iis.net/).</span><span class="sxs-lookup"><span data-stu-id="18b8d-105">For more information about IIS see [Internet Information Services](https://www.iis.net/).</span></span> <span data-ttu-id="18b8d-106">Служба WCF, работающая в среде IIS, в полной мере использует такие функции IIS, как переработка процессов, простоя, мониторинг работоспособности процессов и активация на основе сообщений.</span><span class="sxs-lookup"><span data-stu-id="18b8d-106">A WCF service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="18b8d-107">Для реализации этого варианта размещения требуется правильно настроить службу IIS, но не требуется включать в приложение код размещения.</span><span class="sxs-lookup"><span data-stu-id="18b8d-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="18b8d-108">Размещение в службах IIS возможно только при использовании транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="18b8d-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="18b8d-109">Для получения дополнительной информации о том, как взаимодействуют WCF и ASP.NET, см [ASP.NET.](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)</span><span class="sxs-lookup"><span data-stu-id="18b8d-109">For more information about how WCF and ASP.NET interact, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="18b8d-110">Для получения дополнительной информации о настройке безопасности, [см.](../../../../docs/framework/wcf/feature-details/security.md)</span><span class="sxs-lookup"><span data-stu-id="18b8d-110">For more information about configuring security, see [Security](../../../../docs/framework/wcf/feature-details/security.md).</span></span>  
  
 <span data-ttu-id="18b8d-111">Для исходной копии этого [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)примера см.</span><span class="sxs-lookup"><span data-stu-id="18b8d-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="18b8d-112">Создание службы, размещенной в IIS</span><span class="sxs-lookup"><span data-stu-id="18b8d-112">To create a service hosted by IIS</span></span>  
  
1. <span data-ttu-id="18b8d-113">Убедитесь, что службы IIS установлены и выполняются на компьютере.</span><span class="sxs-lookup"><span data-stu-id="18b8d-113">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="18b8d-114">Для получения дополнительной информации об установке и настройке IIS смотрите [Установка и настройка IIS 7.0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)</span><span class="sxs-lookup"><span data-stu-id="18b8d-114">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)</span></span>  
  
2. <span data-ttu-id="18b8d-115">Создайте новую папку для файлов приложений под названием "IISHostedCalcService", убедитесь, что ASP.NET имеет доступ к содержимому папки, и используйте инструмент управления IIS для создания нового приложения IIS, которое физически находится в этом каталоге приложений.</span><span class="sxs-lookup"><span data-stu-id="18b8d-115">Create a new folder for your application files called "IISHostedCalcService", ensure that ASP.NET has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="18b8d-116">Создайте для каталога приложения псевдоним «IISHostedCalc».</span><span class="sxs-lookup"><span data-stu-id="18b8d-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3. <span data-ttu-id="18b8d-117">Создайте в каталоге приложения новый файл с именем «service.svc».</span><span class="sxs-lookup"><span data-stu-id="18b8d-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="18b8d-118">Оторите этот файл, добавив следующий @ServiceHost элемент.</span><span class="sxs-lookup"><span data-stu-id="18b8d-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
   ```
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>
   ```  
  
4. <span data-ttu-id="18b8d-119">В каталоге приложения создайте подкаталог App_Code.</span><span class="sxs-lookup"><span data-stu-id="18b8d-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5. <span data-ttu-id="18b8d-120">Создайте файл кода с именем Service.cs во вложенном каталоге App_Code.</span><span class="sxs-lookup"><span data-stu-id="18b8d-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6. <span data-ttu-id="18b8d-121">Добавьте следующие операторы using в начало файла Service.cs.</span><span class="sxs-lookup"><span data-stu-id="18b8d-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. <span data-ttu-id="18b8d-122">Добавьте следующее объявление пространства имен после операторов using.</span><span class="sxs-lookup"><span data-stu-id="18b8d-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. <span data-ttu-id="18b8d-123">Определите контракт службы в пределах объявления пространства имен, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="18b8d-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="18b8d-124">Реализуйте контракт службы после определения контракта службы, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="18b8d-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="18b8d-125">Создайте в каталоге приложения файл с именем Web.config и добавьте в него следующий код конфигурации.</span><span class="sxs-lookup"><span data-stu-id="18b8d-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="18b8d-126">Во время выполнения инфраструктура WCF использует информацию для построения конечной точки, с помощью которого клиентские приложения могут общаться.</span><span class="sxs-lookup"><span data-stu-id="18b8d-126">At runtime, the WCF infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]
  
     <span data-ttu-id="18b8d-127">В этом примере конечные точки явно задаются в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="18b8d-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="18b8d-128">Если в службу не добавлена ни одна конечная точка, то среда выполнения добавляет конечные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="18b8d-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="18b8d-129">Для получения дополнительной информации о конечных точках по умолчанию, привязки и поведении [см. Упрощенную конфигурацию](../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенную конфигурацию для WCF Services.](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)</span><span class="sxs-lookup"><span data-stu-id="18b8d-129">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="18b8d-130">Чтобы проверить правильность размещения службы, откройте экземпляр окна Internet Explorer и перейдите по URL-адресу службы: `http://localhost/IISHostedCalc/Service.svc`.</span><span class="sxs-lookup"><span data-stu-id="18b8d-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="18b8d-131">Пример</span><span class="sxs-lookup"><span data-stu-id="18b8d-131">Example</span></span>  
 <span data-ttu-id="18b8d-132">Далее представлен полный код службы калькулятора, размещаемой в IIS.</span><span class="sxs-lookup"><span data-stu-id="18b8d-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="18b8d-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="18b8d-133">See also</span></span>

- [<span data-ttu-id="18b8d-134">Размещение в службах IIS</span><span class="sxs-lookup"><span data-stu-id="18b8d-134">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [<span data-ttu-id="18b8d-135">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="18b8d-135">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="18b8d-136">Службы WCF и ASP.NET</span><span class="sxs-lookup"><span data-stu-id="18b8d-136">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [<span data-ttu-id="18b8d-137">Безопасность</span><span class="sxs-lookup"><span data-stu-id="18b8d-137">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
- <span data-ttu-id="18b8d-138">[Функции размещения Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="18b8d-138">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
