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
ms.openlocfilehash: cf8d6b7e45c0012d223173c85a92fac4fb044c6c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141411"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="e6456-102">Метод StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="e6456-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="e6456-103">Проверяет подпись сборки со строгим именем и обеспечивает сопоставление ключа ECMA с реальным ключом.</span><span class="sxs-lookup"><span data-stu-id="e6456-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6456-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6456-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6456-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6456-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="e6456-106">окне Путь к переносимому исполняемому файлу (exe или DLL) для проверяемой сборки.</span><span class="sxs-lookup"><span data-stu-id="e6456-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="e6456-107">[in] `true` выполнить проверку, даже если необходимо переопределить параметры реестра; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="e6456-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="e6456-108">окне Указатель на сопоставление открытого ключа ECMA с реальным ключом, используемым для проверки.</span><span class="sxs-lookup"><span data-stu-id="e6456-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="e6456-109">окне Длина действительного открытого ключа ECMA.</span><span class="sxs-lookup"><span data-stu-id="e6456-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="e6456-110">[out] `true`, если подпись строгого имени была проверена; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="e6456-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="e6456-111">Этот параметр также имеет значение `false`, если проверка прошла успешно из-за параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="e6456-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6456-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e6456-112">Return Value</span></span>  
 <span data-ttu-id="e6456-113">`S_OK`, если проверка прошла успешно; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) для списка).</span><span class="sxs-lookup"><span data-stu-id="e6456-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6456-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e6456-114">Requirements</span></span>  
 <span data-ttu-id="e6456-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6456-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6456-116">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="e6456-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e6456-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e6456-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6456-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6456-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6456-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e6456-119">See also</span></span>

- [<span data-ttu-id="e6456-120">Метод StrongNameSignatureVerification</span><span class="sxs-lookup"><span data-stu-id="e6456-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="e6456-121">Метод StrongNameSignatureVerificationEx</span><span class="sxs-lookup"><span data-stu-id="e6456-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="e6456-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e6456-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
