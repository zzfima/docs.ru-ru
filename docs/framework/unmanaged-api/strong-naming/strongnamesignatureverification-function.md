---
title: Функция StrongNameSignatureVerification
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c888c32a0b40d2458a919613e35ca9d1d830c4f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459239"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="c7f55-102">Функция StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="c7f55-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="c7f55-103">Возвращает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени, которая будет проверена в соответствии с заданными флагами.</span><span class="sxs-lookup"><span data-stu-id="c7f55-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="c7f55-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="c7f55-104">This function has been deprecated.</span></span> <span data-ttu-id="c7f55-105">Используйте [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="c7f55-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7f55-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7f55-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7f55-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7f55-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c7f55-108">[in] Путь к переносимого исполняемого файла (.dll или .exe) для сборки для проверки.</span><span class="sxs-lookup"><span data-stu-id="c7f55-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="c7f55-109">[in] Флаги для изменения поведения проверки.</span><span class="sxs-lookup"><span data-stu-id="c7f55-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="c7f55-110">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c7f55-110">The following values are supported:</span></span>  
  
-   <span data-ttu-id="c7f55-111">`SN_INFLAG_FORCE_VER` (0x00000001) — принудительная проверка, даже если это необходимо переопределить параметры реестра.</span><span class="sxs-lookup"><span data-stu-id="c7f55-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   <span data-ttu-id="c7f55-112">`SN_INFLAG_INSTALL` (0x00000002) — указывает, что в первый раз, проверка манифеста.</span><span class="sxs-lookup"><span data-stu-id="c7f55-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   <span data-ttu-id="c7f55-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) — указывает, что кэш будет предоставлять доступ только пользователям с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="c7f55-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   <span data-ttu-id="c7f55-114">`SN_INFLAG_USER_ACCESS` (0x00000008) — указывает, что сборка будет доступен только для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="c7f55-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   <span data-ttu-id="c7f55-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) — указывает, что кэш будет предоставляют никаких гарантий ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="c7f55-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   <span data-ttu-id="c7f55-116">`SN_INFLAG_RUNTIME` (0x80000000) — зарезервировано для внутренней отладки.</span><span class="sxs-lookup"><span data-stu-id="c7f55-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="c7f55-117">[out] Флаги, указывающее, был ли проверен подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="c7f55-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="c7f55-118">Поддерживается следующее значение:</span><span class="sxs-lookup"><span data-stu-id="c7f55-118">The following value is supported:</span></span>  
  
-   <span data-ttu-id="c7f55-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) — это значение равно `false` для указания, что проверка прошла успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="c7f55-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7f55-120">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c7f55-120">Return Value</span></span>  
 <span data-ttu-id="c7f55-121">`true` Если проверка прошла успешно; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="c7f55-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7f55-122">Требования</span><span class="sxs-lookup"><span data-stu-id="c7f55-122">Requirements</span></span>  
 <span data-ttu-id="c7f55-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7f55-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7f55-124">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c7f55-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c7f55-125">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7f55-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c7f55-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7f55-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7f55-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c7f55-127">See Also</span></span>  
 [<span data-ttu-id="c7f55-128">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="c7f55-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="c7f55-129">Метод StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="c7f55-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="c7f55-130">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c7f55-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
