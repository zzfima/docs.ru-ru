---
title: Функция GetHashFromFile
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e81ed965fcd5c293378bcffd943eecff35257013
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572673"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="1c272-102">Функция GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="1c272-102">GetHashFromFile Function</span></span>
<span data-ttu-id="1c272-103">Создает хэш содержимого указанного файла.</span><span class="sxs-lookup"><span data-stu-id="1c272-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="1c272-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="1c272-104">This function has been deprecated.</span></span> <span data-ttu-id="1c272-105">Используйте [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="1c272-105">Use the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c272-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c272-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c272-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c272-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="1c272-108">[in] Имя файла для хеширования.</span><span class="sxs-lookup"><span data-stu-id="1c272-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1c272-109">[in, out] Алгоритм, используемый при создании хеша.</span><span class="sxs-lookup"><span data-stu-id="1c272-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="1c272-110">Допустимыми являются алгоритмы, определенные интерфейсом Win32 CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="1c272-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="1c272-111">Если `piHashAlg` имеет значение 0, CALG_SHA 1 используется алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1c272-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1c272-112">[out] Массив байтов, содержащий созданный хэш.</span><span class="sxs-lookup"><span data-stu-id="1c272-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1c272-113">[in] Максимальный размер буфера, `pbHash` указывает.</span><span class="sxs-lookup"><span data-stu-id="1c272-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1c272-114">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1c272-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c272-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c272-115">Remarks</span></span>  
 <span data-ttu-id="1c272-116">Эта функция совпадает со значением [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), за исключением того, что спецификация имени файла — ANSI, а не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="1c272-116">This function is the same as [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c272-117">Требования</span><span class="sxs-lookup"><span data-stu-id="1c272-117">Requirements</span></span>  
 <span data-ttu-id="1c272-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c272-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c272-119">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="1c272-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1c272-120">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c272-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c272-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c272-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c272-122">См. также</span><span class="sxs-lookup"><span data-stu-id="1c272-122">See also</span></span>
- [<span data-ttu-id="1c272-123">Метод GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="1c272-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="1c272-124">Метод GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="1c272-124">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="1c272-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="1c272-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
