---
title: "Authenticode (справочник по неуправляемым интерфейсам API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b790064ef64ab44f3798a62d5dbf004f0f0bba6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="016e8-102">Authenticode (справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="016e8-102">Authenticode (Unmanaged API Reference)</span></span>
<span data-ttu-id="016e8-103">Поддерживает модуль создания и проверки лицензий Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="016e8-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="016e8-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="016e8-104">In This Section</span></span>  
 [<span data-ttu-id="016e8-105">Функция _AxlGetIssuerPublicKeyHash</span><span class="sxs-lookup"><span data-stu-id="016e8-105">_AxlGetIssuerPublicKeyHash Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="016e8-106">Получает хэш SHA-1 открытого ключа, связанного с закрытым ключом, который используется для подписания указанного сертификата.</span><span class="sxs-lookup"><span data-stu-id="016e8-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="016e8-107">Функция _AxlPublicKeyBlobToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="016e8-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="016e8-108">Вычисляет токен открытого ключа строгого имени из формата CSP PUBLICKEYBLOB.</span><span class="sxs-lookup"><span data-stu-id="016e8-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="016e8-109">Функция _AxlRSAKeyValueToPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="016e8-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="016e8-110">Преобразует модули и экспоненту в строгое имя маркера открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="016e8-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="016e8-111">Функция CertFreeAuthenticodeSignerInfo</span><span class="sxs-lookup"><span data-stu-id="016e8-111">CertFreeAuthenticodeSignerInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="016e8-112">Освобождает ресурсы, выделенные для структуры AXL_AUTHENTICODE_SIGNER_INFO.</span><span class="sxs-lookup"><span data-stu-id="016e8-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="016e8-113">Функция CertFreeAuthenticodeTimestamperInfo</span><span class="sxs-lookup"><span data-stu-id="016e8-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="016e8-114">Освобождает ресурсы, выделенные для структуры AXL_AUTHENTICODE_TIMESTAMPER_INFO.</span><span class="sxs-lookup"><span data-stu-id="016e8-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="016e8-115">Функция CertTimestampAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="016e8-115">CertTimestampAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="016e8-116">Присваивает метки времени лицензии Authenticode XrML, созданной функцией CertCreateAuthenticodeLicense.</span><span class="sxs-lookup"><span data-stu-id="016e8-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="016e8-117">Функция CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="016e8-117">CertVerifyAuthenticodeLicense Function</span></span>](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="016e8-118">Проверяет правильность лицензии Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="016e8-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="016e8-119">Структура AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="016e8-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="016e8-120">Определяет информацию о подписавшем Authenticode.</span><span class="sxs-lookup"><span data-stu-id="016e8-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="016e8-121">Структура AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="016e8-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="016e8-122">Определяет информацию об отметке времени Authenticode.</span><span class="sxs-lookup"><span data-stu-id="016e8-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="016e8-123">См. также</span><span class="sxs-lookup"><span data-stu-id="016e8-123">See Also</span></span>  
 [<span data-ttu-id="016e8-124">Справочник по неуправляемым API</span><span class="sxs-lookup"><span data-stu-id="016e8-124">Unmanaged API Reference</span></span>](../../../../docs/framework/unmanaged-api/index.md)
