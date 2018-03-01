---
title: "Перечисление COR_PRF_GC_GENERATION"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69eec0c2dfccacee4c54c9f2493da523812259aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcgeneration-enumeration"></a><span data-ttu-id="c48e0-102">Перечисление COR_PRF_GC_GENERATION</span><span class="sxs-lookup"><span data-stu-id="c48e0-102">COR_PRF_GC_GENERATION Enumeration</span></span>
<span data-ttu-id="c48e0-103">Идентифицирует Создание сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="c48e0-103">Identifies a garbage-collection generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c48e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c48e0-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a><span data-ttu-id="c48e0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c48e0-105">Members</span></span>  
  
|<span data-ttu-id="c48e0-106">Член</span><span class="sxs-lookup"><span data-stu-id="c48e0-106">Member</span></span>|<span data-ttu-id="c48e0-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="c48e0-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|<span data-ttu-id="c48e0-108">Объект хранится в виде поколения 0.</span><span class="sxs-lookup"><span data-stu-id="c48e0-108">The object is stored as generation 0.</span></span>|  
|`COR_PRF_GC_GEN_1`|<span data-ttu-id="c48e0-109">Объект хранится в виде поколения 1.</span><span class="sxs-lookup"><span data-stu-id="c48e0-109">The object is stored as generation 1.</span></span>|  
|`COR_PRF_GC_GEN_2`|<span data-ttu-id="c48e0-110">Объект хранится в виде поколения 2.</span><span class="sxs-lookup"><span data-stu-id="c48e0-110">The object is stored as generation 2.</span></span>|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|<span data-ttu-id="c48e0-111">Объект хранится в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="c48e0-111">The object is stored in the large-object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c48e0-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="c48e0-112">Remarks</span></span>  
 <span data-ttu-id="c48e0-113">Сборщик мусора повышает производительность управления памятью посредством деления объектов в виде поколений на основе возраста.</span><span class="sxs-lookup"><span data-stu-id="c48e0-113">The garbage collector improves memory management performance by dividing objects into generations based on age.</span></span> <span data-ttu-id="c48e0-114">Сборщик мусора в настоящее время использует три поколения с номерами от 0, 1, 2, а также специальный сегмент куч, используемый для больших объектов.</span><span class="sxs-lookup"><span data-stu-id="c48e0-114">The garbage collector currently uses three generations, numbered 0, 1, and 2, plus a special heap segment that is used for large objects.</span></span> <span data-ttu-id="c48e0-115">Объекты, размер которых превышает определенное значение, хранятся в куче больших объектов.</span><span class="sxs-lookup"><span data-stu-id="c48e0-115">Objects whose size is larger than a particular value are stored in the large-object heap.</span></span> <span data-ttu-id="c48e0-116">Другие выделенные объекты запустите относятся к поколению 0.</span><span class="sxs-lookup"><span data-stu-id="c48e0-116">Other allocated objects start out belonging to generation 0.</span></span> <span data-ttu-id="c48e0-117">Все объекты, существующие после сборки мусора в поколении 0 продвигаются в поколение 1.</span><span class="sxs-lookup"><span data-stu-id="c48e0-117">All objects that exist after garbage collection occurs in generation 0 are promoted to generation 1.</span></span> <span data-ttu-id="c48e0-118">Объекты, существующие после сборки мусора в поколении 1, переводятся в поколение 2.</span><span class="sxs-lookup"><span data-stu-id="c48e0-118">Objects that exist after garbage collection occurs in generation 1 move into generation 2.</span></span>  
  
 <span data-ttu-id="c48e0-119">Использование поколения означает, что сборщик мусора должен работать с подмножеством выделенные объекты в любой момент времени.</span><span class="sxs-lookup"><span data-stu-id="c48e0-119">The use of generations means that the garbage collector has to work with only a subset of the allocated objects at any one time.</span></span>  
  
 <span data-ttu-id="c48e0-120">`COR_PRF_GC_GENERATION` Перечисление используется методом [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="c48e0-120">The `COR_PRF_GC_GENERATION` enumeration is used by the [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c48e0-121">Требования</span><span class="sxs-lookup"><span data-stu-id="c48e0-121">Requirements</span></span>  
 <span data-ttu-id="c48e0-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c48e0-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c48e0-123">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c48e0-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c48e0-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c48e0-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c48e0-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c48e0-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c48e0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c48e0-126">See Also</span></span>  
 [<span data-ttu-id="c48e0-127">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="c48e0-127">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
