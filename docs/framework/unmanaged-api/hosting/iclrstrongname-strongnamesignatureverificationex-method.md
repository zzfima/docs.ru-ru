---
title: Метод ICLRStrongName::StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 933b8385a336a087f7af5245024af209582120cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436446"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="6f5db-102">Метод ICLRStrongName::StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="6f5db-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="6f5db-103">Получает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="6f5db-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f5db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f5db-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f5db-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f5db-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="6f5db-106">[in] Путь к переносимого исполняемого файла (.exe или .dll) для сборки, которую требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="6f5db-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="6f5db-107">[in] `true` для выполнения проверки, даже если это необходимо переопределить параметры реестра, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="6f5db-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="6f5db-108">[out] `true` в случае подписи строгого имени проверенного; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="6f5db-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="6f5db-109">`pfWasVerified` также имеет значение `false` , если проверка прошла успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="6f5db-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f5db-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6f5db-110">Return Value</span></span>  
 <span data-ttu-id="6f5db-111">`S_OK` Если проверка прошла успешно; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="6f5db-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f5db-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="6f5db-112">Remarks</span></span>  
 <span data-ttu-id="6f5db-113">[ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) метод предоставляет возможность, аналогично [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="6f5db-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="6f5db-114">Однако второй набор входных данных параметра и выходные данные для [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) имеют тип `BOOLEAN` вместо `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="6f5db-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f5db-115">Требования</span><span class="sxs-lookup"><span data-stu-id="6f5db-115">Requirements</span></span>  
 <span data-ttu-id="6f5db-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f5db-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f5db-117">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6f5db-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6f5db-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f5db-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f5db-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f5db-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5db-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6f5db-120">See Also</span></span>  
 [<span data-ttu-id="6f5db-121">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="6f5db-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="6f5db-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="6f5db-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
