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
ms.openlocfilehash: c060e4883335a8318970b5fbd74bf72c9e13f5bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134864"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="61af7-102">Метод IGCHost::SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="61af7-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="61af7-103">Задает максимальный размер виртуальной памяти среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="61af7-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61af7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61af7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61af7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="61af7-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="61af7-106">окне Максимальный размер виртуальной памяти среды выполнения в мегабайтах.</span><span class="sxs-lookup"><span data-stu-id="61af7-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61af7-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="61af7-107">Remarks</span></span>  
 <span data-ttu-id="61af7-108">Максимальный размер виртуальной памяти среды выполнения можно изменить динамически.</span><span class="sxs-lookup"><span data-stu-id="61af7-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61af7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="61af7-109">Requirements</span></span>  
 <span data-ttu-id="61af7-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61af7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61af7-111">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="61af7-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="61af7-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="61af7-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61af7-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61af7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61af7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="61af7-114">See also</span></span>

- [<span data-ttu-id="61af7-115">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="61af7-115">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
