---
title: Создание утверждений и значения ресурсов
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], creation and resource values
ms.assetid: 30431f76-cbe7-4bad-bad7-8e43e23a82d4
ms.openlocfilehash: 5c2904f68ba50df99504e2f70c9170490ca54f73
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645574"
---
# <a name="claim-creation-and-resource-values"></a><span data-ttu-id="bd775-102">Создание утверждений и значения ресурсов</span><span class="sxs-lookup"><span data-stu-id="bd775-102">Claim Creation and Resource Values</span></span>
<span data-ttu-id="bd775-103">Класс <xref:System.IdentityModel.Claims.Claim> предоставляет несколько методов для создания экземпляров встроенных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="bd775-103">The <xref:System.IdentityModel.Claims.Claim> class provides several methods for creating instances of built-in claims types.</span></span> <span data-ttu-id="bd775-104">Из этих методов следующие не выполняют проверки семантики или формата переданного ресурса:</span><span class="sxs-lookup"><span data-stu-id="bd775-104">Of these methods, the following perform no semantic or format checking on the supplied resource:</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDnsClaim%2A>  
  
- <span data-ttu-id="bd775-105"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (не проверяет длину или содержимое байтового массива).</span><span class="sxs-lookup"><span data-stu-id="bd775-105"><xref:System.IdentityModel.Claims.Claim.CreateHashClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateNameClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateSpnClaim%2A>  
  
- <span data-ttu-id="bd775-106"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (не проверяет длину или содержимое байтового массива).</span><span class="sxs-lookup"><span data-stu-id="bd775-106"><xref:System.IdentityModel.Claims.Claim.CreateThumbprintClaim%2A> (does not check the length or content of the byte array)</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUpnClaim%2A>  
  
 <span data-ttu-id="bd775-107">При вызове перечисленных выше методов необходимо обеспечить, чтобы передаваемые значения ресурсов имели правильный формат или содержали правильную информацию (или и то, и другое).</span><span class="sxs-lookup"><span data-stu-id="bd775-107">Care should be taken when calling the above methods to ensure that the resource values passed in are of the correct format or contain the correct kind of information (or both).</span></span>  
  
 <span data-ttu-id="bd775-108">Следующие методы принимают определенные типы:</span><span class="sxs-lookup"><span data-stu-id="bd775-108">The following methods take specific types:</span></span>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateDenyOnlyWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateMailAddressClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateRsaClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateUriClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateWindowsSidClaim%2A>  
  
- <xref:System.IdentityModel.Claims.Claim.CreateX500DistinguishedNameClaim%2A>  
  
## <a name="see-also"></a><span data-ttu-id="bd775-109">См. также</span><span class="sxs-lookup"><span data-stu-id="bd775-109">See also</span></span>

- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [<span data-ttu-id="bd775-110">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="bd775-110">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
