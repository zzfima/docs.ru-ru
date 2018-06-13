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
ms.openlocfilehash: d79a8c5bc204b6479741c32c47e6b41ff873a1bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406927"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="65f56-102">Функция CertVerifyAuthenticodeLicense</span><span class="sxs-lookup"><span data-stu-id="65f56-102">CertVerifyAuthenticodeLicense Function</span></span>
<span data-ttu-id="65f56-103">Проверяет правильность лицензии Authenticode XrML.</span><span class="sxs-lookup"><span data-stu-id="65f56-103">Verifies the validity of an Authenticode XrML license.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65f56-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65f56-104">Syntax</span></span>  
  
```  
HRESULT CertVerifyAuthenticodeLicense (  
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,  
    [in]   OPTIONAL DWORD                     dwFlags,  
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,  
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65f56-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="65f56-105">Parameters</span></span>  
 `pLicenseBlob`  
 <span data-ttu-id="65f56-106">[в] Лицензия Authenticode XrML должна быть проверена.</span><span class="sxs-lookup"><span data-stu-id="65f56-106">[in] The Authenticode XrML license to be verified.</span></span>  
  
 <span data-ttu-id="65f56-107">В разделе [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="65f56-107">See the [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) structure.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="65f56-108">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="65f56-108">[in] Optional.</span></span> <span data-ttu-id="65f56-109">Комбинация следующих значений:</span><span class="sxs-lookup"><span data-stu-id="65f56-109">A combination of following values:</span></span>  
  
-   <span data-ttu-id="65f56-110">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="65f56-110">AXL_REVOCATION_NO_CHECK</span></span>  
  
-   <span data-ttu-id="65f56-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="65f56-111">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>  
  
-   <span data-ttu-id="65f56-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="65f56-112">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>  
  
-   <span data-ttu-id="65f56-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="65f56-113">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>  
  
-   <span data-ttu-id="65f56-114">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="65f56-114">AXL_LIFETIME_SIGNING</span></span>  
  
-   <span data-ttu-id="65f56-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="65f56-115">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>  
  
 `pSignerInfo`  
 <span data-ttu-id="65f56-116">[из] Для получения сведений о подписавшем.</span><span class="sxs-lookup"><span data-stu-id="65f56-116">[out] To receive the signer's information.</span></span> <span data-ttu-id="65f56-117">Если лицензия не подписана, переменной `dwError` присваивается значение TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="65f56-117">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="65f56-118">Это обязанность вызывающего, чтобы освободить ресурсы с помощью [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) функции после их использования.</span><span class="sxs-lookup"><span data-stu-id="65f56-118">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="65f56-119">В разделе [структуры AXL_AUTHENTICODE_SIGNER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="65f56-119">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md).</span></span>  
  
 `pTimestamperInfo`  
 <span data-ttu-id="65f56-120">[из] Для получения сведений об отметке времени (если есть).</span><span class="sxs-lookup"><span data-stu-id="65f56-120">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="65f56-121">Если отметки времени для лицензии не установлены, переменной `dwError` присваивается значение TRUST_E_NOSIGNATURE.</span><span class="sxs-lookup"><span data-stu-id="65f56-121">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="65f56-122">Это обязанность вызывающего, чтобы освободить ресурсы с помощью [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) функции после их использования.</span><span class="sxs-lookup"><span data-stu-id="65f56-122">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>  
  
 <span data-ttu-id="65f56-123">В разделе [структуры AXL_AUTHENTICODE_TIMESTAMPER_INFO](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span><span class="sxs-lookup"><span data-stu-id="65f56-123">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65f56-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="65f56-124">Return Value</span></span>  
 <span data-ttu-id="65f56-125">Возвращает значение `S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="65f56-125">Returns `S_OK` if successful.</span></span> <span data-ttu-id="65f56-126">В противном случае возвращается код ошибки.</span><span class="sxs-lookup"><span data-stu-id="65f56-126">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f56-127">См. также</span><span class="sxs-lookup"><span data-stu-id="65f56-127">See Also</span></span>  
 [<span data-ttu-id="65f56-128">Authenticode</span><span class="sxs-lookup"><span data-stu-id="65f56-128">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)  
 [<span data-ttu-id="65f56-129">Метод GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="65f56-129">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="65f56-130">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="65f56-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
