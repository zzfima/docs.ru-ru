---
title: Практическое руководство. Размещение службы WCF в IIS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: f106ce1bca67f8b88df0835496eea0b3297ac946
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59309684"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="de9a9-102">Практическое руководство. Размещение службы WCF в IIS</span><span class="sxs-lookup"><span data-stu-id="de9a9-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="de9a9-103">В этом разделе описаны основные шаги для создания службы Windows Communication Foundation (WCF), размещенного в Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="de9a9-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="de9a9-104">Предполагается, что читатель знаком со службами IIS и может использовать средство управления IIS для создания приложений служб IIS и управления такими приложениями.</span><span class="sxs-lookup"><span data-stu-id="de9a9-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="de9a9-105">Дополнительные сведения о службах IIS см. в разделе [Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=132449).</span><span class="sxs-lookup"><span data-stu-id="de9a9-105">For more information about IIS see [Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=132449).</span></span> <span data-ttu-id="de9a9-106">Службы WCF, которая выполняется в среде IIS использует все преимущества функции IIS, такие как перезапуск процессов, бездействует, завершение работы, наблюдение за работоспособностью процессов и активация на основе сообщений.</span><span class="sxs-lookup"><span data-stu-id="de9a9-106">A WCF service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="de9a9-107">Для реализации этого варианта размещения требуется правильно настроить службу IIS, но не требуется включать в приложение код размещения.</span><span class="sxs-lookup"><span data-stu-id="de9a9-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="de9a9-108">Размещение в службах IIS возможно только при использовании транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="de9a9-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="de9a9-109">Дополнительные сведения о том, как WCF и [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] взаимодействовать, см. в разделе [службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="de9a9-109">For more information about how WCF and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interact, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="de9a9-110">Дополнительные сведения о настройке безопасности см. в разделе [безопасности](../../../../docs/framework/wcf/feature-details/security.md).</span><span class="sxs-lookup"><span data-stu-id="de9a9-110">For more information about configuring security, see [Security](../../../../docs/framework/wcf/feature-details/security.md).</span></span>  
  
 <span data-ttu-id="de9a9-111">Копию исходного кода в этом примере, см. в разделе [IIS размещение с помощью встроенного кода](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span><span class="sxs-lookup"><span data-stu-id="de9a9-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="de9a9-112">Создание службы, размещенной в IIS</span><span class="sxs-lookup"><span data-stu-id="de9a9-112">To create a service hosted by IIS</span></span>  
  
1. <span data-ttu-id="de9a9-113">Убедитесь, что службы IIS установлены и выполняются на компьютере.</span><span class="sxs-lookup"><span data-stu-id="de9a9-113">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="de9a9-114">Дополнительные сведения об установке и настройке служб IIS см. в разделе [Установка и настройка IIS 7.0](https://go.microsoft.com/fwlink/?LinkID=132128)</span><span class="sxs-lookup"><span data-stu-id="de9a9-114">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](https://go.microsoft.com/fwlink/?LinkID=132128)</span></span>  
  
2. <span data-ttu-id="de9a9-115">Создайте новую папку с именем IISHostedCalcService для файлов приложения, убедитесь, что [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] имеет доступ к содержимому этой папки, и воспользуйтесь средством управления IIS для создания нового приложения служб IIS, которое физически расположено в каталоге этого приложения.</span><span class="sxs-lookup"><span data-stu-id="de9a9-115">Create a new folder for your application files called "IISHostedCalcService", ensure that [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="de9a9-116">Создайте для каталога приложения псевдоним «IISHostedCalc».</span><span class="sxs-lookup"><span data-stu-id="de9a9-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3. <span data-ttu-id="de9a9-117">Создайте в каталоге приложения новый файл с именем «service.svc».</span><span class="sxs-lookup"><span data-stu-id="de9a9-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="de9a9-118">Измените этот файл, добавив следующий @ServiceHost элемент.</span><span class="sxs-lookup"><span data-stu-id="de9a9-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4. <span data-ttu-id="de9a9-119">В каталоге приложения создайте подкаталог App_Code.</span><span class="sxs-lookup"><span data-stu-id="de9a9-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5. <span data-ttu-id="de9a9-120">Создайте файл кода с именем Service.cs во вложенном каталоге App_Code.</span><span class="sxs-lookup"><span data-stu-id="de9a9-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6. <span data-ttu-id="de9a9-121">Добавьте следующие операторы using в начало файла Service.cs.</span><span class="sxs-lookup"><span data-stu-id="de9a9-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. <span data-ttu-id="de9a9-122">Добавьте следующее объявление пространства имен после операторов using.</span><span class="sxs-lookup"><span data-stu-id="de9a9-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. <span data-ttu-id="de9a9-123">Определите контракт службы в пределах объявления пространства имен, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="de9a9-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="de9a9-124">Реализуйте контракт службы после определения контракта службы, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="de9a9-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="de9a9-125">Создайте в каталоге приложения файл с именем Web.config и добавьте в него следующий код конфигурации.</span><span class="sxs-lookup"><span data-stu-id="de9a9-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="de9a9-126">Во время выполнения инфраструктура WCF использует сведения для создания клиентских приложений для взаимодействия с конечной точки.</span><span class="sxs-lookup"><span data-stu-id="de9a9-126">At runtime, the WCF infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]      
  
     <span data-ttu-id="de9a9-127">В этом примере конечные точки явно задаются в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="de9a9-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="de9a9-128">Если в службу не добавлена ни одна конечная точка, то среда выполнения добавляет конечные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="de9a9-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="de9a9-129">Дополнительные сведения о конечных точках по умолчанию, привязок и поведений см. в разделе [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="de9a9-129">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="de9a9-130">Чтобы проверить правильность размещения службы, откройте экземпляр окна Internet Explorer и перейдите по URL-адресу службы: `http://localhost/IISHostedCalc/Service.svc`.</span><span class="sxs-lookup"><span data-stu-id="de9a9-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="de9a9-131">Пример</span><span class="sxs-lookup"><span data-stu-id="de9a9-131">Example</span></span>  
 <span data-ttu-id="de9a9-132">Далее представлен полный код службы калькулятора, размещаемой в IIS.</span><span class="sxs-lookup"><span data-stu-id="de9a9-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)] 
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)] 
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="de9a9-133">См. также</span><span class="sxs-lookup"><span data-stu-id="de9a9-133">See also</span></span>

- [<span data-ttu-id="de9a9-134">Размещение в службах IIS</span><span class="sxs-lookup"><span data-stu-id="de9a9-134">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [<span data-ttu-id="de9a9-135">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="de9a9-135">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="de9a9-136">Службы WCF и ASP.NET</span><span class="sxs-lookup"><span data-stu-id="de9a9-136">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [<span data-ttu-id="de9a9-137">Безопасность</span><span class="sxs-lookup"><span data-stu-id="de9a9-137">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
- [<span data-ttu-id="de9a9-138">Функции размещения Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="de9a9-138">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
