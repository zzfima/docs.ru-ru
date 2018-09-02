---
title: Метод ICLRStrongName::GetHashFromBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromBlob
helpviewer_keywords:
- ICLRStrongName::GetHashFromBlob method [.NET Framework hosting]
- GetHashFromBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: f91d0f89-f356-49ac-aafb-50fad963c13d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ca958f8472d7f7e1a44ad4ab237f582f92713c3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402742"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="27b98-102">Метод ICLRStrongName::GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="27b98-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="27b98-103">Получает хэш сборки по адресу указанной области памяти, с помощью указанного алгоритма хэширования.</span><span class="sxs-lookup"><span data-stu-id="27b98-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27b98-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27b98-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="27b98-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27b98-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="27b98-106">[in] Указатель на адрес блока памяти, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="27b98-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="27b98-107">[in] Длина в байтах блока памяти.</span><span class="sxs-lookup"><span data-stu-id="27b98-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="27b98-108">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="27b98-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="27b98-109">Использовать нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="27b98-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="27b98-110">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="27b98-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="27b98-111">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="27b98-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="27b98-112">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="27b98-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27b98-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="27b98-113">Return Value</span></span>  
 <span data-ttu-id="27b98-114">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="27b98-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27b98-115">Требования</span><span class="sxs-lookup"><span data-stu-id="27b98-115">Requirements</span></span>  
 <span data-ttu-id="27b98-116">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27b98-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27b98-117">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="27b98-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="27b98-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27b98-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27b98-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27b98-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b98-120">См. также</span><span class="sxs-lookup"><span data-stu-id="27b98-120">See Also</span></span>  
 [<span data-ttu-id="27b98-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="27b98-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
