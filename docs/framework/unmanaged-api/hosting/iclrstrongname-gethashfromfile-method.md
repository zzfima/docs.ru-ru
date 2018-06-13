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
ms.openlocfilehash: 94d17b6c8150744d4beca5e74827d235f81af08c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433319"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="84719-102">Метод ICLRStrongName::GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="84719-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="84719-103">Создает хэш содержимого указанного файла.</span><span class="sxs-lookup"><span data-stu-id="84719-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84719-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="84719-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84719-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="84719-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="84719-106">[in] Имя файла для хеширования.</span><span class="sxs-lookup"><span data-stu-id="84719-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="84719-107">[in, out] Алгоритм, используемый при создании хеша.</span><span class="sxs-lookup"><span data-stu-id="84719-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="84719-108">Допустимыми являются алгоритмы, определенные интерфейсом CryptoAPI в Win32.</span><span class="sxs-lookup"><span data-stu-id="84719-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="84719-109">Если `piHashAlg` имеет значение 0, алгоритм по умолчанию используется CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="84719-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="84719-110">[out] Массив байтов, содержащий созданный хеш.</span><span class="sxs-lookup"><span data-stu-id="84719-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="84719-111">[in] Максимальный размер буфера, `pbHash` указывает.</span><span class="sxs-lookup"><span data-stu-id="84719-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="84719-112">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="84719-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84719-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="84719-113">Return Value</span></span>  
 <span data-ttu-id="84719-114">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="84719-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84719-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="84719-115">Remarks</span></span>  
 <span data-ttu-id="84719-116">Этот метод является таким же, как [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) , за исключением того, что спецификация имени файла является ANSI, а не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="84719-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84719-117">Требования</span><span class="sxs-lookup"><span data-stu-id="84719-117">Requirements</span></span>  
 <span data-ttu-id="84719-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84719-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84719-119">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="84719-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="84719-120">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="84719-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84719-121">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84719-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84719-122">См. также</span><span class="sxs-lookup"><span data-stu-id="84719-122">See Also</span></span>  
 [<span data-ttu-id="84719-123">Метод GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="84719-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="84719-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="84719-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
