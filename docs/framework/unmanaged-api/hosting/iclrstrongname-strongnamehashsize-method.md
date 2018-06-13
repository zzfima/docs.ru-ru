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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ebf2e0225cf497a0b89a46ecdb3e203d5b9a4cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432018"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="bcb64-102">Метод ICLRStrongName::StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="bcb64-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="bcb64-103">Возвращает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="bcb64-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcb64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcb64-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bcb64-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bcb64-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="bcb64-106">[in] Хэш-алгоритм, используемый для вычисления размера буфера.</span><span class="sxs-lookup"><span data-stu-id="bcb64-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="bcb64-107">[out] Размер возвращаемого буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="bcb64-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcb64-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bcb64-108">Return Value</span></span>  
 <span data-ttu-id="bcb64-109">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="bcb64-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcb64-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bcb64-110">Requirements</span></span>  
 <span data-ttu-id="bcb64-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcb64-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcb64-112">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="bcb64-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bcb64-113">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bcb64-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bcb64-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcb64-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcb64-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bcb64-115">See Also</span></span>  
 [<span data-ttu-id="bcb64-116">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="bcb64-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
