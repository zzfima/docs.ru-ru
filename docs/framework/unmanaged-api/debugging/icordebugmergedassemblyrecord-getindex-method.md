---
title: "Метод ICorDebugMergedAssemblyRecord::GetIndex"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54ff8d6935f5507ab02d9d566921cb7f8a890bb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="89f47-102">Метод ICorDebugMergedAssemblyRecord::GetIndex</span><span class="sxs-lookup"><span data-stu-id="89f47-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="89f47-103">Возвращает индекс префикса сборки.</span><span class="sxs-lookup"><span data-stu-id="89f47-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f47-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89f47-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89f47-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="89f47-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="89f47-106">[out] Указатель на индекс префикса.</span><span class="sxs-lookup"><span data-stu-id="89f47-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89f47-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="89f47-107">Remarks</span></span>  
 <span data-ttu-id="89f47-108">Индекс префикса используется для предотвращения конфликтов имен в типе объединенных метаданных.</span><span class="sxs-lookup"><span data-stu-id="89f47-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89f47-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="89f47-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89f47-110">Требования</span><span class="sxs-lookup"><span data-stu-id="89f47-110">Requirements</span></span>  
 <span data-ttu-id="89f47-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89f47-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89f47-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89f47-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89f47-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89f47-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89f47-114">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89f47-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89f47-115">См. также</span><span class="sxs-lookup"><span data-stu-id="89f47-115">See Also</span></span>  
 [<span data-ttu-id="89f47-116">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="89f47-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="89f47-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="89f47-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
