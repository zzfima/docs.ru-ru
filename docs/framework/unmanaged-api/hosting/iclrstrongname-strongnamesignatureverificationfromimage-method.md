---
title: "Метод ICLRStrongName::StrongNameSignatureVerificationFromImage"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 57c8422d59a07de9ad045f2043594cb8d01f2f74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="e0c18-102">Метод ICLRStrongName::StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="e0c18-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="e0c18-103">Проверяет допустимость сборки, который уже сопоставлен в памяти для связанного открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="e0c18-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0c18-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0c18-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0c18-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="e0c18-106">[in] Относительный виртуальный адрес сопоставленных манифест.</span><span class="sxs-lookup"><span data-stu-id="e0c18-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="e0c18-107">[in] Размер в байтах, сопоставленные изображения.</span><span class="sxs-lookup"><span data-stu-id="e0c18-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="e0c18-108">[in] Флаги, которые влияют на поведение проверки.</span><span class="sxs-lookup"><span data-stu-id="e0c18-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="e0c18-109">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e0c18-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="e0c18-110">`SN_INFLAG_FORCE_VER`(0x00000001) — принудительная проверка, даже если это необходимо переопределить параметры реестра.</span><span class="sxs-lookup"><span data-stu-id="e0c18-110">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="e0c18-111">`SN_INFLAG_INSTALL`(0x00000002) — указывает, что это первая проверка, выполняемая для данного образа.</span><span class="sxs-lookup"><span data-stu-id="e0c18-111">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="e0c18-112">`SN_INFLAG_ADMIN_ACCESS`(0x00000004) — указывает, что кэш будет предоставлять доступ только пользователям с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="e0c18-112">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="e0c18-113">`SN_INFLAG_USER_ACCESS`(0x00000008) — указывает, что сборка будет доступен только для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="e0c18-113">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="e0c18-114">`SN_INFLAG_ALL_ACCESS`(0x00000010) — указывает, что кэш будет предоставляют никаких гарантий ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="e0c18-114">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="e0c18-115">`SN_INFLAG_RUNTIME`(0x80000000) — зарезервировано для внутренней отладки.</span><span class="sxs-lookup"><span data-stu-id="e0c18-115">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="e0c18-116">[out] Флаг для дополнительных выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e0c18-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="e0c18-117">Поддерживается следующее значение:</span><span class="sxs-lookup"><span data-stu-id="e0c18-117">The following value is supported:</span></span>  
  
-   <span data-ttu-id="e0c18-118">`SN_OUTFLAG_WAS_VERIFIED`(0x00000001) — это значение равно `false` для указания, что проверка прошла успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="e0c18-118">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0c18-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e0c18-119">Return Value</span></span>  
 <span data-ttu-id="e0c18-120">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="e0c18-120">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0c18-121">Требования</span><span class="sxs-lookup"><span data-stu-id="e0c18-121">Requirements</span></span>  
 <span data-ttu-id="e0c18-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0c18-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0c18-123">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e0c18-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e0c18-124">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0c18-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0c18-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0c18-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c18-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e0c18-126">See Also</span></span>  
 [<span data-ttu-id="e0c18-127">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e0c18-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
