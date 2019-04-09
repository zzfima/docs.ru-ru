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
ms.openlocfilehash: c398663b84637d2551b0d94bd59b9e0994721ba5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124771"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="2361e-102">Функция StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="2361e-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="2361e-103">Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени, которая проверяется в соответствии с заданными флагами.</span><span class="sxs-lookup"><span data-stu-id="2361e-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="2361e-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="2361e-104">This function has been deprecated.</span></span> <span data-ttu-id="2361e-105">Используйте [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="2361e-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2361e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2361e-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2361e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="2361e-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="2361e-108">[in] Путь к переносимого исполняемого файла (.dll или .exe) для сборки для проверки.</span><span class="sxs-lookup"><span data-stu-id="2361e-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="2361e-109">[in] Флаги для изменения поведения проверки.</span><span class="sxs-lookup"><span data-stu-id="2361e-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="2361e-110">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="2361e-110">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="2361e-111">(0x00000001) — проверка производится, даже если это необходимо переопределить параметры реестра.</span><span class="sxs-lookup"><span data-stu-id="2361e-111">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="2361e-112">(0x00000002) — указывает, что это в первый раз, проверка манифеста.</span><span class="sxs-lookup"><span data-stu-id="2361e-112">(0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="2361e-113">(0x00000004) — указывает, что кэш будет предоставлять доступ только к пользователям, имеющим права администратора.</span><span class="sxs-lookup"><span data-stu-id="2361e-113">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="2361e-114">(0x00000008) — указывает, что сборка будет доступен только для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="2361e-114">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="2361e-115">(0x00000010) — указывает, что кэш будет предоставлять никаких гарантий, ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="2361e-115">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="2361e-116">(0x80000000) — зарезервировано для внутренней отладки.</span><span class="sxs-lookup"><span data-stu-id="2361e-116">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="2361e-117">[out] Флаги, указывающие, был ли проверен подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="2361e-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="2361e-118">Поддерживается следующее значение:</span><span class="sxs-lookup"><span data-stu-id="2361e-118">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="2361e-119">(0x00000001) — это значение присваивается `false` для указания, что проверка выполнена успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="2361e-119">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2361e-120">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2361e-120">Return Value</span></span>  
 `true` <span data-ttu-id="2361e-121">Если проверка прошла успешно; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="2361e-121">if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2361e-122">Требования</span><span class="sxs-lookup"><span data-stu-id="2361e-122">Requirements</span></span>  
 <span data-ttu-id="2361e-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2361e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2361e-124">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="2361e-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2361e-125">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2361e-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="2361e-126">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2361e-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2361e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2361e-127">See also</span></span>

- [<span data-ttu-id="2361e-128">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="2361e-128">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="2361e-129">Метод StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="2361e-129">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="2361e-130">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="2361e-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
