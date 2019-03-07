---
title: Метод StrongNameSignatureVerificationEx2
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc8b3096bd0c60e826fec4c8daf535c3c4086630
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482786"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="707ac-102">Метод StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="707ac-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="707ac-103">Проверяет подпись сборки со строгим именем, а также сопоставление ключа ECMA фактическую клавишу.</span><span class="sxs-lookup"><span data-stu-id="707ac-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="707ac-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="707ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="707ac-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="707ac-106">[in] Путь к переносимого исполняемого файла (.exe или .dll) для сборки, которую требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="707ac-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="707ac-107">[in] `true` будет выполнить проверку подлинности, даже если это необходимо переопределить параметры реестра, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="707ac-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="707ac-108">[in] Указатель на сопоставление из фактическую клавишу ECMA открытый ключ, используемый для проверки.</span><span class="sxs-lookup"><span data-stu-id="707ac-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="707ac-109">[in] Длина открытого ключа реальных ECMA.</span><span class="sxs-lookup"><span data-stu-id="707ac-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="707ac-110">[out] `true` при подписи строгого имени проверенного; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="707ac-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="707ac-111">Этот параметр задается значение `false` Если проверка пройдена успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="707ac-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="707ac-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="707ac-112">Return Value</span></span>  
 <span data-ttu-id="707ac-113">`S_OK` Если проверка прошла успешно; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="707ac-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="707ac-114">Требования</span><span class="sxs-lookup"><span data-stu-id="707ac-114">Requirements</span></span>  
 <span data-ttu-id="707ac-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="707ac-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="707ac-116">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="707ac-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="707ac-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="707ac-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="707ac-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="707ac-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="707ac-119">См. также</span><span class="sxs-lookup"><span data-stu-id="707ac-119">See also</span></span>
- [<span data-ttu-id="707ac-120">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="707ac-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="707ac-121">Метод StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="707ac-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="707ac-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="707ac-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
