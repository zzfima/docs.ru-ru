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
ms.openlocfilehash: 37659262695b63a6dd6390c62c4bb7e04fdadca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179312"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="e6e88-102">Структура COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="e6e88-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="e6e88-103">Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.</span><span class="sxs-lookup"><span data-stu-id="e6e88-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6e88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6e88-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;
    DWORD pointerSize;
    DWORD numHeaps;  
    BOOL concurrent;
    CorDebugGCType gcType;
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="e6e88-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e6e88-105">Members</span></span>  
  
|<span data-ttu-id="e6e88-106">Участник</span><span class="sxs-lookup"><span data-stu-id="e6e88-106">Member</span></span>|<span data-ttu-id="e6e88-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e6e88-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="e6e88-108">`true`если структуры сбора мусора действительны и куча может быть перечислена; в `false`противном случае, .</span><span class="sxs-lookup"><span data-stu-id="e6e88-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="e6e88-109">Размер, в байтах, указателей на целевую архитектуру.</span><span class="sxs-lookup"><span data-stu-id="e6e88-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="e6e88-110">Количество логических кучи сбора мусора в процессе.</span><span class="sxs-lookup"><span data-stu-id="e6e88-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="e6e88-111">`TRUE`если включен параллельный (фоновый) сбор мусора; в `FALSE`противном случае, .</span><span class="sxs-lookup"><span data-stu-id="e6e88-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="e6e88-112">Участник перечисления [CorDebugGCType,](cordebuggctype-enumeration.md) указывающий, работает ли сборщик мусора на рабочей станции или сервере.</span><span class="sxs-lookup"><span data-stu-id="e6e88-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6e88-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6e88-113">Remarks</span></span>  
 <span data-ttu-id="e6e88-114">Экземпляр `COR_HEAPINFO` структуры возвращается, позвонив методi [ICorDebugProcess5:GetGCHeapInformation.](icordebugprocess5-getgcheapinformation-method.md)</span><span class="sxs-lookup"><span data-stu-id="e6e88-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="e6e88-115">Прежде чем перечислять объекты на куче сбора мусора, вы всегда должны проверить `areGCStructuresValid` поле, чтобы убедиться, что куча находится в перечисленном состоянии.</span><span class="sxs-lookup"><span data-stu-id="e6e88-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="e6e88-116">Для получения дополнительной [информации](icordebugprocess5-getgcheapinformation-method.md) см.</span><span class="sxs-lookup"><span data-stu-id="e6e88-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6e88-117">Требования</span><span class="sxs-lookup"><span data-stu-id="e6e88-117">Requirements</span></span>  
 <span data-ttu-id="e6e88-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6e88-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6e88-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6e88-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6e88-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6e88-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6e88-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6e88-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6e88-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e6e88-122">See also</span></span>

- [<span data-ttu-id="e6e88-123">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="e6e88-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="e6e88-124">Отладки</span><span class="sxs-lookup"><span data-stu-id="e6e88-124">Debugging</span></span>](index.md)
