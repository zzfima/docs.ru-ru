---
title: Метод ICLRStrongName::StrongNameSignatureVerification
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9fb7098c29768821cafad6662b646eb0e08a138
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212847"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a><span data-ttu-id="75fe2-102">Метод ICLRStrongName::StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="75fe2-102">ICLRStrongName::StrongNameSignatureVerification Method</span></span>
<span data-ttu-id="75fe2-103">Получает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени, который проверяется в соответствии с заданными флагами.</span><span class="sxs-lookup"><span data-stu-id="75fe2-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75fe2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75fe2-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75fe2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="75fe2-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="75fe2-106">[in] Путь к переносимого исполняемого файла (.dll или .exe) для сборки для проверки.</span><span class="sxs-lookup"><span data-stu-id="75fe2-106">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="75fe2-107">[in] Флаги для изменения поведения проверки.</span><span class="sxs-lookup"><span data-stu-id="75fe2-107">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="75fe2-108">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="75fe2-108">The following values are supported:</span></span>  
  
-   `SN_INFLAG_FORCE_VER` <span data-ttu-id="75fe2-109">(0x00000001) — проверка производится, даже если это необходимо переопределить параметры реестра.</span><span class="sxs-lookup"><span data-stu-id="75fe2-109">(0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
-   `SN_INFLAG_INSTALL` <span data-ttu-id="75fe2-110">(0x00000002) — указывает, что это в первый раз, проверка манифеста.</span><span class="sxs-lookup"><span data-stu-id="75fe2-110">(0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
-   `SN_INFLAG_ADMIN_ACCESS` <span data-ttu-id="75fe2-111">(0x00000004) — указывает, что кэш будет предоставлять доступ только к пользователям, имеющим права администратора.</span><span class="sxs-lookup"><span data-stu-id="75fe2-111">(0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
-   `SN_INFLAG_USER_ACCESS` <span data-ttu-id="75fe2-112">(0x00000008) — указывает, что сборка будет доступен только для текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="75fe2-112">(0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
-   `SN_INFLAG_ALL_ACCESS` <span data-ttu-id="75fe2-113">(0x00000010) — указывает, что кэш будет предоставлять никаких гарантий, ограничения доступа.</span><span class="sxs-lookup"><span data-stu-id="75fe2-113">(0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
-   `SN_INFLAG_RUNTIME` <span data-ttu-id="75fe2-114">(0x80000000) — зарезервировано для внутренней отладки.</span><span class="sxs-lookup"><span data-stu-id="75fe2-114">(0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="75fe2-115">[out] Флаги, указывающие, был ли проверен подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="75fe2-115">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="75fe2-116">Поддерживается следующее значение:</span><span class="sxs-lookup"><span data-stu-id="75fe2-116">The following value is supported:</span></span>  
  
-   `SN_OUTFLAG_WAS_VERIFIED` <span data-ttu-id="75fe2-117">(0x00000001) — это значение присваивается `false` для указания, что проверка выполнена успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="75fe2-117">(0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75fe2-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="75fe2-118">Return Value</span></span>  
 `S_OK` <span data-ttu-id="75fe2-119">Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="75fe2-119">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75fe2-120">Требования</span><span class="sxs-lookup"><span data-stu-id="75fe2-120">Requirements</span></span>  
 <span data-ttu-id="75fe2-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75fe2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75fe2-122">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="75fe2-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="75fe2-123">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="75fe2-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="75fe2-124">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="75fe2-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="75fe2-125">См. также</span><span class="sxs-lookup"><span data-stu-id="75fe2-125">See also</span></span>

- [<span data-ttu-id="75fe2-126">Метод StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="75fe2-126">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="75fe2-127">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="75fe2-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
