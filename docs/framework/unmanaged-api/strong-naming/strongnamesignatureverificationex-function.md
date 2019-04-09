---
title: Функция StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 049b7b11473a05d74dc311ca6ee79947039b0dd1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112909"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="cb029-102">Функция StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="cb029-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="cb029-103">Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="cb029-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="cb029-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="cb029-104">This function has been deprecated.</span></span> <span data-ttu-id="cb029-105">Используйте [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="cb029-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb029-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb029-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb029-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb029-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="cb029-108">[in] Путь к переносимого исполняемого файла (.exe или .dll) для сборки, которую требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="cb029-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="cb029-109">[in] `true` будет выполнить проверку подлинности, даже если это необходимо переопределить параметры реестра, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="cb029-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="cb029-110">[out] `true` при подписи строгого имени проверенного; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="cb029-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> `pfWasVerified` <span data-ttu-id="cb029-111">задается значение `false` Если проверка пройдена успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="cb029-111">is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb029-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cb029-112">Return Value</span></span>  
 `true` <span data-ttu-id="cb029-113">Если проверка прошла успешно; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="cb029-113">if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb029-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb029-114">Remarks</span></span>  
 `StrongNameSignatureVerificationEx` <span data-ttu-id="cb029-115">предоставляет возможность, аналогичную [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="cb029-115">provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="cb029-116">Однако второй входной параметр и параметр вывода для `StrongNameSignatureVerificationEx` относятся к типу `BOOLEAN` вместо `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="cb029-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb029-117">Требования</span><span class="sxs-lookup"><span data-stu-id="cb029-117">Requirements</span></span>  
 <span data-ttu-id="cb029-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb029-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb029-119">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="cb029-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="cb029-120">**Библиотека:** Включена как ресурс в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cb029-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 **<span data-ttu-id="cb029-121">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cb029-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cb029-122">См. также</span><span class="sxs-lookup"><span data-stu-id="cb029-122">See also</span></span>

- [<span data-ttu-id="cb029-123">Метод StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="cb029-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="cb029-124">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="cb029-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="cb029-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="cb029-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
