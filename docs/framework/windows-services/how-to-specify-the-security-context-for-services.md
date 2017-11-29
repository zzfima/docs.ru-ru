---
title: "Практическое руководство. Назначение службам контекста безопасности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 50a9c6ff7f02cda4475aa5390181fa5d410af161
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="e3949-102">Практическое руководство. Назначение службам контекста безопасности</span><span class="sxs-lookup"><span data-stu-id="e3949-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="e3949-103">По умолчанию службы запускаются в контексте безопасности, отличном от пользователя, вошедшего в систему.</span><span class="sxs-lookup"><span data-stu-id="e3949-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="e3949-104">Службы выполняются в контексте системной учетной записи по умолчанию называется `LocalSystem`, что дает им разные права доступа к ресурсам системы от пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3949-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="e3949-105">Можно изменить таким образом, чтобы указать учетную запись пользователя, под которой будет запускаться служба.</span><span class="sxs-lookup"><span data-stu-id="e3949-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="e3949-106">Задать контекст безопасности, управляя <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> свойство для процесса, в котором выполняется служба.</span><span class="sxs-lookup"><span data-stu-id="e3949-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="e3949-107">Это свойство позволяет задать один из четырех типов учетных записей службы:</span><span class="sxs-lookup"><span data-stu-id="e3949-107">This property allows you to set the service to one of four account types:</span></span>  
  
-   <span data-ttu-id="e3949-108">`User`, чего система запрашивает допустимое имя пользователя и пароль, когда служба устанавливается и запускается в контексте учетной записи, указанной пользователем по сети;</span><span class="sxs-lookup"><span data-stu-id="e3949-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
-   <span data-ttu-id="e3949-109">`LocalService`, который выполняется в контексте учетной записи, которая действует как непривилегированного пользователя локального компьютера и предоставляет учетные данные для анонимного доступа к удаленным серверам;</span><span class="sxs-lookup"><span data-stu-id="e3949-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="e3949-110">`LocalSystem`, который выполняется в контексте учетной записи, которая предоставляет широкие локальные привилегии и передает учетные данные компьютера удаленным серверам;</span><span class="sxs-lookup"><span data-stu-id="e3949-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="e3949-111">`NetworkService`, который выполняется в контексте учетной записи, которая действует как непривилегированного пользователя локального компьютера и предоставляет учетные данные компьютера удаленным серверам.</span><span class="sxs-lookup"><span data-stu-id="e3949-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="e3949-112">Дополнительные сведения см. в описании перечисления <xref:System.ServiceProcess.ServiceAccount>.</span><span class="sxs-lookup"><span data-stu-id="e3949-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="e3949-113">Чтобы указать контекст безопасности для службы</span><span class="sxs-lookup"><span data-stu-id="e3949-113">To specify the security context for a service</span></span>  
  
1.  <span data-ttu-id="e3949-114">После создания службы, добавьте установщики, необходимые для него.</span><span class="sxs-lookup"><span data-stu-id="e3949-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="e3949-115">Дополнительные сведения см. в разделе [как: добавление установщиков к приложению службы](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="e3949-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="e3949-116">В конструкторе, доступ к `ProjectInstaller` класса и нажмите кнопку установщик процессов службы для службы, вы работаете.</span><span class="sxs-lookup"><span data-stu-id="e3949-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3949-117">Для каждого приложения служб есть по крайней мере два компонента установки в `ProjectInstaller` класса — компонент, устанавливающий процессы для всех служб в проекте и установщик для каждой службы, приложение содержит.</span><span class="sxs-lookup"><span data-stu-id="e3949-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="e3949-118">В этом случае нужно выбрать <xref:System.ServiceProcess.ServiceProcessInstaller>.</span><span class="sxs-lookup"><span data-stu-id="e3949-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3.  <span data-ttu-id="e3949-119">В **свойства** задайте <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="e3949-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3949-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e3949-120">See Also</span></span>  
 [<span data-ttu-id="e3949-121">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="e3949-121">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="e3949-122">Как: добавление установщиков в приложение службы</span><span class="sxs-lookup"><span data-stu-id="e3949-122">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="e3949-123">Как: создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="e3949-123">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
