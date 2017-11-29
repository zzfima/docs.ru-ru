---
title: "Метод ICLRStrongName::GetHashFromFile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.GetHashFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bccdb01e098015f61a29ba267da1f3ec37543fcd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="aabf4-102">Метод ICLRStrongName::GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="aabf4-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="aabf4-103">Создает хэш содержимого указанного файла.</span><span class="sxs-lookup"><span data-stu-id="aabf4-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aabf4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aabf4-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aabf4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aabf4-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="aabf4-106">[in] Имя файла для хеширования.</span><span class="sxs-lookup"><span data-stu-id="aabf4-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="aabf4-107">[in, out] Алгоритм, используемый при создании хеша.</span><span class="sxs-lookup"><span data-stu-id="aabf4-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="aabf4-108">Допустимыми являются алгоритмы, определенные интерфейсом CryptoAPI в Win32.</span><span class="sxs-lookup"><span data-stu-id="aabf4-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="aabf4-109">Если `piHashAlg` имеет значение 0, алгоритм по умолчанию используется CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="aabf4-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="aabf4-110">[out] Массив байтов, содержащий созданный хеш.</span><span class="sxs-lookup"><span data-stu-id="aabf4-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="aabf4-111">[in] Максимальный размер буфера, `pbHash` указывает.</span><span class="sxs-lookup"><span data-stu-id="aabf4-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="aabf4-112">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="aabf4-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aabf4-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="aabf4-113">Return Value</span></span>  
 <span data-ttu-id="aabf4-114">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="aabf4-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aabf4-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="aabf4-115">Remarks</span></span>  
 <span data-ttu-id="aabf4-116">Этот метод является таким же, как [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) , за исключением того, что спецификация имени файла является ANSI, а не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="aabf4-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aabf4-117">Требования</span><span class="sxs-lookup"><span data-stu-id="aabf4-117">Requirements</span></span>  
 <span data-ttu-id="aabf4-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aabf4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aabf4-119">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="aabf4-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="aabf4-120">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aabf4-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aabf4-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aabf4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aabf4-122">См. также</span><span class="sxs-lookup"><span data-stu-id="aabf4-122">See Also</span></span>  
 [<span data-ttu-id="aabf4-123">Метод GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="aabf4-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="aabf4-124">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="aabf4-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
