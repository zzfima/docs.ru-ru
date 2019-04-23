---
title: Поиск утверждений в наборах утверждений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- claims [WCF], finding in a claimset
- claims [WCF]
ms.assetid: a76ce107-aeb3-47d0-bfa9-134c53664e20
ms.openlocfilehash: 42e6ee682220913f872da337eb41f6c290082988
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137128"
---
# <a name="finding-claims-in-a-claimset"></a><span data-ttu-id="0c750-102">Поиск утверждений в наборах утверждений</span><span class="sxs-lookup"><span data-stu-id="0c750-102">Finding Claims in a ClaimSet</span></span>
<span data-ttu-id="0c750-103">При использовании авторизации на основе утверждений часто выполняется проверка содержимого <xref:System.IdentityModel.Claims.ClaimSet> для определенных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="0c750-103">Examining the content of a <xref:System.IdentityModel.Claims.ClaimSet> for particular types of claims is a common task when using claim-based authorization.</span></span> <span data-ttu-id="0c750-104">Чтобы проверить <xref:System.IdentityModel.Claims.ClaimSet> на наличие определенных утверждений, используйте метод <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c750-104">To examine a <xref:System.IdentityModel.Claims.ClaimSet> for the presence of particular claims, use the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%2A> method.</span></span> <span data-ttu-id="0c750-105">Этот метод обеспечивает более высокую производительность по сравнению с выполнением итерации непосредственно с <xref:System.IdentityModel.Claims.ClaimSet>.</span><span class="sxs-lookup"><span data-stu-id="0c750-105">This method provides better performance than iterating directly over the <xref:System.IdentityModel.Claims.ClaimSet>.</span></span> <span data-ttu-id="0c750-106">Использование этого метода показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0c750-106">The following example demonstrates this usage.</span></span> <span data-ttu-id="0c750-107">Обратите внимание, что параметры `claimType` и `claimRight` могут иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="0c750-107">Note that the `claimType` and `claimRight` parameters can be `null`.</span></span> <span data-ttu-id="0c750-108">В этом случае параметры будут соответствовать всем типам и правам утверждения.</span><span class="sxs-lookup"><span data-stu-id="0c750-108">In that case, the parameters will match all claim types and claim rights.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c750-109">Пример</span><span class="sxs-lookup"><span data-stu-id="0c750-109">Example</span></span>  
 [!code-csharp[c_FindClaimsPerf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_findclaimsperf/cs/c_findclaimsperf.cs#2)]
 [!code-vb[c_FindClaimsPerf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_findclaimsperf/vb/c_findclaimsperf.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0c750-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0c750-110">See also</span></span>

- [<span data-ttu-id="0c750-111">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="0c750-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
