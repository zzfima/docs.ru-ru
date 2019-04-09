---
title: Метод ICLRStrongName::StrongNameSignatureVerificationFromImage
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7e09ac96a8803f41d78b532c9da67315e5dd6b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113741"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a><span data-ttu-id="39c35-102">Метод ICLRStrongName::StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="39c35-102">ICLRStrongName::StrongNameSignatureVerificationFromImage Method</span></span>
<span data-ttu-id="39c35-103">Проверяет допустимость сборки, которая уже была сопоставлена с памятью, для связанного открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="39c35-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c35-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39c35-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39c35-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="39c35-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="39c35-106">[in] Относительный виртуальный адрес сопоставленные манифест.</span><span class="sxs-lookup"><span data-stu-id="39c35-106">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="39c35-107">[in] Размер в байтах, сопоставленные изображения.</span><span class="sxs-lookup"><span data-stu-id="39c35-107">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="39c35-108">[in] Флаги, которые влияют на поведение проверки.</span><span class="sxs-lookup"><span data-stu-id="39c35-108">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="39c35-109">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="39c35-109">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="39c35-110">(0x00000001) — проверка производится, даже если это необходимо переопределить параметры реестра.</span><span class="sxs-lookup"><span data-stu-id="39c35-110">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="39c35-111">(0x00000002) — указывает, что это первая проверка, выполняемая в этом образе.</span><span class="sxs-lookup"><span data-stu-id="39c35-111">(0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="39c35-112">(0x00000004) — указывает, что кэш будет предоставлять доступ только к пользователям, имеющим права администратора.</span><span class="sxs-lookup"><span data-stu-id="39c35-112">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="39c35-113">(0x00000008) — указывает, что сборка будет доступен только для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="39c35-113">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="39c35-114">(0x00000010) — указывает, что кэш будет предоставлять никаких гарантий, ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="39c35-114">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="39c35-115">(0x80000000) — зарезервировано для внутренней отладки.</span><span class="sxs-lookup"><span data-stu-id="39c35-115">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="39c35-116">[out] Флаг, Дополнительные выходные сведения.</span><span class="sxs-lookup"><span data-stu-id="39c35-116">[out] A flag for additional output information.</span></span> <span data-ttu-id="39c35-117">Поддерживается следующее значение:</span><span class="sxs-lookup"><span data-stu-id="39c35-117">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="39c35-118">(0x00000001) — это значение присваивается `false` для указания, что проверка выполнена успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="39c35-118">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39c35-119">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="39c35-119">Return Value</span></span>  
 `S_OK` <span data-ttu-id="39c35-120">Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="39c35-120">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39c35-121">Требования</span><span class="sxs-lookup"><span data-stu-id="39c35-121">Requirements</span></span>  
 <span data-ttu-id="39c35-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39c35-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39c35-123">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="39c35-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="39c35-124">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39c35-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="39c35-125">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="39c35-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="39c35-126">См. также</span><span class="sxs-lookup"><span data-stu-id="39c35-126">See also</span></span>

- [<span data-ttu-id="39c35-127">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="39c35-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
