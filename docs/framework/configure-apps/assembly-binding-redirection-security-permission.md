---
title: Разрешение безопасности перенаправления привязки сборок
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: b59689e78f901637674c0a1df28ed74411e8e7c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921378"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="29915-102">Разрешение безопасности перенаправления привязки сборок</span><span class="sxs-lookup"><span data-stu-id="29915-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="29915-103">Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности.</span><span class="sxs-lookup"><span data-stu-id="29915-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="29915-104">Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок.</span><span class="sxs-lookup"><span data-stu-id="29915-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="29915-105">Разрешение предоставляется путем установки <xref:System.Security.Permissions.SecurityPermissionFlag> флага <xref:System.Security.Permissions.SecurityPermission>для.</span><span class="sxs-lookup"><span data-stu-id="29915-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="29915-106">По умолчанию управляемые сборки не имеют разрешений.</span><span class="sxs-lookup"><span data-stu-id="29915-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="29915-107">Разрешение безопасности предоставляется приложениям, выполняемым в зоне доверенной зоны (локального компьютера) и зоны интрасети.</span><span class="sxs-lookup"><span data-stu-id="29915-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="29915-108">Приложениям, выполняемым в зоне Интернета, строго запрещено выполнять перенаправление привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="29915-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="29915-109">Разрешение не требуется, если перенаправление сборок выполняется в файле политики издателя, который управляется издателем компонента, или в файле конфигурации компьютера, управляемом администратором.</span><span class="sxs-lookup"><span data-stu-id="29915-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="29915-110">Однако разрешение требуется для приложения, чтобы явно игнорировать политику издателя с помощью [ \<элемента publisherpolicy Apply Apply = "No"/>](./file-schema/runtime/publisherpolicy-element.md) в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="29915-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="29915-111">В следующей таблице показаны параметры безопасности по умолчанию для флага **BindingRedirects** .</span><span class="sxs-lookup"><span data-stu-id="29915-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="29915-112">Зона</span><span class="sxs-lookup"><span data-stu-id="29915-112">Zone</span></span>|<span data-ttu-id="29915-113">Параметр флага BindingRedirects</span><span class="sxs-lookup"><span data-stu-id="29915-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="29915-114">Доверенная зона (локальный компьютер)</span><span class="sxs-lookup"><span data-stu-id="29915-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="29915-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="29915-115">**ON**</span></span>|  
|<span data-ttu-id="29915-116">Зона интрасети</span><span class="sxs-lookup"><span data-stu-id="29915-116">Intranet Zone</span></span>|<span data-ttu-id="29915-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="29915-117">**ON**</span></span>|  
|<span data-ttu-id="29915-118">Зона Интернета</span><span class="sxs-lookup"><span data-stu-id="29915-118">Internet Zone</span></span>|<span data-ttu-id="29915-119">**OFF**</span><span class="sxs-lookup"><span data-stu-id="29915-119">**OFF**</span></span>|  
|<span data-ttu-id="29915-120">Недоверенные зоны</span><span class="sxs-lookup"><span data-stu-id="29915-120">Untrusted zones</span></span>|<span data-ttu-id="29915-121">**OFF**</span><span class="sxs-lookup"><span data-stu-id="29915-121">**OFF**</span></span>|  
  
 <span data-ttu-id="29915-122">Администратор может изменить эти параметры безопасности для поддержки или ограничения конкретных сценариев на определенном компьютере.</span><span class="sxs-lookup"><span data-stu-id="29915-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="29915-123">Нет средств для изменения значения флага **BindingRedirects** по умолчанию; Администратор должен вручную изменить файл Security. config на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="29915-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29915-124">См. также</span><span class="sxs-lookup"><span data-stu-id="29915-124">See also</span></span>

- <span data-ttu-id="29915-125">[Файлы политики издателя и параллельное выполнение](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="29915-125">[Publisher Policy Files and Side-by-Side Execution](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span></span>
- [<span data-ttu-id="29915-126">Практическое руководство. Включение и отключение автоматического перенаправления привязки</span><span class="sxs-lookup"><span data-stu-id="29915-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="29915-127">Параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="29915-127">Side-by-Side Execution</span></span>](../deployment/side-by-side-execution.md)
