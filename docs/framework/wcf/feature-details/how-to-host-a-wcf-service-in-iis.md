---
title: "Практическое руководство. Размещение службы WCF в IIS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 934b5d16cdea7026e0e7874cf04ab53c8fbdf58e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="89bfa-102">Практическое руководство. Размещение службы WCF в IIS</span><span class="sxs-lookup"><span data-stu-id="89bfa-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="89bfa-103">В этом разделе описаны основные шаги по созданию службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], размещенной в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="89bfa-103">This topic outlines the basic steps required to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="89bfa-104">Предполагается, что читатель знаком со службами IIS и может использовать средство управления IIS для создания приложений служб IIS и управления такими приложениями.</span><span class="sxs-lookup"><span data-stu-id="89bfa-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="89bfa-105">В разделе IIS [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449).</span><span class="sxs-lookup"><span data-stu-id="89bfa-105"> IIS see [Internet Information Services](http://go.microsoft.com/fwlink/?LinkId=132449).</span></span> <span data-ttu-id="89bfa-106">Служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], исполняемая в среде IIS, полноценно использует все функции IIS, такие как перезапуск процессов, завершение при ожидании, мониторинг работоспособности процессов и активация на основе сообщений.</span><span class="sxs-lookup"><span data-stu-id="89bfa-106">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="89bfa-107">Для реализации этого варианта размещения требуется правильно настроить службу IIS, но не требуется включать в приложение код размещения.</span><span class="sxs-lookup"><span data-stu-id="89bfa-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="89bfa-108">Размещение в службах IIS возможно только при использовании транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="89bfa-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="89bfa-109">как [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] взаимодействия см. в разделе [службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="89bfa-109"> how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interact, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="89bfa-110">Настройка параметров безопасности, в разделе [безопасности](../../../../docs/framework/wcf/feature-details/security.md).</span><span class="sxs-lookup"><span data-stu-id="89bfa-110"> configuring security, see [Security](../../../../docs/framework/wcf/feature-details/security.md).</span></span>  
  
 <span data-ttu-id="89bfa-111">Исходная копия в этом примере в разделе [IIS размещения с использованием встроенного кода](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span><span class="sxs-lookup"><span data-stu-id="89bfa-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="89bfa-112">Создание службы, размещенной в IIS</span><span class="sxs-lookup"><span data-stu-id="89bfa-112">To create a service hosted by IIS</span></span>  
  
1.  <span data-ttu-id="89bfa-113">Убедитесь, что службы IIS установлены и выполняются на компьютере.</span><span class="sxs-lookup"><span data-stu-id="89bfa-113">Confirm that IIS is installed and running on your computer.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="89bfa-114">Установка и настройка служб IIS в разделе [Установка и настройка служб IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)</span><span class="sxs-lookup"><span data-stu-id="89bfa-114"> installing and configuring IIS see [Installing and Configuring IIS 7.0](http://go.microsoft.com/fwlink/?LinkID=132128)</span></span>  
  
2.  <span data-ttu-id="89bfa-115">Создайте новую папку с именем IISHostedCalcService для файлов приложения, убедитесь, что [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] имеет доступ к содержимому этой папки, и воспользуйтесь средством управления IIS для создания нового приложения служб IIS, которое физически расположено в каталоге этого приложения.</span><span class="sxs-lookup"><span data-stu-id="89bfa-115">Create a new folder for your application files called "IISHostedCalcService", ensure that [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="89bfa-116">Создайте для каталога приложения псевдоним «IISHostedCalc».</span><span class="sxs-lookup"><span data-stu-id="89bfa-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3.  <span data-ttu-id="89bfa-117">Создайте в каталоге приложения новый файл с именем «service.svc».</span><span class="sxs-lookup"><span data-stu-id="89bfa-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="89bfa-118">Изменить этот файл, добавив следующий код @ServiceHost элемента.</span><span class="sxs-lookup"><span data-stu-id="89bfa-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4.  <span data-ttu-id="89bfa-119">В каталоге приложения создайте подкаталог App_Code.</span><span class="sxs-lookup"><span data-stu-id="89bfa-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5.  <span data-ttu-id="89bfa-120">Создайте файл кода с именем Service.cs во вложенном каталоге App_Code.</span><span class="sxs-lookup"><span data-stu-id="89bfa-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6.  <span data-ttu-id="89bfa-121">Добавьте следующие операторы using в начало файла Service.cs.</span><span class="sxs-lookup"><span data-stu-id="89bfa-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7.  <span data-ttu-id="89bfa-122">Добавьте следующее объявление пространства имен после операторов using.</span><span class="sxs-lookup"><span data-stu-id="89bfa-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8.  <span data-ttu-id="89bfa-123">Определите контракт службы в пределах объявления пространства имен, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="89bfa-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="89bfa-124">Реализуйте контракт службы после определения контракта службы, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="89bfa-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="89bfa-125">Создайте в каталоге приложения файл с именем Web.config и добавьте в него следующий код конфигурации.</span><span class="sxs-lookup"><span data-stu-id="89bfa-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="89bfa-126">Во время выполнения инфраструктура [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует эти данные для создания конечной точки, с которой могут взаимодействовать клиентские приложения.</span><span class="sxs-lookup"><span data-stu-id="89bfa-126">At runtime, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]      
  
     <span data-ttu-id="89bfa-127">В этом примере конечные точки явно задаются в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="89bfa-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="89bfa-128">Если в службу не добавлена ни одна конечная точка, то среда выполнения добавляет конечные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="89bfa-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="89bfa-129">по умолчанию конечные точки, привязки и поведения см. в разделе [упрощенной конфигурации](../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="89bfa-129"> default endpoints, bindings, and behaviors see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="89bfa-130">Чтобы проверить правильность размещения службы, откройте экземпляр окна Internet Explorer и перейдите по URL-адресу службы: `http://localhost/IISHostedCalc/Service.svc`.</span><span class="sxs-lookup"><span data-stu-id="89bfa-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="89bfa-131">Пример</span><span class="sxs-lookup"><span data-stu-id="89bfa-131">Example</span></span>  
 <span data-ttu-id="89bfa-132">Далее представлен полный код службы калькулятора, размещаемой в IIS.</span><span class="sxs-lookup"><span data-stu-id="89bfa-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)] 
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)] 
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="89bfa-133">См. также</span><span class="sxs-lookup"><span data-stu-id="89bfa-133">See Also</span></span>  
 [<span data-ttu-id="89bfa-134">Размещение в службах IIS</span><span class="sxs-lookup"><span data-stu-id="89bfa-134">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)  
 [<span data-ttu-id="89bfa-135">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="89bfa-135">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="89bfa-136">Службы WCF и ASP.NET</span><span class="sxs-lookup"><span data-stu-id="89bfa-136">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [<span data-ttu-id="89bfa-137">Безопасность</span><span class="sxs-lookup"><span data-stu-id="89bfa-137">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
 [<span data-ttu-id="89bfa-138">Функции размещения Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="89bfa-138">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
