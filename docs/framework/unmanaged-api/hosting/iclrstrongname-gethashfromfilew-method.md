---
title: Метод ICLRStrongName::GetHashFromFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acfa5c138faa47c96600530ab923de102b173ed6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43803461"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a><span data-ttu-id="0da30-102">Метод ICLRStrongName::GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="0da30-102">ICLRStrongName::GetHashFromFileW Method</span></span>
<span data-ttu-id="0da30-103">Создает хэш содержимого файла, указанного строкой Юникода.</span><span class="sxs-lookup"><span data-stu-id="0da30-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0da30-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="0da30-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0da30-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="0da30-106">[in] Имя файла для хеширования Юникода.</span><span class="sxs-lookup"><span data-stu-id="0da30-106">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="0da30-107">[in, out] Алгоритм, используемый при создании хеша.</span><span class="sxs-lookup"><span data-stu-id="0da30-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="0da30-108">Допустимыми являются алгоритмы, определенные интерфейсом Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="0da30-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="0da30-109">Если `piHashAlg` имеет значение 0, CALG_SHA 1 используется алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0da30-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="0da30-110">[out] Массив байтов, содержащий созданный хэш.</span><span class="sxs-lookup"><span data-stu-id="0da30-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="0da30-111">[in] Максимальный размер буфера, на которые указывают `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="0da30-111">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="0da30-112">[out] Размер в байтах из `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="0da30-112">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0da30-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0da30-113">Return Value</span></span>  
 <span data-ttu-id="0da30-114">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="0da30-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0da30-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="0da30-115">Remarks</span></span>  
 <span data-ttu-id="0da30-116">Этот метод является таким же, как [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) , за исключением того, что спецификация имени файла является Юникода вместо ANSI.</span><span class="sxs-lookup"><span data-stu-id="0da30-116">This method is the same as the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method, except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0da30-117">Требования</span><span class="sxs-lookup"><span data-stu-id="0da30-117">Requirements</span></span>  
 <span data-ttu-id="0da30-118">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0da30-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0da30-119">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0da30-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0da30-120">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0da30-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0da30-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0da30-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0da30-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0da30-122">See Also</span></span>  
 [<span data-ttu-id="0da30-123">Метод GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="0da30-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="0da30-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="0da30-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
