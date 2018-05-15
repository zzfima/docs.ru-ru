---
title: Замена объекта Principal
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94391471fecd92aeadec4da39cdd5b6f80bb6949
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="replacing-a-principal-object"></a><span data-ttu-id="ebefa-102">Замена объекта Principal</span><span class="sxs-lookup"><span data-stu-id="ebefa-102">Replacing a Principal Object</span></span>
<span data-ttu-id="ebefa-103">Приложения, предоставляющие службы проверки подлинности, должны иметь возможность заменять объект **Principal** (<xref:System.Security.Principal.IPrincipal>) для данного потока.</span><span class="sxs-lookup"><span data-stu-id="ebefa-103">Applications that provide authentication services must be able to replace the **Principal** object (<xref:System.Security.Principal.IPrincipal>) for a given thread.</span></span> <span data-ttu-id="ebefa-104">Более того, система безопасности должна защищать возможность замены объектов **Principal** , так как злонамеренно подключенный неправильный **Principal** является угрозой безопасности приложения, предоставляя неверное удостоверение или роль.</span><span class="sxs-lookup"><span data-stu-id="ebefa-104">Furthermore, the security system must help protect the ability to replace **Principal** objects because a maliciously attached, incorrect **Principal** compromises the security of your application by claiming an untrue identity or role.</span></span> <span data-ttu-id="ebefa-105">Таким образом, приложениям, которым требуется возможность замены **основной** объекты должны быть предоставлены <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> объекта для основного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ebefa-105">Therefore, applications that require the ability to replace **Principal** objects must be granted the <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> object for principal control.</span></span> <span data-ttu-id="ebefa-106">(Обратите внимание, что это разрешение не требуется для выполнения проверок безопасности на основе ролей или для создания объектов **Principal** .)</span><span class="sxs-lookup"><span data-stu-id="ebefa-106">(Note that this permission is not required for performing role-based security checks or for creating **Principal** objects.)</span></span>  
  
 <span data-ttu-id="ebefa-107">Текущий объект **Principal** можно заменить, выполнив следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="ebefa-107">The current **Principal** object can be replaced by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="ebefa-108">Создайте замещающий объект **Principal** и связанный объект **Identity** (удостоверение).</span><span class="sxs-lookup"><span data-stu-id="ebefa-108">Create the replacement **Principal** object and associated **Identity** object.</span></span>  
  
2.  <span data-ttu-id="ebefa-109">Подключите новый объект **Principal** к контексту вызова.</span><span class="sxs-lookup"><span data-stu-id="ebefa-109">Attach the new **Principal** object to the call context.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebefa-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ebefa-110">Example</span></span>  
 <span data-ttu-id="ebefa-111">В следующем примере показывается, как создать универсальный объект Principal и использовать его для задания участника потока.</span><span class="sxs-lookup"><span data-stu-id="ebefa-111">The following example shows how to create a generic principal object and use it to set the principal of a thread.</span></span>  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ebefa-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ebefa-112">See Also</span></span>  
 <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>  
 [<span data-ttu-id="ebefa-113">Объекты Principal и Identity</span><span class="sxs-lookup"><span data-stu-id="ebefa-113">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
