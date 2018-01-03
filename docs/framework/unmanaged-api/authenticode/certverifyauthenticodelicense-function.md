---
title: "Функция CertVerifyAuthenticodeLicense"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertVerifyAuthenticodeLicense
api_location: clr.dll
api_type: DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bab3a3bcee52a302345ccdcfad81e7f67efdd8d5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="d031b-102">Функция CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="d031b-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="d031b-103">Проверяет правильность лицензии Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="d031b-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d031b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d031b-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d031b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d031b-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="d031b-106">[в] Лицензия Authenticode XrML должна быть проверена.</span><span class="sxs-lookup"><span data-stu-id="d031b-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="d031b-107">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="d031b-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d031b-108">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="d031b-108">[in] Optional.</span></span> <span data-ttu-id="d031b-109">Комбинация следующих значений:</span><span class="sxs-lookup"><span data-stu-id="d031b-109">A combination of following values:</span></span>  
  
-   <span data-ttu-id="d031b-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="d031b-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
-   <span data-ttu-id="d031b-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="d031b-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
-   <span data-ttu-id="d031b-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="d031b-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
-   <span data-ttu-id="d031b-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="d031b-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
-   <span data-ttu-id="d031b-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="d031b-114">AXL_LIFETIME_SIGNING</span></span>  
  
-   <span data-ttu-id="d031b-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="d031b-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="d031b-116">[из] Для получения сведений о подписавшем.</span><span class="sxs-lookup"><span data-stu-id="d031b-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="d031b-117">Если лицензия не подписана, переменной `dwError` присваивается значение TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="d031b-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="d031b-118">Это обязанность вызывающего, чтобы освободить ресурсы с помощью [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) функции после их использования.</span><span class="sxs-lookup"><span data-stu-id="d031b-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="d031b-119">В разделе [структуры AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="d031b-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="d031b-120">[из] Для получения сведений об отметке времени (если есть).</span><span class="sxs-lookup"><span data-stu-id="d031b-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="d031b-121">Если отметки времени для лицензии не установлены, переменной `dwError` присваивается значение TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="d031b-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="d031b-122">Это обязанность вызывающего, чтобы освободить ресурсы с помощью [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) функции после их использования.</span><span class="sxs-lookup"><span data-stu-id="d031b-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="d031b-123">В разделе [структуры AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="d031b-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d031b-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d031b-124">Return Value</span></span>  
 <span data-ttu-id="d031b-125">Возвращает значение `S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="d031b-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="d031b-126">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="d031b-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d031b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d031b-127">See Also</span></span>  
 [<span data-ttu-id="d031b-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="d031b-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)  
 [<span data-ttu-id="d031b-129">Метод GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="d031b-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="d031b-130">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d031b-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
