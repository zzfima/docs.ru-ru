---
title: Создание утверждений и значения ресурсов
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
ms.openlocfilehash: bd9a8b7faf3cd7a648ff6b2a50ac68f21561497c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093700"
---
# <a name="claim-creation-and-resource-values"></a><span data-ttu-id="02483-102">Создание утверждений и значения ресурсов</span><span class="sxs-lookup"><span data-stu-id="02483-102">Claim Creation and Resource Values</span></span>
<span data-ttu-id="02483-103">Класс <xref:System.IdentityModel.Claims.Claim> предоставляет несколько методов для создания экземпляров встроенных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="02483-103">The <xref:System.IdentityModel.Claims.Claim> class provides several methods for creating instances of built-in claims types.</span></span> <span data-ttu-id="02483-104">Из этих методов следующие не выполняют проверки семантики или формата переданного ресурса:</span><span class="sxs-lookup"><span data-stu-id="02483-104">Of these methods, the following perform no semantic or format checking on the supplied resource:</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> <span data-ttu-id="02483-105">(не проверяет длину или содержимое массива байтов)</span><span class="sxs-lookup"><span data-stu-id="02483-105">(does not check the length or content of the byte array)</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> <span data-ttu-id="02483-106">(не проверяет длину или содержимое массива байтов)</span><span class="sxs-lookup"><span data-stu-id="02483-106">(does not check the length or content of the byte array)</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 <span data-ttu-id="02483-107">При вызове перечисленных выше методов необходимо обеспечить, чтобы передаваемые значения ресурсов имели правильный формат или содержали правильную информацию (или и то, и другое).</span><span class="sxs-lookup"><span data-stu-id="02483-107">Care should be taken when calling the above methods to ensure that the resource values passed in are of the correct format or contain the correct kind of information (or both).</span></span>  
  
 <span data-ttu-id="02483-108">Следующие методы принимают определенные типы:</span><span class="sxs-lookup"><span data-stu-id="02483-108">The following methods take specific types:</span></span>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
-   <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a><span data-ttu-id="02483-109">См. также</span><span class="sxs-lookup"><span data-stu-id="02483-109">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="02483-110">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="02483-110">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
