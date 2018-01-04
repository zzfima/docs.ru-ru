---
title: "Использование средств разработки WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d253f38fab21496dd305cc67e7b6e84846579f3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="414ff-102">Использование средств разработки WCF</span><span class="sxs-lookup"><span data-stu-id="414ff-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="414ff-103">В этом разделе описываются [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] средства разработки, которые могут помочь в разработке вашей [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]службы.</span><span class="sxs-lookup"><span data-stu-id="414ff-103">This section describes the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[indigo1](../../../includes/indigo1-md.md)] development tools that can assist you in developing your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]service.</span></span>  
  
 <span data-ttu-id="414ff-104">Можно использовать [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] шаблоны как основу для быстрого создания собственной службы, затем с помощью [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host и [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] тестовый клиент для отладки и тестирования службы.</span><span class="sxs-lookup"><span data-stu-id="414ff-104">You can use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] templates as a foundation to quickly build your own service, then use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host and [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client to debug and test your service.</span></span> <span data-ttu-id="414ff-105">Оба этих инструмента обеспечивают быстрый и удобный цикл отладки и тестирования и исключают необходимость фиксации модели размещения на ранней стадии.</span><span class="sxs-lookup"><span data-stu-id="414ff-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="414ff-106">Инструменты разработчика WCF</span><span class="sxs-lookup"><span data-stu-id="414ff-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="414ff-107">Шаблоны WCF в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="414ff-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="414ff-108">Можно использовать предопределенный [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] шаблонов проектов и элементов в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] для быстрого создания [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] службы и окружающих приложений.</span><span class="sxs-lookup"><span data-stu-id="414ff-108">You can use the predefined [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] project and item templates in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to quickly build [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="414ff-109">Узел службы WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="414ff-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="414ff-110">Средство Service Auto Host [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfSvcHost.exe) позволяет запускать отладчик [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] (F5) для автоматического размещения и проверки реализованной службы.</span><span class="sxs-lookup"><span data-stu-id="414ff-110">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (WcfSvcHost.exe) allows you to launch the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="414ff-111">Затем службу можно проверить с помощью тестового клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfTestClient.exe) или своего собственного клиента для поиска и устранения потенциальных ошибок.</span><span class="sxs-lookup"><span data-stu-id="414ff-111">You can then test the service using the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="414ff-112">Тестовый клиент WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="414ff-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="414ff-113">Тестовый клиент [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (WcfTestClient.exe) представляет собой средство графического интерфейса пользователя, позволяющее вводить тестовые параметры произвольных типов, отправлять их в службу и просматривать ответную реакцию службы.</span><span class="sxs-lookup"><span data-stu-id="414ff-113">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="414ff-114">При совместном использовании со средством Service Auto Host [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] это обеспечивает удобный способ тестирования служб.</span><span class="sxs-lookup"><span data-stu-id="414ff-114">It provides a seamless service testing experience when combined with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host.</span></span>  
  
 [<span data-ttu-id="414ff-115">Формирование классов типов данных из XML</span><span class="sxs-lookup"><span data-stu-id="414ff-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="414ff-116">Данные XML, сохраненные в буфере обмена, можно вставить в кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="414ff-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="414ff-117">Классы, определенные в данных, будут преобразованы в типы кода.</span><span class="sxs-lookup"><span data-stu-id="414ff-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="414ff-118">Использование инструментов без прав администратора</span><span class="sxs-lookup"><span data-stu-id="414ff-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="414ff-119">Чтобы позволить пользователю, у которого нет прав администратора, разрабатывать службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], для пространства имен "http://+:8731/Design_Time_Addresses" при установке [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] создается список управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="414ff-119">To enable users without administrator privilege to develop [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="414ff-120">Список управления доступом определяется пользовательским интерфейсом, который включает всех пользователей, выполнивших вход в систему.</span><span class="sxs-lookup"><span data-stu-id="414ff-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="414ff-121">Администраторы могут добавлять или удалять пользователей из этого списка ACL или открыть дополнительные порты. Этот список ACL позволяет шаблонам WCF или WF отправлять и получать данные в их конфигурации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="414ff-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="414ff-122">Он также позволяет пользователям использовать средство Service Auto Host [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (wcfSvcHost.exe) без предоставления им прав администратора.</span><span class="sxs-lookup"><span data-stu-id="414ff-122">It also enables users to use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="414ff-123">Можно изменить доступ используя средство Netsh.exe в [!INCLUDE[wv](../../../includes/wv-md.md)] под учетной записью администратора.</span><span class="sxs-lookup"><span data-stu-id="414ff-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="414ff-124">Ниже приведен пример использования средства Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="414ff-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="414ff-125">Netsh.exe см. в разделе [способы использования средства Netsh.exe и переключателей командной строки](http://go.microsoft.com/fwlink/?LinkId=97877).</span><span class="sxs-lookup"><span data-stu-id="414ff-125"> Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](http://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="414ff-126">См. также</span><span class="sxs-lookup"><span data-stu-id="414ff-126">See Also</span></span>  
 [<span data-ttu-id="414ff-127">Шаблоны WCF в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="414ff-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [<span data-ttu-id="414ff-128">Узел службы WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="414ff-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [<span data-ttu-id="414ff-129">Тестовый клиент WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="414ff-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
