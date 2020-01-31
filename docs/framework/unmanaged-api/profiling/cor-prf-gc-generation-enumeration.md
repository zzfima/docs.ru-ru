---
title: Перечисление COR_PRF_GC_GENERATION
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
ms.openlocfilehash: 4eff8472e353c4e5fd2505b281cc9efc89f013fc
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867221"
---
# <a name="cor_prf_gc_generation-enumeration"></a><span data-ttu-id="39ea5-102">Перечисление COR_PRF_GC_GENERATION</span><span class="sxs-lookup"><span data-stu-id="39ea5-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="39ea5-103">Определяет создание коллекции мусора.</span><span class="sxs-lookup"><span data-stu-id="39ea5-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39ea5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39ea5-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="39ea5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="39ea5-105">Members</span></span>  
  
|<span data-ttu-id="39ea5-106">Член</span><span class="sxs-lookup"><span data-stu-id="39ea5-106">Member</span></span>|<span data-ttu-id="39ea5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="39ea5-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="39ea5-108">Объект сохраняется как поколение 0.</span><span class="sxs-lookup"><span data-stu-id="39ea5-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="39ea5-109">Объект сохраняется как поколение 1.</span><span class="sxs-lookup"><span data-stu-id="39ea5-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="39ea5-110">Объект сохраняется как поколение 2.</span><span class="sxs-lookup"><span data-stu-id="39ea5-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="39ea5-111">Объект хранится в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="39ea5-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39ea5-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="39ea5-112">Remarks</span></span>  
 <span data-ttu-id="39ea5-113">Сборщик мусора повышает производительность управления памятью, разделив объекты на поколения на основе возраста.</span><span class="sxs-lookup"><span data-stu-id="39ea5-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="39ea5-114">Сборщик мусора в настоящее время использует три поколения, нумерованный 0, 1 и 2, а также специальный сегмент кучи, используемый для больших объектов.</span><span class="sxs-lookup"><span data-stu-id="39ea5-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="39ea5-115">Объекты, размер которых больше определенного значения, хранятся в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="39ea5-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="39ea5-116">Другие выделенные объекты начинают принадлежать к поколению 0.</span><span class="sxs-lookup"><span data-stu-id="39ea5-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="39ea5-117">Все объекты, существующие после сборки мусора в поколении 0, переходят в поколение 1.</span><span class="sxs-lookup"><span data-stu-id="39ea5-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="39ea5-118">Объекты, существующие после сборки мусора в поколении 1, переходят в поколение 2.</span><span class="sxs-lookup"><span data-stu-id="39ea5-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="39ea5-119">Использование поколений означает, что сборщик мусора должен работать только с подмножеством выделенных объектов в один момент времени.</span><span class="sxs-lookup"><span data-stu-id="39ea5-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="39ea5-120">Перечисление `COR_PRF_GC_GENERATION` используется структурой [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="39ea5-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39ea5-121">Требования</span><span class="sxs-lookup"><span data-stu-id="39ea5-121">Requirements</span></span>  
 <span data-ttu-id="39ea5-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39ea5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39ea5-123">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39ea5-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39ea5-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39ea5-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39ea5-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39ea5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39ea5-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="39ea5-126">See also</span></span>

- [<span data-ttu-id="39ea5-127">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="39ea5-127">Profiling Enumerations</span></span>](profiling-enumerations.md)
