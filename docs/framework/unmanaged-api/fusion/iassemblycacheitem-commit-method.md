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
ms.openlocfilehash: f840438e175790a2b4c97302963b910f98dffb7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176569"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="2eb03-102">Метод IAssemblyCacheItem::Commit</span><span class="sxs-lookup"><span data-stu-id="2eb03-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="2eb03-103">Фиксирует ссылку кэшированной сборки на память.</span><span class="sxs-lookup"><span data-stu-id="2eb03-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eb03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2eb03-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit (  
    [in] DWORD dwFlags,
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2eb03-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2eb03-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="2eb03-106">(в) Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="2eb03-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="2eb03-107">(вне, необязательно) Значение, указывававание результата операции.</span><span class="sxs-lookup"><span data-stu-id="2eb03-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2eb03-108">Требования</span><span class="sxs-lookup"><span data-stu-id="2eb03-108">Requirements</span></span>  
 <span data-ttu-id="2eb03-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2eb03-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2eb03-110">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="2eb03-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2eb03-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2eb03-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb03-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2eb03-112">See also</span></span>

- [<span data-ttu-id="2eb03-113">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="2eb03-113">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
