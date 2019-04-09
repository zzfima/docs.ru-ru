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
ms.openlocfilehash: b36e1d34b874f47f1edb0e1ffe3dc2fe2d87ddcc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124297"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="35192-102">Метод ICLRStrongName::StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="35192-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="35192-103">Получает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="35192-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35192-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35192-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35192-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="35192-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="35192-106">[in] Путь к переносимого исполняемого файла (.exe или .dll) для сборки, которую требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="35192-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="35192-107">[in] `true` будет выполнить проверку подлинности, даже если это необходимо переопределить параметры реестра, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="35192-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="35192-108">[out] `true` при подписи строгого имени проверенного; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="35192-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> `pfWasVerified` <span data-ttu-id="35192-109">задается значение `false` Если проверка пройдена успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="35192-109">is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35192-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="35192-110">Return Value</span></span>  
 `S_OK` <span data-ttu-id="35192-111">Если проверка прошла успешно; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="35192-111">if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35192-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="35192-112">Remarks</span></span>  
 <span data-ttu-id="35192-113">[ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) метод предоставляет возможность, аналогичную [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="35192-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="35192-114">Однако второй входной параметр и параметр вывода для [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) относятся к типу `BOOLEAN` вместо `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="35192-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35192-115">Требования</span><span class="sxs-lookup"><span data-stu-id="35192-115">Requirements</span></span>  
 <span data-ttu-id="35192-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35192-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35192-117">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="35192-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="35192-118">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35192-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="35192-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="35192-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="35192-120">См. также</span><span class="sxs-lookup"><span data-stu-id="35192-120">See also</span></span>

- [<span data-ttu-id="35192-121">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="35192-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="35192-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="35192-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
