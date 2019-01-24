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
ms.openlocfilehash: 281582b04aabd8a18af8bf17091979385d009ee8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536546"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="61c36-102">Опасные разрешения и администрирование политик</span><span class="sxs-lookup"><span data-stu-id="61c36-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="61c36-103">Некоторые из защищенных операций, для которых .NET Framework предоставляет разрешения, потенциально могут позволить обойти систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="61c36-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="61c36-104">Эти небезопасные разрешения должны предоставляться только надежному коду и только в случае необходимости.</span><span class="sxs-lookup"><span data-stu-id="61c36-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="61c36-105">Обычно невозможно защититься от вредоносного кода, который получил эти разрешения.</span><span class="sxs-lookup"><span data-stu-id="61c36-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61c36-106">В версии [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]произошли серьезные изменения в терминологии и модели безопасности .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="61c36-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="61c36-107">Дополнительные сведения об этих изменениях см. в разделе [изменения системы безопасности](../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="61c36-107">For more information about these changes, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="61c36-108">Небезопасные разрешения приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="61c36-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="61c36-109">Разрешение</span><span class="sxs-lookup"><span data-stu-id="61c36-109">Permission</span></span>|<span data-ttu-id="61c36-110">Потенциальный риск</span><span class="sxs-lookup"><span data-stu-id="61c36-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="61c36-111">Позволяет управляемому коду вызывать неуправляемый код, который часто небезопасен.</span><span class="sxs-lookup"><span data-stu-id="61c36-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="61c36-112">Без проверки код может что-либо сделать.</span><span class="sxs-lookup"><span data-stu-id="61c36-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="61c36-113">Непроверенное свидетельство может обмануть систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="61c36-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="61c36-114">Возможность изменять политику безопасности может отключить систему безопасности.</span><span class="sxs-lookup"><span data-stu-id="61c36-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="61c36-115">Использование сериализации позволяет обойти механизмы специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="61c36-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="61c36-116">Подробные сведения см. в разделе [Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="61c36-116">For details, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="61c36-117">Возможность установки текущего участника может сбить с толку безопасность на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="61c36-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="61c36-118">Управление потоками представляет опасность, поскольку состояние безопасности связано с потоками.</span><span class="sxs-lookup"><span data-stu-id="61c36-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="61c36-119">Можно использовать закрытые члены для нарушения правил доступа.</span><span class="sxs-lookup"><span data-stu-id="61c36-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="61c36-120">См. также</span><span class="sxs-lookup"><span data-stu-id="61c36-120">See also</span></span>
- [<span data-ttu-id="61c36-121">Правила написания безопасного кода</span><span class="sxs-lookup"><span data-stu-id="61c36-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
