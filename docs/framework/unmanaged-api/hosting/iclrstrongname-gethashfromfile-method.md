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
ms.openlocfilehash: 9561d383e7c134230b8664329b59aec23e487124
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899580"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="f616c-102">Метод ICLRStrongName::GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="f616c-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="f616c-103">Создает хэш содержимого указанного файла.</span><span class="sxs-lookup"><span data-stu-id="f616c-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f616c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f616c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f616c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f616c-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="f616c-106">окне Имя файла для хэширования.</span><span class="sxs-lookup"><span data-stu-id="f616c-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f616c-107">[вход, выход] Алгоритм, используемый при формировании хэша.</span><span class="sxs-lookup"><span data-stu-id="f616c-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="f616c-108">Допустимыми являются алгоритмы, определяемые интерфейсом Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="f616c-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="f616c-109">Если `piHashAlg` имеет значение 0, используется алгоритм по умолчанию CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="f616c-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f616c-110">заполняет Массив байтов, содержащий созданный хэш.</span><span class="sxs-lookup"><span data-stu-id="f616c-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f616c-111">окне Максимальный размер буфера, на который `pbHash` указывает.</span><span class="sxs-lookup"><span data-stu-id="f616c-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f616c-112">заполняет Размер возвращаемого `pbHash`в байтах.</span><span class="sxs-lookup"><span data-stu-id="f616c-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f616c-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f616c-113">Return Value</span></span>  
 <span data-ttu-id="f616c-114">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="f616c-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f616c-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="f616c-115">Remarks</span></span>  
 <span data-ttu-id="f616c-116">Этот метод аналогичен методу [метод iclrstrongname:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) , за исключением того, что спецификация имени файла является ANSI, а не Unicode.</span><span class="sxs-lookup"><span data-stu-id="f616c-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f616c-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f616c-117">Requirements</span></span>  
 <span data-ttu-id="f616c-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f616c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f616c-119">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="f616c-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f616c-120">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f616c-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f616c-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f616c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f616c-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="f616c-122">See also</span></span>

- [<span data-ttu-id="f616c-123">Метод GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="f616c-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="f616c-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f616c-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
