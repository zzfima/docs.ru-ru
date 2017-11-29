---
title: "Структура COR_HEAPINFO"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_HEAPINFO
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_HEAPINFO
helpviewer_keywords: COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e316b964e3e983f50b81228709623e162529b05c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="corheapinfo-structure"></a><span data-ttu-id="12128-102">Структура COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="12128-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="12128-103">Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.</span><span class="sxs-lookup"><span data-stu-id="12128-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12128-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12128-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="12128-105">Члены</span><span class="sxs-lookup"><span data-stu-id="12128-105">Members</span></span>  
  
|<span data-ttu-id="12128-106">Член</span><span class="sxs-lookup"><span data-stu-id="12128-106">Member</span></span>|<span data-ttu-id="12128-107">Описание</span><span class="sxs-lookup"><span data-stu-id="12128-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="12128-108">`true`Если структурами для сборки мусора являются допустимыми и могут быть перечислены кучи; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="12128-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="12128-109">Размер в байтах указателей в целевой архитектуре.</span><span class="sxs-lookup"><span data-stu-id="12128-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="12128-110">Количество логических мусора кучи в процессе.</span><span class="sxs-lookup"><span data-stu-id="12128-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="12128-111">`TRUE`Если параллельной сборки мусора (фонового) включена; в противном случае `FALSE`.</span><span class="sxs-lookup"><span data-stu-id="12128-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="12128-112">Член [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) перечисление, указывающее, выполняется ли сборщик мусора на рабочей станции или сервере.</span><span class="sxs-lookup"><span data-stu-id="12128-112">A member of the [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12128-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="12128-113">Remarks</span></span>  
 <span data-ttu-id="12128-114">Экземпляр `COR_HEAPINFO` структуры, возвращенный при вызове [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="12128-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="12128-115">Перед перечисление объектов в куче сбора мусора, необходимо всегда проверять `areGCStructuresValid` поле, чтобы убедитесь, что в состоянии перечисляемую кучи.</span><span class="sxs-lookup"><span data-stu-id="12128-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="12128-116">Дополнительные сведения см. в разделе [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="12128-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12128-117">Требования</span><span class="sxs-lookup"><span data-stu-id="12128-117">Requirements</span></span>  
 <span data-ttu-id="12128-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12128-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12128-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12128-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12128-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12128-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12128-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12128-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12128-122">См. также</span><span class="sxs-lookup"><span data-stu-id="12128-122">See Also</span></span>  
 [<span data-ttu-id="12128-123">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="12128-123">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="12128-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="12128-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
