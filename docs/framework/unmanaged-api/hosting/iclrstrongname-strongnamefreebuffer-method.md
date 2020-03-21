---
title: Метод ICLRStrongName::StrongNameFreeBuffer
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameFreeBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameFreeBuffer method [.NET Framework hosting]
ms.assetid: 6148c508-bd1d-4a37-85c3-06ecb09cc857
topic_type:
- apiref
ms.openlocfilehash: a08aef367f300f7617e3bc9dc721b904f6f33626
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176361"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="f249f-102">Метод ICLRStrongName::StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="f249f-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="f249f-103">Освобождает память, которая была выделена с предыдущим вызовом на сильный метод имени, такие как [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameToToFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), или [ICLRStrongName::StrongNameSignature.](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)</span><span class="sxs-lookup"><span data-stu-id="f249f-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f249f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f249f-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f249f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f249f-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="f249f-106">(в) Указатель на память, чтобы освободить.</span><span class="sxs-lookup"><span data-stu-id="f249f-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f249f-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f249f-107">Return Value</span></span>  
 <span data-ttu-id="f249f-108">`S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="f249f-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f249f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f249f-109">Requirements</span></span>  
 <span data-ttu-id="f249f-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f249f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f249f-111">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f249f-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f249f-112">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f249f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f249f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f249f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f249f-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f249f-114">See also</span></span>

- [<span data-ttu-id="f249f-115">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f249f-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
