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
ms.openlocfilehash: 919c746b738246d76e90730c42882bfdd3ac6edc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="75fbd-102">Функция StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="75fbd-102">StrongNameSignatureVerificationFromImage Function</span></span>
<span data-ttu-id="75fbd-103">Проверяет допустимость сборки, который уже сопоставлен в памяти для связанного открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="75fbd-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="75fbd-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="75fbd-104">This function has been deprecated.</span></span> <span data-ttu-id="75fbd-105">Используйте [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="75fbd-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75fbd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75fbd-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75fbd-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="75fbd-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="75fbd-108">[in] Относительный виртуальный адрес сопоставленных манифест.</span><span class="sxs-lookup"><span data-stu-id="75fbd-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="75fbd-109">[in] Размер в байтах, сопоставленные изображения.</span><span class="sxs-lookup"><span data-stu-id="75fbd-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="75fbd-110">[in] Флаги, которые влияют на поведение проверки.</span><span class="sxs-lookup"><span data-stu-id="75fbd-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="75fbd-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="75fbd-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="75fbd-112">`SN_INFLAG_FORCE_VER` (0x00000001) — принудительная проверка, даже если это необходимо переопределить параметры реестра.</span><span class="sxs-lookup"><span data-stu-id="75fbd-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="75fbd-113">`SN_INFLAG_INSTALL` (0x00000002) — указывает, что это первая проверка, выполняемая для данного образа.</span><span class="sxs-lookup"><span data-stu-id="75fbd-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
-   <span data-ttu-id="75fbd-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) — указывает, что кэш будет предоставлять доступ только пользователям с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="75fbd-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="75fbd-115">`SN_INFLAG_USER_ACCESS` (0x00000008) — указывает, что сборка будет доступен только для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="75fbd-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="75fbd-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) — указывает, что кэш будет предоставляют никаких гарантий ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="75fbd-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="75fbd-117">`SN_INFLAG_RUNTIME` (0x80000000) — зарезервировано для внутренней отладки.</span><span class="sxs-lookup"><span data-stu-id="75fbd-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="75fbd-118">[out] Флаг для дополнительных выходных данных.</span><span class="sxs-lookup"><span data-stu-id="75fbd-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="75fbd-119">Поддерживается следующее значение:</span><span class="sxs-lookup"><span data-stu-id="75fbd-119">The following value is supported:</span></span>  
  
-   <span data-ttu-id="75fbd-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) — это значение равно `false` для указания, что проверка прошла успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="75fbd-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75fbd-121">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="75fbd-121">Return Value</span></span>  
 <span data-ttu-id="75fbd-122">`true` При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="75fbd-122">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75fbd-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="75fbd-123">Remarks</span></span>  
 <span data-ttu-id="75fbd-124">Если `StrongNameSignatureVerificationFromImage` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="75fbd-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75fbd-125">Требования</span><span class="sxs-lookup"><span data-stu-id="75fbd-125">Requirements</span></span>  
 <span data-ttu-id="75fbd-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75fbd-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75fbd-127">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="75fbd-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="75fbd-128">**Библиотека:** включена как ресурс в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="75fbd-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="75fbd-129">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75fbd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75fbd-130">См. также</span><span class="sxs-lookup"><span data-stu-id="75fbd-130">See Also</span></span>  
 [<span data-ttu-id="75fbd-131">Метод StrongNameSignatureVerificationFromImage</span><span class="sxs-lookup"><span data-stu-id="75fbd-131">StrongNameSignatureVerificationFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)  
 [<span data-ttu-id="75fbd-132">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="75fbd-132">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
