---
title: Метод ICLRStrongName::GetHashFromFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33aab5ee23a1f0d30d1f9f3079856ca30d46d2ec
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44705158"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="13f81-102">Метод ICLRStrongName::GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="13f81-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="13f81-103">Создает хэш содержимого указанного файла.</span><span class="sxs-lookup"><span data-stu-id="13f81-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13f81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13f81-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13f81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="13f81-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="13f81-106">[in] Имя файла для хеширования.</span><span class="sxs-lookup"><span data-stu-id="13f81-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="13f81-107">[in, out] Алгоритм, используемый при создании хеша.</span><span class="sxs-lookup"><span data-stu-id="13f81-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="13f81-108">Допустимыми являются алгоритмы, определенные интерфейсом Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="13f81-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="13f81-109">Если `piHashAlg` имеет значение 0, CALG_SHA 1 используется алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="13f81-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="13f81-110">[out] Массив байтов, содержащий созданный хэш.</span><span class="sxs-lookup"><span data-stu-id="13f81-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="13f81-111">[in] Максимальный размер буфера, `pbHash` указывает.</span><span class="sxs-lookup"><span data-stu-id="13f81-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="13f81-112">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="13f81-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13f81-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="13f81-113">Return Value</span></span>  
 <span data-ttu-id="13f81-114">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="13f81-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13f81-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="13f81-115">Remarks</span></span>  
 <span data-ttu-id="13f81-116">Этот метод является таким же, как [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) , за исключением того, что спецификация имени файла является ANSI, а не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="13f81-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13f81-117">Требования</span><span class="sxs-lookup"><span data-stu-id="13f81-117">Requirements</span></span>  
 <span data-ttu-id="13f81-118">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13f81-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13f81-119">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="13f81-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="13f81-120">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13f81-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13f81-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13f81-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f81-122">См. также</span><span class="sxs-lookup"><span data-stu-id="13f81-122">See Also</span></span>  
 [<span data-ttu-id="13f81-123">Метод GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="13f81-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="13f81-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="13f81-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
