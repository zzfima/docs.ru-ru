---
title: "Функция GetHashFromBlob"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromBlob
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromBlob
helpviewer_keywords: GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4564ea36ed8dd4c5de0d1633ba791b47bc2a01b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="6af48-102">Функция GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="6af48-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="6af48-103">Возвращает хэш сборки по указанному адресу памяти, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="6af48-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="6af48-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="6af48-104">This function has been deprecated.</span></span> <span data-ttu-id="6af48-105">Используйте [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="6af48-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6af48-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6af48-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromBlob (  
    [in]  BYTE    *pbBlob,  
    [in]  DWORD   cchBlob,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE    *pbHash,  
    [in]  DWORD   cchHash,  
    [out] DWORD   *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6af48-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="6af48-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="6af48-108">[in] Указатель на адрес блока памяти, предназначенные для хэширования.</span><span class="sxs-lookup"><span data-stu-id="6af48-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="6af48-109">[in] Длина блока памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="6af48-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="6af48-110">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="6af48-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="6af48-111">Использовать нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6af48-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="6af48-112">[out] Буфер, возвращенный хэш.</span><span class="sxs-lookup"><span data-stu-id="6af48-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="6af48-113">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="6af48-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="6af48-114">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="6af48-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6af48-115">Требования</span><span class="sxs-lookup"><span data-stu-id="6af48-115">Requirements</span></span>  
 <span data-ttu-id="6af48-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6af48-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6af48-117">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="6af48-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6af48-118">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6af48-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6af48-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6af48-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af48-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6af48-120">See Also</span></span>  
 [<span data-ttu-id="6af48-121">Метод GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="6af48-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)  
 [<span data-ttu-id="6af48-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="6af48-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
