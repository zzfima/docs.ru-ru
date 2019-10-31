---
title: Метод IGCHostControl::RequestVirtualMemLimit
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
ms.openlocfilehash: ccff575974093de0bf00b257cba78c509f9cbd92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134777"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="98ec5-102">Метод IGCHostControl::RequestVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="98ec5-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="98ec5-103">Запрашивает у узла изменение ограничений виртуальной памяти.</span><span class="sxs-lookup"><span data-stu-id="98ec5-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98ec5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98ec5-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98ec5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="98ec5-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="98ec5-106">окне Запрошенный размер выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="98ec5-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="98ec5-107">[вход, выход] Указатель на фактический размер выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="98ec5-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98ec5-108">Требования</span><span class="sxs-lookup"><span data-stu-id="98ec5-108">Requirements</span></span>  
 <span data-ttu-id="98ec5-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98ec5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98ec5-110">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="98ec5-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98ec5-111">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="98ec5-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98ec5-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98ec5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ec5-113">См. также</span><span class="sxs-lookup"><span data-stu-id="98ec5-113">See also</span></span>

- [<span data-ttu-id="98ec5-114">Интерфейс IGCHostControl</span><span class="sxs-lookup"><span data-stu-id="98ec5-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
