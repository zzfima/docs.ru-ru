---
title: "Метод StrongNameSignatureVerificationEx2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location: mscoree.dll
api_type: COM
f1_keywords: StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 823eac67a53c4534a12122b118ac46bb91530d1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="479bf-102">Метод StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="479bf-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="479bf-103">Проверяет подпись сборки строгим именем, а также сопоставление ключ ECMA действительный ключ.</span><span class="sxs-lookup"><span data-stu-id="479bf-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="479bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="479bf-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="479bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="479bf-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="479bf-106">[in] Путь к переносимого исполняемого файла (.exe или .dll) для сборки, которую требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="479bf-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="479bf-107">[in] `true` для выполнения проверки, даже если это необходимо переопределить параметры реестра, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="479bf-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="479bf-108">[in] Указатель сопоставление из действительный ключ ECMA открытый ключ, используемый для проверки.</span><span class="sxs-lookup"><span data-stu-id="479bf-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="479bf-109">[in] Длина действительный открытый ключ ECMA.</span><span class="sxs-lookup"><span data-stu-id="479bf-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="479bf-110">[out] `true` в случае подписи строгого имени проверенного; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="479bf-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="479bf-111">Этот параметр также имеет значение `false` , если проверка прошла успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="479bf-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="479bf-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="479bf-112">Return Value</span></span>  
 <span data-ttu-id="479bf-113">`S_OK`Если проверка прошла успешно; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="479bf-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="479bf-114">Требования</span><span class="sxs-lookup"><span data-stu-id="479bf-114">Requirements</span></span>  
 <span data-ttu-id="479bf-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="479bf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="479bf-116">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="479bf-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="479bf-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="479bf-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="479bf-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="479bf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479bf-119">См. также</span><span class="sxs-lookup"><span data-stu-id="479bf-119">See Also</span></span>  
 [<span data-ttu-id="479bf-120">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="479bf-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="479bf-121">Метод StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="479bf-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="479bf-122">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="479bf-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
