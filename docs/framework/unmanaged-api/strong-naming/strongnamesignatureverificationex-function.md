---
title: "Функция StrongNameSignatureVerificationEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerificationEx
helpviewer_keywords: StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0aebb53c6718a6812cbe6a6888f389c7b1a52dda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="621d7-102">Функция StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="621d7-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="621d7-103">Возвращает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="621d7-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="621d7-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="621d7-104">This function has been deprecated.</span></span> <span data-ttu-id="621d7-105">Используйте [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="621d7-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="621d7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="621d7-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="621d7-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="621d7-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="621d7-108">[in] Путь к переносимого исполняемого файла (.exe или .dll) для сборки, которую требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="621d7-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="621d7-109">[in] `true` для выполнения проверки, даже если это необходимо переопределить параметры реестра, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="621d7-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="621d7-110">[out] `true` в случае подписи строгого имени проверенного; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="621d7-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="621d7-111">`pfWasVerified`также имеет значение `false` , если проверка прошла успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="621d7-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="621d7-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="621d7-112">Return Value</span></span>  
 <span data-ttu-id="621d7-113">`true`Если проверка прошла успешно; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="621d7-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="621d7-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="621d7-114">Remarks</span></span>  
 <span data-ttu-id="621d7-115">`StrongNameSignatureVerificationEx`предоставляет возможность, аналогично [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="621d7-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="621d7-116">Однако второй набор входных данных параметра и выходные данные для `StrongNameSignatureVerificationEx` имеют тип `BOOLEAN` вместо `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="621d7-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="621d7-117">Требования</span><span class="sxs-lookup"><span data-stu-id="621d7-117">Requirements</span></span>  
 <span data-ttu-id="621d7-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="621d7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="621d7-119">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="621d7-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="621d7-120">**Библиотека:** включена как ресурс в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="621d7-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="621d7-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="621d7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="621d7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="621d7-122">See Also</span></span>  
 [<span data-ttu-id="621d7-123">Метод StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="621d7-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [<span data-ttu-id="621d7-124">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="621d7-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="621d7-125">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="621d7-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
