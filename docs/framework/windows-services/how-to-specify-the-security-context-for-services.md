---
title: Практическое руководство. Назначение службам контекста безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
author: ghogen
ms.openlocfilehash: a5a437af90f29bc601215176ad5c4fec702ddbc0
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2018
ms.locfileid: "47073727"
---
# <a name="how-to-specify-the-security-context-for-services"></a><span data-ttu-id="b992a-102">Практическое руководство. Назначение службам контекста безопасности</span><span class="sxs-lookup"><span data-stu-id="b992a-102">How to: Specify the Security Context for Services</span></span>
<span data-ttu-id="b992a-103">По умолчанию службы работают в контексте безопасности, отличном от того, в котором работает вошедший в систему пользователь.</span><span class="sxs-lookup"><span data-stu-id="b992a-103">By default, services run in a different security context than that of the logged-in user.</span></span> <span data-ttu-id="b992a-104">Службы работают в контексте стандартной системной учетной записи с именем `LocalSystem`. Она дает им другие права на доступ к системным ресурсам (не такие, как у пользователя).</span><span class="sxs-lookup"><span data-stu-id="b992a-104">Services run in the context of the default system account, called `LocalSystem`, which gives them different access privileges to system resources than the user.</span></span> <span data-ttu-id="b992a-105">Эту ситуацию можно изменить, указав другую учетную запись пользователя, под которой будет работать служба.</span><span class="sxs-lookup"><span data-stu-id="b992a-105">You can change this behavior to specify a different user account under which your service should run.</span></span>  
  
 <span data-ttu-id="b992a-106">Чтобы задать контекст безопасности, для процесса, в котором выполняется служба, нужно изменить свойство <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>.</span><span class="sxs-lookup"><span data-stu-id="b992a-106">You set the security context by manipulating the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property for the process within which the service runs.</span></span> <span data-ttu-id="b992a-107">Это свойство позволяет задать для службы один из четырех типов учетных записей.</span><span class="sxs-lookup"><span data-stu-id="b992a-107">This property allows you to set the service to one of four account types:</span></span>  
  
-   <span data-ttu-id="b992a-108">`User`. Система запрашивает действительное имя пользователя и пароль, когда служба устанавливается и запускается в контексте учетной записи, указанной одним пользователем по сети.</span><span class="sxs-lookup"><span data-stu-id="b992a-108">`User`, which causes the system to prompt for a valid user name and password when the service is installed and runs in the context of an account specified by a single user on the network;</span></span>  
  
-   <span data-ttu-id="b992a-109">`LocalService`. Выполняется в контексте учетной записи, которая аналогична учетной записи непривилегированного пользователя локального компьютера. Удаленным серверам при этом передаются учетные данные анонимного пользователя.</span><span class="sxs-lookup"><span data-stu-id="b992a-109">`LocalService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents anonymous credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="b992a-110">`LocalSystem`. Выполняется в контексте учетной записи, которая предоставляет широкие локальные привилегии. Удаленным серверам при этом передаются учетные данные компьютера.</span><span class="sxs-lookup"><span data-stu-id="b992a-110">`LocalSystem`, which runs in the context of an account that provides extensive local privileges, and presents the computer's credentials to any remote server;</span></span>  
  
-   <span data-ttu-id="b992a-111">`NetworkService`. Выполняется в контексте учетной записи, которая аналогична учетной записи непривилегированного пользователя локального компьютера. Удаленным серверам при этом передаются учетные данные компьютера.</span><span class="sxs-lookup"><span data-stu-id="b992a-111">`NetworkService`, which runs in the context of an account that acts as a non-privileged user on the local computer, and presents the computer's credentials to any remote server.</span></span>  
  
 <span data-ttu-id="b992a-112">Дополнительные сведения см. в описании перечисления <xref:System.ServiceProcess.ServiceAccount>.</span><span class="sxs-lookup"><span data-stu-id="b992a-112">For more information, see the <xref:System.ServiceProcess.ServiceAccount> enumeration.</span></span>  
  
### <a name="to-specify-the-security-context-for-a-service"></a><span data-ttu-id="b992a-113">Назначение службам контекста безопасности</span><span class="sxs-lookup"><span data-stu-id="b992a-113">To specify the security context for a service</span></span>  
  
1.  <span data-ttu-id="b992a-114">Создав службу, добавьте для нее необходимые установщики.</span><span class="sxs-lookup"><span data-stu-id="b992a-114">After creating your service, add the necessary installers for it.</span></span> <span data-ttu-id="b992a-115">Дополнительные сведения см. в [руководстве по добавлению установщиков в приложение-службу](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="b992a-115">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
2.  <span data-ttu-id="b992a-116">В конструкторе откройте класс `ProjectInstaller` и щелкните установщик процессов службы, с которой вы работаете.</span><span class="sxs-lookup"><span data-stu-id="b992a-116">In the designer, access the `ProjectInstaller` class and click the service process installer for the service you are working with.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b992a-117">В классе `ProjectInstaller` для каждого приложения-службы есть по крайней мере два компонента установки: установщик процессов для всех служб в проекте и установщик для каждой службы приложения.</span><span class="sxs-lookup"><span data-stu-id="b992a-117">For every service application, there are at least two installation components in the `ProjectInstaller` class — one that installs the processes for all services in the project, and one installer for each service the application contains.</span></span> <span data-ttu-id="b992a-118">Сейчас вам нужно выбрать <xref:System.ServiceProcess.ServiceProcessInstaller>.</span><span class="sxs-lookup"><span data-stu-id="b992a-118">In this instance, you want to select <xref:System.ServiceProcess.ServiceProcessInstaller>.</span></span>  
  
3.  <span data-ttu-id="b992a-119">В окне **Свойства** задайте для свойства <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="b992a-119">In the **Properties** window, set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> to the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b992a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b992a-120">See Also</span></span>  
 [<span data-ttu-id="b992a-121">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="b992a-121">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="b992a-122">Практическое руководство. Добавление установщиков в приложение служб</span><span class="sxs-lookup"><span data-stu-id="b992a-122">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="b992a-123">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="b992a-123">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)
