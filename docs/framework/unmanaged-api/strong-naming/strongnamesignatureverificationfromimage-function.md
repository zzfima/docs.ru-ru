---
title: Функция StrongNameSignatureVerificationFromImage
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54b1d35d1c40289bad465978750ba738acf28c90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212444"
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="11b5e-102">Функция StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="11b5e-102">StrongNameSignatureVerificationFromImage Function</span></span>
<span data-ttu-id="11b5e-103">Проверяет допустимость сборки, которая уже была сопоставлена с памятью, для связанного открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="11b5e-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="11b5e-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="11b5e-104">This function has been deprecated.</span></span> <span data-ttu-id="11b5e-105">Используйте [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="11b5e-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11b5e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11b5e-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11b5e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="11b5e-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="11b5e-108">[in] Относительный виртуальный адрес сопоставленные манифест.</span><span class="sxs-lookup"><span data-stu-id="11b5e-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="11b5e-109">[in] Размер в байтах, сопоставленные изображения.</span><span class="sxs-lookup"><span data-stu-id="11b5e-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="11b5e-110">[in] Флаги, которые влияют на поведение проверки.</span><span class="sxs-lookup"><span data-stu-id="11b5e-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="11b5e-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="11b5e-111">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="11b5e-112">(0x00000001) — проверка производится, даже если это необходимо переопределить параметры реестра.</span><span class="sxs-lookup"><span data-stu-id="11b5e-112">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="11b5e-113">(0x00000002) — указывает, что это первая проверка, выполняемая в этом образе.</span><span class="sxs-lookup"><span data-stu-id="11b5e-113">(0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="11b5e-114">(0x00000004) — указывает, что кэш будет предоставлять доступ только к пользователям, имеющим права администратора.</span><span class="sxs-lookup"><span data-stu-id="11b5e-114">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="11b5e-115">(0x00000008) — указывает, что сборка будет доступен только для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="11b5e-115">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="11b5e-116">(0x00000010) — указывает, что кэш будет предоставлять никаких гарантий, ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="11b5e-116">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="11b5e-117">(0x80000000) — зарезервировано для внутренней отладки.</span><span class="sxs-lookup"><span data-stu-id="11b5e-117">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="11b5e-118">[out] Флаг, Дополнительные выходные сведения.</span><span class="sxs-lookup"><span data-stu-id="11b5e-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="11b5e-119">Поддерживается следующее значение:</span><span class="sxs-lookup"><span data-stu-id="11b5e-119">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="11b5e-120">(0x00000001) — это значение присваивается `false` для указания, что проверка выполнена успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="11b5e-120">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11b5e-121">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="11b5e-121">Return Value</span></span>  
 `true` <span data-ttu-id="11b5e-122">После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="11b5e-122">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11b5e-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="11b5e-123">Remarks</span></span>  
 <span data-ttu-id="11b5e-124">Если `StrongNameSignatureVerificationFromImage` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="11b5e-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11b5e-125">Требования</span><span class="sxs-lookup"><span data-stu-id="11b5e-125">Requirements</span></span>  
 <span data-ttu-id="11b5e-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11b5e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11b5e-127">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="11b5e-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="11b5e-128">**Библиотека:** Включена как ресурс в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="11b5e-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 **<span data-ttu-id="11b5e-129">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="11b5e-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11b5e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="11b5e-130">See also</span></span>

- [<span data-ttu-id="11b5e-131">Метод StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="11b5e-131">StrongNameSignatureVerificationFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [<span data-ttu-id="11b5e-132">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="11b5e-132">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
