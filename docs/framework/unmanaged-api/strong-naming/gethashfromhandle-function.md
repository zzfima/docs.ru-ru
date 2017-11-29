---
title: "Функция GetHashFromHandle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromHandle
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromHandle
helpviewer_keywords: GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ccb6d3b50e70d69b706f63be8a783ad6d7f7cdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="1b565-102">Функция GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="1b565-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="1b565-103">Создает хэш содержимого файла с помощью заданного дескриптора файла, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="1b565-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="1b565-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="1b565-104">This function has been deprecated.</span></span> <span data-ttu-id="1b565-105">Используйте [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="1b565-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b565-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b565-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b565-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b565-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="1b565-108">[in] Дескриптор файла для хэширования.</span><span class="sxs-lookup"><span data-stu-id="1b565-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1b565-109">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="1b565-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="1b565-110">Использовать нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1b565-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1b565-111">[out] Буфер, возвращенный хэш.</span><span class="sxs-lookup"><span data-stu-id="1b565-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1b565-112">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1b565-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1b565-113">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1b565-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b565-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1b565-114">Requirements</span></span>  
 <span data-ttu-id="1b565-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b565-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b565-116">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="1b565-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1b565-117">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b565-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1b565-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b565-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b565-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1b565-119">See Also</span></span>  
 [<span data-ttu-id="1b565-120">Метод GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="1b565-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="1b565-121">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1b565-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
