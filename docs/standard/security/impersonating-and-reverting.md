---
title: Олицетворение и возвращение
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsIdentity objects, impersonating
- security [.NET Framework], impersonating Windows accounts
- impersonating Windows accounts
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
ms.openlocfilehash: 14b01ec3ac800abd795e87b641a442df100f102b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706023"
---
# <a name="impersonating-and-reverting"></a><span data-ttu-id="ddedc-102">Олицетворение и возвращение</span><span class="sxs-lookup"><span data-stu-id="ddedc-102">Impersonating and Reverting</span></span>
<span data-ttu-id="ddedc-103">Иногда может потребоваться получить токен учетной записи Windows для олицетворения учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="ddedc-103">Sometimes you might need to obtain a Windows account token to impersonate a Windows account.</span></span> <span data-ttu-id="ddedc-104">Например, приложению ASP.NET может требоваться действовать от лица разных пользователей в разное время.</span><span class="sxs-lookup"><span data-stu-id="ddedc-104">For example, your ASP.NET-based application might have to act on behalf of several users at different times.</span></span> <span data-ttu-id="ddedc-105">Ваше приложение может принять токен, представляющий администратора, из служб IIS, выполнить олицетворение этого пользователя, выполнить операцию и вернуться к предыдущему удостоверению.</span><span class="sxs-lookup"><span data-stu-id="ddedc-105">Your application might accept a token that represents an administrator from Internet Information Services (IIS), impersonate that user, perform an operation, and revert to the previous identity.</span></span> <span data-ttu-id="ddedc-106">Далее он может принять токен из служб IIS, который представляет пользователя с меньшим набором прав, выполнить некую операцию и снова вернуться.</span><span class="sxs-lookup"><span data-stu-id="ddedc-106">Next, it might accept a token from IIS that represents a user with fewer rights, perform some operation, and revert again.</span></span>  
  
 <span data-ttu-id="ddedc-107">В ситуациях, когда приложение должно олицетворять учетную запись Windows, не подключенную к текущему потоку службами IIS, необходимо получить токен для этой учетной записи и с его помощью активировать эту учетную запись.</span><span class="sxs-lookup"><span data-stu-id="ddedc-107">In situations where your application must impersonate a Windows account that has not been attached to the current thread by IIS, you must retrieve that account's token and use it to activate the account.</span></span> <span data-ttu-id="ddedc-108">Это можно сделать, выполнив следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="ddedc-108">You can do this by performing the following tasks:</span></span>  
  
1. <span data-ttu-id="ddedc-109">Получите токен учетной записи для конкретного пользователя путем вызова неуправляемого метода **LogonUser**.</span><span class="sxs-lookup"><span data-stu-id="ddedc-109">Retrieve an account token for a particular user by making a call to the unmanaged **LogonUser** method.</span></span> <span data-ttu-id="ddedc-110">Этот метод находится не в библиотеке базовых классов .NET Framework, а в неуправляемой библиотеке **advapi32.dl**.</span><span class="sxs-lookup"><span data-stu-id="ddedc-110">This method is not in the .NET Framework base class library, but is located in the unmanaged **advapi32.dll**.</span></span> <span data-ttu-id="ddedc-111">Доступ к методам в неуправляемом коде является сложной операцией и выходит за рамки данного обсуждения.</span><span class="sxs-lookup"><span data-stu-id="ddedc-111">Accessing methods in unmanaged code is an advanced operation and is beyond the scope of this discussion.</span></span> <span data-ttu-id="ddedc-112">Дополнительные сведения см. в разделе [Взаимодействие с неуправляемым кодом](../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="ddedc-112">For more information, see [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="ddedc-113">Дополнительные сведения о методе **LogonUser** и библиотеке **advapi32.dll** см. в документации Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="ddedc-113">For more information about the **LogonUser** method and **advapi32.dll**, see the Platform SDK documentation.</span></span>  
  
2. <span data-ttu-id="ddedc-114">Создайте новый экземпляр класса **WindowsIdentity**, передав токен.</span><span class="sxs-lookup"><span data-stu-id="ddedc-114">Create a new instance of the **WindowsIdentity** class, passing the token.</span></span> <span data-ttu-id="ddedc-115">Следующий код демонстрирует этот вызов, где `hToken` представляет токен Windows.</span><span class="sxs-lookup"><span data-stu-id="ddedc-115">The following code demonstrates this call, where `hToken` represents a Windows token.</span></span>  
  
    ```csharp  
    WindowsIdentity impersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim impersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3. <span data-ttu-id="ddedc-116">Начните олицетворение, создав новый экземпляр класса <xref:System.Security.Principal.WindowsImpersonationContext> и инициализировав его с помощью метода <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> инициализации класса, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ddedc-116">Begin impersonation by creating a new instance of the <xref:System.Security.Principal.WindowsImpersonationContext> class and initializing it with the <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> method of the initialized class, as shown in the following code.</span></span>  
  
    ```csharp  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate()  
    ```  
  
4. <span data-ttu-id="ddedc-117">Если это олицетворение больше не требуется, вызовите метод <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> для отмены олицетворения, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="ddedc-117">When you no longer need to impersonate, call the <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> method to revert the impersonation, as shown in the following code.</span></span>  
  
    ```csharp  
    myImpersonation.Undo();  
    ```  
  
    ```vb  
    myImpersonation.Undo()  
    ```  
  
 <span data-ttu-id="ddedc-118">Если доверенный код уже подключил объект <xref:System.Security.Principal.WindowsPrincipal> к потоку, можно вызвать метод экземпляра **impersonate**, который не принимает маркер учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ddedc-118">If trusted code has already attached a <xref:System.Security.Principal.WindowsPrincipal> object to the thread, you can call the instance method **Impersonate**, which does not take an account token.</span></span> <span data-ttu-id="ddedc-119">Обратите внимание, что это целесообразно только в том случае, если объект **WindowsPrincipal** в потоке представляет пользователя, отличного от того, под которым выполняется процесс.</span><span class="sxs-lookup"><span data-stu-id="ddedc-119">Note that this is only useful when the **WindowsPrincipal** object on the thread represents a user other than the one under which the process is currently executing.</span></span> <span data-ttu-id="ddedc-120">Например, такая ситуация может возникнуть при использовании ASP.NET с включенной проверкой подлинности Windows и отключенным олицетворением.</span><span class="sxs-lookup"><span data-stu-id="ddedc-120">For example, you might encounter this situation using ASP.NET with Windows authentication turned on and impersonation turned off.</span></span> <span data-ttu-id="ddedc-121">В этом случае процесс выполняется под учетной записью, настроенной в IIS, тогда как текущий участник представляет пользователя Windows, который обращается к странице.</span><span class="sxs-lookup"><span data-stu-id="ddedc-121">In this case, the process is running under an account configured in Internet Information Services (IIS) while the current principal represents the Windows user that is accessing the page.</span></span>  
  
 <span data-ttu-id="ddedc-122">Обратите внимание, что ни **олицетворение** , ни **Отмена** изменений не изменяет объект **Principal** (<xref:System.Security.Principal.IPrincipal>), связанный с текущим контекстом вызова.</span><span class="sxs-lookup"><span data-stu-id="ddedc-122">Note that neither **Impersonate** nor **Undo** changes the **Principal** object (<xref:System.Security.Principal.IPrincipal>)  associated with the current call context.</span></span> <span data-ttu-id="ddedc-123">Говоря точнее, эти методы меняют токен, связанный с текущим процессом операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ddedc-123">Rather, impersonation and reverting change the token associated with the current operating system process..</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddedc-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="ddedc-124">See also</span></span>

- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.Security.Principal.WindowsImpersonationContext>
- [<span data-ttu-id="ddedc-125">Объекты Principal и Identity</span><span class="sxs-lookup"><span data-stu-id="ddedc-125">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
- [<span data-ttu-id="ddedc-126">Взаимодействие с неуправляемым кодом</span><span class="sxs-lookup"><span data-stu-id="ddedc-126">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)
