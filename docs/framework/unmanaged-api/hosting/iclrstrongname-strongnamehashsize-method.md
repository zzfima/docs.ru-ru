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
ms.openlocfilehash: 91b84a980e8a670b8e8b2970cfc96ddd6f4c33b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218489"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="ce3f7-102">Метод ICLRStrongName::StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="ce3f7-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="ce3f7-103">Получает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="ce3f7-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce3f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce3f7-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce3f7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce3f7-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="ce3f7-106">[in] Хэш-алгоритм, используемый для вычисления размера буфера.</span><span class="sxs-lookup"><span data-stu-id="ce3f7-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="ce3f7-107">[out] Возвращаемый размер буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="ce3f7-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce3f7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ce3f7-108">Return Value</span></span>  
 `S_OK` <span data-ttu-id="ce3f7-109">Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="ce3f7-109">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce3f7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ce3f7-110">Requirements</span></span>  
 <span data-ttu-id="ce3f7-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce3f7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce3f7-112">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ce3f7-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ce3f7-113">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce3f7-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ce3f7-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ce3f7-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ce3f7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ce3f7-115">See also</span></span>

- [<span data-ttu-id="ce3f7-116">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ce3f7-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
