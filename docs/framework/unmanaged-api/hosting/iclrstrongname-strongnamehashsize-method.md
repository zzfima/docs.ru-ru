---
title: Метод ICLRStrongName::StrongNameHashSize
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
ms.openlocfilehash: abcae4a89dc2ee3895d6ff246fa7358a5fe2f06e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901117"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="d7945-102">Метод ICLRStrongName::StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="d7945-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="d7945-103">Получает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="d7945-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7945-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7945-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7945-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7945-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="d7945-106">окне Хэш-алгоритм, используемый для вычисления размера буфера.</span><span class="sxs-lookup"><span data-stu-id="d7945-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="d7945-107">заполняет Размер возвращенного буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="d7945-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7945-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d7945-108">Return Value</span></span>  
 <span data-ttu-id="d7945-109">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="d7945-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7945-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d7945-110">Requirements</span></span>  
 <span data-ttu-id="d7945-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7945-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7945-112">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="d7945-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d7945-113">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d7945-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7945-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7945-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7945-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="d7945-115">See also</span></span>

- [<span data-ttu-id="d7945-116">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d7945-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
