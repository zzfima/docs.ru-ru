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
ms.openlocfilehash: b6fd3682290c9752125aed7b9663c6704ade25de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132336"
---
# <a name="cor_heapinfo-structure"></a><span data-ttu-id="298de-102">Структура COR_HEAPINFO</span><span class="sxs-lookup"><span data-stu-id="298de-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="298de-103">Содержит общие сведения о куче для сборки мусора и указывает, является ли она перечислимой.</span><span class="sxs-lookup"><span data-stu-id="298de-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="298de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="298de-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="298de-105">Члены</span><span class="sxs-lookup"><span data-stu-id="298de-105">Members</span></span>  
  
|<span data-ttu-id="298de-106">Член</span><span class="sxs-lookup"><span data-stu-id="298de-106">Member</span></span>|<span data-ttu-id="298de-107">Описание</span><span class="sxs-lookup"><span data-stu-id="298de-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|<span data-ttu-id="298de-108">`true`, являются ли структуры сборки мусора допустимыми и можно перечислять кучу; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="298de-108">`true` if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="298de-109">Размер указателей в байтах в целевой архитектуре.</span><span class="sxs-lookup"><span data-stu-id="298de-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="298de-110">Количество куч логической сборки мусора в процессе.</span><span class="sxs-lookup"><span data-stu-id="298de-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|<span data-ttu-id="298de-111">`TRUE`, если включена одновременная (фоновая) сборка мусора; в противном случае `FALSE`.</span><span class="sxs-lookup"><span data-stu-id="298de-111">`TRUE` if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="298de-112">Член перечисления [CorDebugGCType](cordebuggctype-enumeration.md) , указывающий, работает ли сборщик мусора на рабочей станции или сервере.</span><span class="sxs-lookup"><span data-stu-id="298de-112">A member of the [CorDebugGCType](cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="298de-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="298de-113">Remarks</span></span>  
 <span data-ttu-id="298de-114">Экземпляр структуры `COR_HEAPINFO` возвращается путем вызова метода [метод ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="298de-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="298de-115">Перед перечислением объектов в куче сборки мусора необходимо всегда проверять `areGCStructuresValid` поле, чтобы убедиться в том, что куча находится в перечислимом состоянии.</span><span class="sxs-lookup"><span data-stu-id="298de-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="298de-116">Дополнительные сведения см. в описании метода [метод ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) .</span><span class="sxs-lookup"><span data-stu-id="298de-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="298de-117">Требования</span><span class="sxs-lookup"><span data-stu-id="298de-117">Requirements</span></span>  
 <span data-ttu-id="298de-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="298de-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="298de-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="298de-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="298de-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="298de-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="298de-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="298de-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="298de-122">См. также</span><span class="sxs-lookup"><span data-stu-id="298de-122">See also</span></span>

- [<span data-ttu-id="298de-123">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="298de-123">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="298de-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="298de-124">Debugging</span></span>](index.md)
