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
ms.openlocfilehash: d5193756861f407315ec82e4419f1d04495c7dd2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606037"
---
# <a name="replacing-a-principal-object"></a><span data-ttu-id="cfce6-102">Замена объекта Principal</span><span class="sxs-lookup"><span data-stu-id="cfce6-102">Replacing a Principal Object</span></span>
<span data-ttu-id="cfce6-103">Приложения, предоставляющие службы проверки подлинности, должны иметь возможность заменять объект **Principal** (<xref:System.Security.Principal.IPrincipal>) для данного потока.</span><span class="sxs-lookup"><span data-stu-id="cfce6-103">Applications that provide authentication services must be able to replace the **Principal** object (<xref:System.Security.Principal.IPrincipal>) for a given thread.</span></span> <span data-ttu-id="cfce6-104">Более того, система безопасности должна защищать возможность замены объектов **Principal** , так как злонамеренно подключенный неправильный **Principal** является угрозой безопасности приложения, предоставляя неверное удостоверение или роль.</span><span class="sxs-lookup"><span data-stu-id="cfce6-104">Furthermore, the security system must help protect the ability to replace **Principal** objects because a maliciously attached, incorrect **Principal** compromises the security of your application by claiming an untrue identity or role.</span></span> <span data-ttu-id="cfce6-105">Таким образом, приложениям, которым требуется возможность замены объектов **Principal** , должен быть предоставлен объект <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> для элемента управления "Участник".</span><span class="sxs-lookup"><span data-stu-id="cfce6-105">Therefore, applications that require the ability to replace **Principal** objects must be granted the <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> object for principal control.</span></span> <span data-ttu-id="cfce6-106">(Обратите внимание, что это разрешение не требуется для выполнения проверок безопасности на основе ролей или для создания объектов **Principal** .)</span><span class="sxs-lookup"><span data-stu-id="cfce6-106">(Note that this permission is not required for performing role-based security checks or for creating **Principal** objects.)</span></span>  
  
 <span data-ttu-id="cfce6-107">Текущий объект **Principal** можно заменить, выполнив следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="cfce6-107">The current **Principal** object can be replaced by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="cfce6-108">Создайте замещающий объект **Principal** и связанный объект **Identity** (удостоверение).</span><span class="sxs-lookup"><span data-stu-id="cfce6-108">Create the replacement **Principal** object and associated **Identity** object.</span></span>  
  
2.  <span data-ttu-id="cfce6-109">Подключите новый объект **Principal** к контексту вызова.</span><span class="sxs-lookup"><span data-stu-id="cfce6-109">Attach the new **Principal** object to the call context.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfce6-110">Пример</span><span class="sxs-lookup"><span data-stu-id="cfce6-110">Example</span></span>  
 <span data-ttu-id="cfce6-111">В следующем примере показывается, как создать универсальный объект Principal и использовать его для задания участника потока.</span><span class="sxs-lookup"><span data-stu-id="cfce6-111">The following example shows how to create a generic principal object and use it to set the principal of a thread.</span></span>  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cfce6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="cfce6-112">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>
- [<span data-ttu-id="cfce6-113">Объекты Principal и Identity</span><span class="sxs-lookup"><span data-stu-id="cfce6-113">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
