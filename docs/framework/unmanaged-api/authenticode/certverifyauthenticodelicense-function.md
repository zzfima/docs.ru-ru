---
title: Функция CertVerifyAuthenticodeLicense
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a644e3e2df2544e8164cdaf3bbef3c44d3cd567f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502557"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="84956-102">Функция CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="84956-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="84956-103">Проверяет правильность лицензии Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="84956-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84956-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84956-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84956-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84956-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="84956-106">[в] Лицензия Authenticode XrML должна быть проверена.</span><span class="sxs-lookup"><span data-stu-id="84956-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="84956-107">См. в разделе [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) структуры.</span><span class="sxs-lookup"><span data-stu-id="84956-107">See the [CRYPTOAPI_BLOB](/windows/desktop/api/dpapi/ns-dpapi-_cryptoapi_blob) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="84956-108">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="84956-108">[in] Optional.</span></span> <span data-ttu-id="84956-109">Комбинация следующих значений:</span><span class="sxs-lookup"><span data-stu-id="84956-109">A combination of following values:</span></span>  
  
-   <span data-ttu-id="84956-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="84956-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
-   <span data-ttu-id="84956-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="84956-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
-   <span data-ttu-id="84956-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="84956-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
-   <span data-ttu-id="84956-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="84956-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
-   <span data-ttu-id="84956-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="84956-114">AXL_LIFETIME_SIGNING</span></span>  
  
-   <span data-ttu-id="84956-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="84956-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="84956-116">[из] Для получения сведений о подписавшем.</span><span class="sxs-lookup"><span data-stu-id="84956-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="84956-117">Если лицензия не подписана, переменной `dwError` присваивается значение TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="84956-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="84956-118">Это обязанность вызывающего, чтобы освободить ресурсы с помощью [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) функции после использования.</span><span class="sxs-lookup"><span data-stu-id="84956-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="84956-119">См. в разделе [структура AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="84956-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="84956-120">[из] Для получения сведений об отметке времени (если есть).</span><span class="sxs-lookup"><span data-stu-id="84956-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="84956-121">Если отметки времени для лицензии не установлены, переменной `dwError` присваивается значение TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="84956-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="84956-122">Это обязанность вызывающего, чтобы освободить ресурсы с помощью [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) функции после использования.</span><span class="sxs-lookup"><span data-stu-id="84956-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="84956-123">См. в разделе [структура AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="84956-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84956-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="84956-124">Return Value</span></span>  
 <span data-ttu-id="84956-125">Возвращает значение `S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="84956-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="84956-126">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="84956-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84956-127">См. также</span><span class="sxs-lookup"><span data-stu-id="84956-127">See also</span></span>
- [<span data-ttu-id="84956-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="84956-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
- [<span data-ttu-id="84956-129">Метод GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="84956-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="84956-130">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="84956-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
