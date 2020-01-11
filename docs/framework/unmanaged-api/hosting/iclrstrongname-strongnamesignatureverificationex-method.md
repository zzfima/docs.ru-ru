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
ms.openlocfilehash: fbc9ea6aab9f0c3d9be95e6affcd04342ce4c5cc
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901078"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="7fd5f-102">Метод ICLRStrongName::StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="7fd5f-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="7fd5f-103">Возвращает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="7fd5f-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fd5f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7fd5f-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fd5f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7fd5f-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="7fd5f-106">окне Путь к переносимому исполняемому файлу (exe или DLL) для проверяемой сборки.</span><span class="sxs-lookup"><span data-stu-id="7fd5f-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="7fd5f-107">[in] `true` выполнить проверку, даже если необходимо переопределить параметры реестра; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="7fd5f-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="7fd5f-108">[out] `true`, если подпись строгого имени была проверена; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="7fd5f-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="7fd5f-109">`pfWasVerified` также имеет значение `false`, если проверка прошла успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="7fd5f-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7fd5f-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7fd5f-110">Return Value</span></span>  
 <span data-ttu-id="7fd5f-111">`S_OK`, если проверка прошла успешно; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="7fd5f-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fd5f-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="7fd5f-112">Remarks</span></span>  
 <span data-ttu-id="7fd5f-113">Метод [метод iclrstrongname:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) предоставляет такую возможность, как метод [метод iclrstrongname:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7fd5f-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="7fd5f-114">Однако второй входной параметр и выходной параметр для [метод iclrstrongname:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) относятся к типу `BOOLEAN` вместо `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="7fd5f-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fd5f-115">Требования</span><span class="sxs-lookup"><span data-stu-id="7fd5f-115">Requirements</span></span>  
 <span data-ttu-id="7fd5f-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fd5f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fd5f-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="7fd5f-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7fd5f-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7fd5f-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7fd5f-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fd5f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd5f-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="7fd5f-120">See also</span></span>

- [<span data-ttu-id="7fd5f-121">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="7fd5f-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="7fd5f-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="7fd5f-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
