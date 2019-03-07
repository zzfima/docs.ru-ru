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
ms.openlocfilehash: 34e8bcdda30c890fc40bab206bc6757afc073177
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475207"
---
# <a name="iclrstrongnamegethashfromblob-method"></a><span data-ttu-id="47f60-102">Метод ICLRStrongName::GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="47f60-102">ICLRStrongName::GetHashFromBlob Method</span></span>
<span data-ttu-id="47f60-103">Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="47f60-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47f60-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47f60-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="47f60-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="47f60-105">Parameters</span></span>  
 `pbBlob`  
 <span data-ttu-id="47f60-106">[in] Указатель на адрес блока памяти, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="47f60-106">[in] A pointer to the address of the memory block to be hashed.</span></span>  
  
 `cchBlob`  
 <span data-ttu-id="47f60-107">[in] Длина в байтах блока памяти.</span><span class="sxs-lookup"><span data-stu-id="47f60-107">[in] The length, in bytes, of the memory block.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="47f60-108">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="47f60-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="47f60-109">Использовать нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="47f60-109">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="47f60-110">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="47f60-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="47f60-111">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="47f60-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="47f60-112">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="47f60-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47f60-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="47f60-113">Return Value</span></span>  
 <span data-ttu-id="47f60-114">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="47f60-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47f60-115">Требования</span><span class="sxs-lookup"><span data-stu-id="47f60-115">Requirements</span></span>  
 <span data-ttu-id="47f60-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47f60-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47f60-117">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="47f60-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="47f60-118">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47f60-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47f60-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47f60-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f60-120">См. также</span><span class="sxs-lookup"><span data-stu-id="47f60-120">See also</span></span>
- [<span data-ttu-id="47f60-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="47f60-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
