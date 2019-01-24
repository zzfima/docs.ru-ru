---
title: Структура COR_ARRAY_LAYOUT
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6fee91146e99ba1f63ecafcbbdaae9d42675848
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731144"
---
# <a name="corarraylayout-structure"></a><span data-ttu-id="0052a-102">Структура COR_ARRAY_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="0052a-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="0052a-103">Предоставляет сведения о расположении объекта массива в памяти.</span><span class="sxs-lookup"><span data-stu-id="0052a-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0052a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0052a-104">Syntax</span></span>  
  
```  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;   
    ULONG32 rankSize;   
    ULONG32 numRanks;   
    ULONG32 rankOffset;   
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="0052a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0052a-105">Members</span></span>  
  
|<span data-ttu-id="0052a-106">Член</span><span class="sxs-lookup"><span data-stu-id="0052a-106">Member</span></span>|<span data-ttu-id="0052a-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0052a-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="0052a-108">Идентификатор для типа объектов, содержащихся в массиве.</span><span class="sxs-lookup"><span data-stu-id="0052a-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="0052a-109">CorElementType значение перечисления, указывающее, находится ли компонент ссылка на сборку мусора, класс значений или примитивный тип.</span><span class="sxs-lookup"><span data-stu-id="0052a-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="0052a-110">Смещение до первого элемента в массиве.</span><span class="sxs-lookup"><span data-stu-id="0052a-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="0052a-111">Размер каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="0052a-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="0052a-112">Смещение, в число элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="0052a-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="0052a-113">Размер ранг, в байтах.</span><span class="sxs-lookup"><span data-stu-id="0052a-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="0052a-114">Число ранги в массиве.</span><span class="sxs-lookup"><span data-stu-id="0052a-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="0052a-115">Смещение, с которой начинается ранги.</span><span class="sxs-lookup"><span data-stu-id="0052a-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0052a-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="0052a-116">Remarks</span></span>  
 <span data-ttu-id="0052a-117">`rankSize` Поле указывает размер ранжирования в многомерный массив.</span><span class="sxs-lookup"><span data-stu-id="0052a-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="0052a-118">Оно является точным для также одномерные массивы.</span><span class="sxs-lookup"><span data-stu-id="0052a-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="0052a-119">Значение `numRanks` равно 1 для одномерного массива и `N` для многомерный массив `N` измерений.</span><span class="sxs-lookup"><span data-stu-id="0052a-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0052a-120">Требования</span><span class="sxs-lookup"><span data-stu-id="0052a-120">Requirements</span></span>  
 <span data-ttu-id="0052a-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0052a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0052a-122">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0052a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0052a-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0052a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0052a-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0052a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0052a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0052a-125">See also</span></span>
- [<span data-ttu-id="0052a-126">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="0052a-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="0052a-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="0052a-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
