---
title: "Разрешение безопасности перенаправления привязки сборок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d2593df04b93db17f9ca61a98b21aaec1d534d46
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="cf38a-102">Разрешение безопасности перенаправления привязки сборок</span><span class="sxs-lookup"><span data-stu-id="cf38a-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="cf38a-103">Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности.</span><span class="sxs-lookup"><span data-stu-id="cf38a-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="cf38a-104">Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок.</span><span class="sxs-lookup"><span data-stu-id="cf38a-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="cf38a-105">Разрешение можно получить, установив <xref:System.Security.Permissions.SecurityPermissionFlag> флаг <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="cf38a-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="cf38a-106">Управляемые сборки не имеют разрешений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cf38a-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="cf38a-107">Разрешение безопасности к приложениям, работающим в зону надежных (локальный компьютер) и интрасеть.</span><span class="sxs-lookup"><span data-stu-id="cf38a-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="cf38a-108">Приложения, выполняющиеся в зоне Интернета, строго запрещено осуществлять перенаправление привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="cf38a-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="cf38a-109">Разрешение не требуется, если перенаправление сборки выполняется в файл политики издателя, которые управляются издателем компонента или в файле конфигурации компьютера, который управляется администратором.</span><span class="sxs-lookup"><span data-stu-id="cf38a-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="cf38a-110">Тем не менее, требуется разрешение для приложения, чтобы явно игнорировать политику издателя с помощью [ \<исполняемым = «no» / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="cf38a-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="cf38a-111">В следующей таблице показаны по умолчанию параметры безопасности для **BindingRedirects** флаг.</span><span class="sxs-lookup"><span data-stu-id="cf38a-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="cf38a-112">Зоны</span><span class="sxs-lookup"><span data-stu-id="cf38a-112">Zone</span></span>|<span data-ttu-id="cf38a-113">Установка флага BindingRedirects</span><span class="sxs-lookup"><span data-stu-id="cf38a-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="cf38a-114">Зоны надежных узлов (локальный компьютер)</span><span class="sxs-lookup"><span data-stu-id="cf38a-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="cf38a-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="cf38a-115">**ON**</span></span>|  
|<span data-ttu-id="cf38a-116">Зоны интрасети</span><span class="sxs-lookup"><span data-stu-id="cf38a-116">Intranet Zone</span></span>|<span data-ttu-id="cf38a-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="cf38a-117">**ON**</span></span>|  
|<span data-ttu-id="cf38a-118">Зона Интернета</span><span class="sxs-lookup"><span data-stu-id="cf38a-118">Internet Zone</span></span>|<span data-ttu-id="cf38a-119">**OFF**</span><span class="sxs-lookup"><span data-stu-id="cf38a-119">**OFF**</span></span>|  
|<span data-ttu-id="cf38a-120">Зоны без доверия</span><span class="sxs-lookup"><span data-stu-id="cf38a-120">Untrusted zones</span></span>|<span data-ttu-id="cf38a-121">**OFF**</span><span class="sxs-lookup"><span data-stu-id="cf38a-121">**OFF**</span></span>|  
  
 <span data-ttu-id="cf38a-122">Администратор может изменить эти параметры безопасности, чтобы разрешить или запретить определенные сценарии на данном компьютере.</span><span class="sxs-lookup"><span data-stu-id="cf38a-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="cf38a-123">Нет средств для изменения **BindingRedirects** установку по умолчанию; флагов администратору необходимо вручную изменить файл Security.config на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="cf38a-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf38a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="cf38a-124">See Also</span></span>  
 [<span data-ttu-id="cf38a-125">Файлы политики издателя и выполнения Side-by-Side</span><span class="sxs-lookup"><span data-stu-id="cf38a-125">Publisher Policy Files and Side-by-Side Execution</span></span>](http://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [<span data-ttu-id="cf38a-126">Практическое руководство. Включение и отключение автоматического перенаправления привязки</span><span class="sxs-lookup"><span data-stu-id="cf38a-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [<span data-ttu-id="cf38a-127">Параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="cf38a-127">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)
