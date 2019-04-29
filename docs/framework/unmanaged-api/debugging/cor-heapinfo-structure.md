---
title: Структура COR_HEAPINFO
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23bda470b8b5812b567081ba268ad503ac39ecaa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609487"
---
# <a name="corheapinfo-structure"></a><span data-ttu-id="ac360-102">Структура COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="ac360-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="ac360-103">Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.</span><span class="sxs-lookup"><span data-stu-id="ac360-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac360-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac360-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="ac360-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ac360-105">Members</span></span>  
  
|<span data-ttu-id="ac360-106">Член</span><span class="sxs-lookup"><span data-stu-id="ac360-106">Member</span></span>|<span data-ttu-id="ac360-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ac360-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="ac360-108">`true` Если структурами для сборки мусора являются допустимыми и могут быть перечислены кучи; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="ac360-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="ac360-109">Размер в байтах, указателей в целевой архитектуре.</span><span class="sxs-lookup"><span data-stu-id="ac360-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="ac360-110">Количество логических мусора кучи в процессе.</span><span class="sxs-lookup"><span data-stu-id="ac360-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="ac360-111">`TRUE` Если параллельный сбор мусора (фон) включена; в противном случае `FALSE`.</span><span class="sxs-lookup"><span data-stu-id="ac360-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="ac360-112">Является членом [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) перечисление, указывающее, выполняется ли сборщик мусора на рабочей станции или сервера.</span><span class="sxs-lookup"><span data-stu-id="ac360-112">A member of the [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac360-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac360-113">Remarks</span></span>  
 <span data-ttu-id="ac360-114">Экземпляр `COR_HEAPINFO` структура возвращается путем вызова [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="ac360-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="ac360-115">Прежде чем перечисление объектов в куче сбора мусора, всегда необходимо проверять `areGCStructuresValid` чтобы убедиться, что кучи находится в состоянии перечисляемый.</span><span class="sxs-lookup"><span data-stu-id="ac360-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="ac360-116">Дополнительные сведения см. в разделе [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="ac360-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac360-117">Требования</span><span class="sxs-lookup"><span data-stu-id="ac360-117">Requirements</span></span>  
 <span data-ttu-id="ac360-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac360-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac360-119">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac360-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac360-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac360-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac360-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac360-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac360-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ac360-122">See also</span></span>

- [<span data-ttu-id="ac360-123">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="ac360-123">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="ac360-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="ac360-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
