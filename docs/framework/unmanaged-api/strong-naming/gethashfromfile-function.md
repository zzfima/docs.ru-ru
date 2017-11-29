---
title: "Функция GetHashFromFile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromFile
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromFile
helpviewer_keywords: GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c8e84881822cbafa8c43c3669f7522c390d5c5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="67666-102">Функция GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="67666-102">GetHashFromFile Function</span></span>
<span data-ttu-id="67666-103">Создает хэш содержимого указанного файла.</span><span class="sxs-lookup"><span data-stu-id="67666-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="67666-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="67666-104">This function has been deprecated.</span></span> <span data-ttu-id="67666-105">Используйте [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="67666-105">Use the [ICLRStrongName::GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67666-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67666-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67666-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="67666-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="67666-108">[in] Имя файла для хеширования.</span><span class="sxs-lookup"><span data-stu-id="67666-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="67666-109">[in, out] Алгоритм, используемый при создании хеша.</span><span class="sxs-lookup"><span data-stu-id="67666-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="67666-110">Допустимыми являются алгоритмы, определенные интерфейсом CryptoAPI в Win32.</span><span class="sxs-lookup"><span data-stu-id="67666-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="67666-111">Если `piHashAlg` имеет значение 0, алгоритм по умолчанию используется CALG_SHA-1.</span><span class="sxs-lookup"><span data-stu-id="67666-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="67666-112">[out] Массив байтов, содержащий созданный хеш.</span><span class="sxs-lookup"><span data-stu-id="67666-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="67666-113">[in] Максимальный размер буфера, `pbHash` указывает.</span><span class="sxs-lookup"><span data-stu-id="67666-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="67666-114">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="67666-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67666-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="67666-115">Remarks</span></span>  
 <span data-ttu-id="67666-116">Эта функция является таким же, как [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), за исключением того, что спецификация имени файла — ANSI, а не в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="67666-116">This function is the same as [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67666-117">Требования</span><span class="sxs-lookup"><span data-stu-id="67666-117">Requirements</span></span>  
 <span data-ttu-id="67666-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67666-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67666-119">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="67666-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="67666-120">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67666-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67666-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67666-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67666-122">См. также</span><span class="sxs-lookup"><span data-stu-id="67666-122">See Also</span></span>  
 [<span data-ttu-id="67666-123">Метод GetHashFromFile</span><span class="sxs-lookup"><span data-stu-id="67666-123">GetHashFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [<span data-ttu-id="67666-124">Метод GetHashFromFileW</span><span class="sxs-lookup"><span data-stu-id="67666-124">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [<span data-ttu-id="67666-125">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="67666-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
