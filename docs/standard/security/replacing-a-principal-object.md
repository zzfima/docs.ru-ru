---
title: "Замена объекта Principal"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET Framework], replacing principal objects
- security [.NET Framework], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c53064ae12889df09b5259fbb7c8159cfdcd07aa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="replacing-a-principal-object"></a><span data-ttu-id="49093-102">Замена объекта Principal</span><span class="sxs-lookup"><span data-stu-id="49093-102">Replacing a Principal Object</span></span>
<span data-ttu-id="49093-103">Приложения, предоставляющие службы проверки подлинности, должны иметь возможность заменять объект **Principal** (<xref:System.Security.Principal.IPrincipal>) для данного потока.</span><span class="sxs-lookup"><span data-stu-id="49093-103">Applications that provide authentication services must be able to replace the **Principal** object (<xref:System.Security.Principal.IPrincipal>) for a given thread.</span></span> <span data-ttu-id="49093-104">Более того, система безопасности должна защищать возможность замены объектов **Principal** , так как злонамеренно подключенный неправильный **Principal** является угрозой безопасности приложения, предоставляя неверное удостоверение или роль.</span><span class="sxs-lookup"><span data-stu-id="49093-104">Furthermore, the security system must help protect the ability to replace **Principal** objects because a maliciously attached, incorrect **Principal** compromises the security of your application by claiming an untrue identity or role.</span></span> <span data-ttu-id="49093-105">Таким образом, приложениям, которым требуется возможность замены **основной** объекты должны быть предоставлены <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> объекта для основного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="49093-105">Therefore, applications that require the ability to replace **Principal** objects must be granted the <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> object for principal control.</span></span> <span data-ttu-id="49093-106">(Обратите внимание, что это разрешение не требуется для выполнения проверок безопасности на основе ролей или для создания объектов **Principal** .)</span><span class="sxs-lookup"><span data-stu-id="49093-106">(Note that this permission is not required for performing role-based security checks or for creating **Principal** objects.)</span></span>  
  
 <span data-ttu-id="49093-107">Текущий объект **Principal** можно заменить, выполнив следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="49093-107">The current **Principal** object can be replaced by performing the following tasks:</span></span>  
  
1.  <span data-ttu-id="49093-108">Создайте замещающий объект **Principal** и связанный объект **Identity** (удостоверение).</span><span class="sxs-lookup"><span data-stu-id="49093-108">Create the replacement **Principal** object and associated **Identity** object.</span></span>  
  
2.  <span data-ttu-id="49093-109">Подключите новый объект **Principal** к контексту вызова.</span><span class="sxs-lookup"><span data-stu-id="49093-109">Attach the new **Principal** object to the call context.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49093-110">Пример</span><span class="sxs-lookup"><span data-stu-id="49093-110">Example</span></span>  
 <span data-ttu-id="49093-111">В следующем примере показывается, как создать универсальный объект Principal и использовать его для задания участника потока.</span><span class="sxs-lookup"><span data-stu-id="49093-111">The following example shows how to create a generic principal object and use it to set the principal of a thread.</span></span>  
  
 [!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
 [!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="49093-112">См. также</span><span class="sxs-lookup"><span data-stu-id="49093-112">See Also</span></span>  
 <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>  
 [<span data-ttu-id="49093-113">Объекты Principal и Identity</span><span class="sxs-lookup"><span data-stu-id="49093-113">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
