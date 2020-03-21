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
ms.openlocfilehash: ca2d00611a7530dfb0d1c2a27123947bdf69820d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179342"
---
# <a name="cor_array_layout-structure"></a><span data-ttu-id="b88c2-102">Структура COR_ARRAY_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="b88c2-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="b88c2-103">Предоставляет сведения о расположении объекта массива в памяти.</span><span class="sxs-lookup"><span data-stu-id="b88c2-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b88c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b88c2-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="b88c2-105">Члены</span><span class="sxs-lookup"><span data-stu-id="b88c2-105">Members</span></span>  
  
|<span data-ttu-id="b88c2-106">Участник</span><span class="sxs-lookup"><span data-stu-id="b88c2-106">Member</span></span>|<span data-ttu-id="b88c2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b88c2-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="b88c2-108">Идентификатор типа объектов, содержащих массив.</span><span class="sxs-lookup"><span data-stu-id="b88c2-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="b88c2-109">Значение перечисления CorElementType, которое указывает, является ли компонент ссылкой на сбор мусора, классом значений или примитивным.</span><span class="sxs-lookup"><span data-stu-id="b88c2-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="b88c2-110">Смещение до первого элемента в массиве.</span><span class="sxs-lookup"><span data-stu-id="b88c2-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="b88c2-111">Размер каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="b88c2-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="b88c2-112">Смещение с числом элементов в массиве.</span><span class="sxs-lookup"><span data-stu-id="b88c2-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="b88c2-113">Размер ранга, в байтах.</span><span class="sxs-lookup"><span data-stu-id="b88c2-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="b88c2-114">Количество званий в массиве.</span><span class="sxs-lookup"><span data-stu-id="b88c2-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="b88c2-115">Смещение, с которого начинаются ряды.</span><span class="sxs-lookup"><span data-stu-id="b88c2-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b88c2-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="b88c2-116">Remarks</span></span>  
 <span data-ttu-id="b88c2-117">Поле `rankSize` определяет размер ранга в многомерном массиве.</span><span class="sxs-lookup"><span data-stu-id="b88c2-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="b88c2-118">Это точно для одномерных массивов, а также.</span><span class="sxs-lookup"><span data-stu-id="b88c2-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="b88c2-119">Значение `numRanks` 1 для одномерного массива `N` и для многомерного массива измерений. `N`</span><span class="sxs-lookup"><span data-stu-id="b88c2-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b88c2-120">Требования</span><span class="sxs-lookup"><span data-stu-id="b88c2-120">Requirements</span></span>  
 <span data-ttu-id="b88c2-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b88c2-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b88c2-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b88c2-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b88c2-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b88c2-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b88c2-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b88c2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b88c2-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b88c2-125">See also</span></span>

- [<span data-ttu-id="b88c2-126">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="b88c2-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b88c2-127">Отладки</span><span class="sxs-lookup"><span data-stu-id="b88c2-127">Debugging</span></span>](index.md)
