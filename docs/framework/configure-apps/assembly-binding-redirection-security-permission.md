---
title: Разрешение безопасности перенаправления привязки сборок
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
author: mcleblanc
ms.author: markl
ms.openlocfilehash: d4483d11903d61135585a2b6c2c33eff48300151
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616018"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="b6970-102">Разрешение безопасности перенаправления привязки сборок</span><span class="sxs-lookup"><span data-stu-id="b6970-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="b6970-103">Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности.</span><span class="sxs-lookup"><span data-stu-id="b6970-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="b6970-104">Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок.</span><span class="sxs-lookup"><span data-stu-id="b6970-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="b6970-105">Разрешение, задав <xref:System.Security.Permissions.SecurityPermissionFlag> флаг <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="b6970-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="b6970-106">Управляемые сборки не имеют разрешений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b6970-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="b6970-107">Разрешение безопасности к приложениям, работающим в зону надежных (локальный компьютер) и зоны интрасети.</span><span class="sxs-lookup"><span data-stu-id="b6970-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="b6970-108">Приложения, работающие в зоне Интернета, строго запрещено выполнять перенаправление привязки сборок.</span><span class="sxs-lookup"><span data-stu-id="b6970-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="b6970-109">Разрешение не требуется, если перенаправление сборки выполняется в файл политики издателя, которые управляются издателем компонента, или в файле конфигурации компьютера, которое управляется администратором.</span><span class="sxs-lookup"><span data-stu-id="b6970-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="b6970-110">Тем не менее, разрешение является обязательным для приложения, чтобы явно игнорировать политику издателя с помощью [ \<исполняемым = «no» / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) элемент в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b6970-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="b6970-111">В следующей таблице показаны по умолчанию параметры безопасности для **BindingRedirects** флаг.</span><span class="sxs-lookup"><span data-stu-id="b6970-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="b6970-112">Зона</span><span class="sxs-lookup"><span data-stu-id="b6970-112">Zone</span></span>|<span data-ttu-id="b6970-113">Установка флага BindingRedirects</span><span class="sxs-lookup"><span data-stu-id="b6970-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="b6970-114">Зоны надежных узлов (локальный компьютер)</span><span class="sxs-lookup"><span data-stu-id="b6970-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="b6970-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="b6970-115">**ON**</span></span>|  
|<span data-ttu-id="b6970-116">Зона интрасети</span><span class="sxs-lookup"><span data-stu-id="b6970-116">Intranet Zone</span></span>|<span data-ttu-id="b6970-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="b6970-117">**ON**</span></span>|  
|<span data-ttu-id="b6970-118">Зона Интернета</span><span class="sxs-lookup"><span data-stu-id="b6970-118">Internet Zone</span></span>|<span data-ttu-id="b6970-119">**OFF**</span><span class="sxs-lookup"><span data-stu-id="b6970-119">**OFF**</span></span>|  
|<span data-ttu-id="b6970-120">Зоны без доверия</span><span class="sxs-lookup"><span data-stu-id="b6970-120">Untrusted zones</span></span>|<span data-ttu-id="b6970-121">**OFF**</span><span class="sxs-lookup"><span data-stu-id="b6970-121">**OFF**</span></span>|  
  
 <span data-ttu-id="b6970-122">Администратор может изменить эти параметры безопасности, чтобы разрешить или запретить конкретных сценариев на данном компьютере.</span><span class="sxs-lookup"><span data-stu-id="b6970-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="b6970-123">Нет средств по изменению **BindingRedirects** флаг, используемый по умолчанию; Azure с помощью администратора необходимо вручную изменить файл Security.config на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="b6970-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6970-124">См. также</span><span class="sxs-lookup"><span data-stu-id="b6970-124">See also</span></span>
- [<span data-ttu-id="b6970-125">Файлы политики издателя и выполнение Side-by-Side</span><span class="sxs-lookup"><span data-stu-id="b6970-125">Publisher Policy Files and Side-by-Side Execution</span></span>](https://msdn.microsoft.com/library/97a042be-4d72-40c3-91c0-76fd36bdf133)
- [<span data-ttu-id="b6970-126">Практическое руководство. Включение и отключение автоматического перенаправления привязки</span><span class="sxs-lookup"><span data-stu-id="b6970-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="b6970-127">Параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="b6970-127">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)
