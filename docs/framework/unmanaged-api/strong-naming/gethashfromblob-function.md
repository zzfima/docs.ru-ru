---
title: Функция GetHashFromBlob
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bfa846aa66345e23e085ca148c7e3f492c529f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576347"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="5a926-102">Функция GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="5a926-102">GetHashFromBlob Function</span></span>
<span data-ttu-id="5a926-103">Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="5a926-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="5a926-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="5a926-104">This function has been deprecated.</span></span> <span data-ttu-id="5a926-105">Используйте [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="5a926-105">Use the [ICLRStronName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a926-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a926-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="5a926-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a926-107">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="5a926-108">[in] Указатель на адрес блока памяти, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="5a926-108">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="5a926-109">[in] Длина в байтах блока памяти.</span><span class="sxs-lookup"><span data-stu-id="5a926-109">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="5a926-110">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="5a926-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="5a926-111">Использовать нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5a926-111">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="5a926-112">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="5a926-112">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="5a926-113">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="5a926-113">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="5a926-114">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="5a926-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a926-115">Требования</span><span class="sxs-lookup"><span data-stu-id="5a926-115">Requirements</span></span>  
 <span data-ttu-id="5a926-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a926-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a926-117">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="5a926-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5a926-118">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a926-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a926-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a926-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a926-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5a926-120">See also</span></span>
- [<span data-ttu-id="5a926-121">Метод GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="5a926-121">GetHashFromBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="5a926-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5a926-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
