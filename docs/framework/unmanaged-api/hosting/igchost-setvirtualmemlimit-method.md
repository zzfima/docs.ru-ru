---
title: Метод IGCHost::SetVirtualMemLimit
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5b4210bda7d41b190f1025b62132c5df896a2a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088396"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="aa02a-102">Метод IGCHost::SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="aa02a-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="aa02a-103">Задает максимальный размер виртуальной памяти среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="aa02a-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa02a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa02a-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa02a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa02a-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="aa02a-106">[in] Максимальный размер в мегабайтах, виртуальной памяти среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="aa02a-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa02a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa02a-107">Remarks</span></span>  
 <span data-ttu-id="aa02a-108">Максимальный объем виртуальной памяти среды выполнения может динамически изменяться.</span><span class="sxs-lookup"><span data-stu-id="aa02a-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa02a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="aa02a-109">Requirements</span></span>  
 <span data-ttu-id="aa02a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa02a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa02a-111">**Заголовок.** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="aa02a-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="aa02a-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa02a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="aa02a-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="aa02a-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aa02a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="aa02a-114">See also</span></span>

- [<span data-ttu-id="aa02a-115">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="aa02a-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
