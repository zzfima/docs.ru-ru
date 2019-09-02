---
title: Опасные разрешения и администрирование политик
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ffe4f3e000c80610d5a105dddef90f9cfd51f0dc
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205585"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="82a51-102">Опасные разрешения и администрирование политик</span><span class="sxs-lookup"><span data-stu-id="82a51-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="82a51-103">Некоторые из защищенных операций, для которых .NET Framework предоставляет разрешения, потенциально могут позволить обойти систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="82a51-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="82a51-104">Эти небезопасные разрешения должны предоставляться только надежному коду и только в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="82a51-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="82a51-105">Обычно невозможно защититься от вредоносного кода, который получил эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="82a51-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82a51-106">В .NET Framework 4 были внесены важные изменения в модель и терминологию безопасности .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="82a51-106">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="82a51-107">Дополнительные сведения об этих изменениях см. в разделе [изменения в системе безопасности](../security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="82a51-107">For more information about these changes, see [Security Changes](../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="82a51-108">Небезопасные разрешения приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="82a51-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="82a51-109">Разрешение</span><span class="sxs-lookup"><span data-stu-id="82a51-109">Permission</span></span>|<span data-ttu-id="82a51-110">Потенциальный риск</span><span class="sxs-lookup"><span data-stu-id="82a51-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="82a51-111">Позволяет управляемому коду вызывать неуправляемый код, который часто небезопасен.</span><span class="sxs-lookup"><span data-stu-id="82a51-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="82a51-112">Без проверки код может что-либо сделать.</span><span class="sxs-lookup"><span data-stu-id="82a51-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="82a51-113">Непроверенное свидетельство может обмануть систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="82a51-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="82a51-114">Возможность изменять политику безопасности может отключить систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="82a51-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="82a51-115">Использование сериализации позволяет обойти механизмы специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="82a51-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="82a51-116">Подробные сведения см. в разделе [Безопасность и сериализация](security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="82a51-116">For details, see [Security and Serialization](security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="82a51-117">Возможность установки текущего участника может сбить с толку безопасность на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="82a51-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="82a51-118">Управление потоками представляет опасность, поскольку состояние безопасности связано с потоками.</span><span class="sxs-lookup"><span data-stu-id="82a51-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="82a51-119">Можно использовать закрытые члены для нарушения правил доступа.</span><span class="sxs-lookup"><span data-stu-id="82a51-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82a51-120">См. также</span><span class="sxs-lookup"><span data-stu-id="82a51-120">See also</span></span>

- [<span data-ttu-id="82a51-121">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="82a51-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
