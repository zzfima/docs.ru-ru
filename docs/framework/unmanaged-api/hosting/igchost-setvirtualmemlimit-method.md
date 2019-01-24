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
ms.openlocfilehash: d38b174a7e959647a9c1f5287b8acbbcdaf5ca7b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564283"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="62b17-102">Метод IGCHost::SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="62b17-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="62b17-103">Задает максимальный размер виртуальной памяти среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="62b17-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62b17-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62b17-104">Syntax</span></span>  
  
```  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62b17-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62b17-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="62b17-106">[in] Максимальный размер в мегабайтах, виртуальной памяти среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="62b17-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62b17-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="62b17-107">Remarks</span></span>  
 <span data-ttu-id="62b17-108">Максимальный объем виртуальной памяти среды выполнения может динамически изменяться.</span><span class="sxs-lookup"><span data-stu-id="62b17-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62b17-109">Требования</span><span class="sxs-lookup"><span data-stu-id="62b17-109">Requirements</span></span>  
 <span data-ttu-id="62b17-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62b17-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62b17-111">**Заголовок.** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="62b17-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="62b17-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62b17-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62b17-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62b17-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b17-114">См. также</span><span class="sxs-lookup"><span data-stu-id="62b17-114">See also</span></span>
- [<span data-ttu-id="62b17-115">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="62b17-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
