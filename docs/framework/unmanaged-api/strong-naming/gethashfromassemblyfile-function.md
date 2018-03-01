---
title: "Функция GetHashFromAssemblyFile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ed5de637f8b8d51e2619ba205d89c753b27722bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="b1d83-102">Функция GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="b1d83-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="b1d83-103">Возвращает хэш файла указанную сборку, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="b1d83-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="b1d83-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="b1d83-104">This function has been deprecated.</span></span> <span data-ttu-id="b1d83-105">Используйте [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="b1d83-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1d83-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1d83-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1d83-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1d83-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="b1d83-108">[in] Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="b1d83-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="b1d83-109">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="b1d83-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="b1d83-110">Использовать нуль для хэш-алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b1d83-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="b1d83-111">[out] Буфер, возвращенный хэш.</span><span class="sxs-lookup"><span data-stu-id="b1d83-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="b1d83-112">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="b1d83-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="b1d83-113">[out] Возвращаемый размер в байтах для `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="b1d83-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1d83-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b1d83-114">Requirements</span></span>  
 <span data-ttu-id="b1d83-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1d83-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1d83-116">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b1d83-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b1d83-117">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b1d83-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b1d83-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1d83-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d83-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b1d83-119">See Also</span></span>  
 [<span data-ttu-id="b1d83-120">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="b1d83-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="b1d83-121">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="b1d83-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="b1d83-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b1d83-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
