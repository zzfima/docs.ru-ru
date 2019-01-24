---
title: Метод IAssemblyCacheItem::Commit
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.Commit
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b39cdec6d5cc10256c2911c98f94b7565295408
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538002"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="bb60a-102">Метод IAssemblyCacheItem::Commit</span><span class="sxs-lookup"><span data-stu-id="bb60a-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="bb60a-103">Фиксирует ссылки на сборку, кэшированных в памяти.</span><span class="sxs-lookup"><span data-stu-id="bb60a-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb60a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb60a-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb60a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb60a-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="bb60a-106">[in] Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="bb60a-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="bb60a-107">[out, optional] Значение, указывающее результат операции.</span><span class="sxs-lookup"><span data-stu-id="bb60a-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb60a-108">Требования</span><span class="sxs-lookup"><span data-stu-id="bb60a-108">Requirements</span></span>  
 <span data-ttu-id="bb60a-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb60a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb60a-110">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="bb60a-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="bb60a-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb60a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb60a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bb60a-112">See also</span></span>
- [<span data-ttu-id="bb60a-113">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="bb60a-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
