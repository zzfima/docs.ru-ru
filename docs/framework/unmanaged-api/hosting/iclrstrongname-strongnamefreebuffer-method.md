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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d250270d139c0e930f3270f2ca1191c9c57284b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755121"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="c1660-102">Метод ICLRStrongName::StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="c1660-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="c1660-103">Освобождает память, выделенную предыдущим вызовом метода строгого имени, таких как [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), или [ ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="c1660-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1660-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1660-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1660-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1660-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="c1660-106">[in] Указатель на область памяти для освобождения.</span><span class="sxs-lookup"><span data-stu-id="c1660-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1660-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c1660-107">Return Value</span></span>  
 <span data-ttu-id="c1660-108">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="c1660-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1660-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c1660-109">Requirements</span></span>  
 <span data-ttu-id="c1660-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1660-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1660-111">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c1660-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c1660-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1660-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1660-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1660-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1660-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c1660-114">See also</span></span>

- [<span data-ttu-id="c1660-115">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c1660-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
