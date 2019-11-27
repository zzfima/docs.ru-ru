---
title: Структура COR_PRF_FUNCTION_ARGUMENT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
ms.openlocfilehash: 2b01acbd617b13a64ef3dca6c8661f1e6bb067ac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447379"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="b5d4c-102">Структура COR_PRF_FUNCTION_ARGUMENT_INFO</span><span class="sxs-lookup"><span data-stu-id="b5d4c-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="b5d4c-103">Представляет аргументы функции слева направо.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5d4c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5d4c-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b5d4c-105">Члены</span><span class="sxs-lookup"><span data-stu-id="b5d4c-105">Members</span></span>  
  
|<span data-ttu-id="b5d4c-106">Член</span><span class="sxs-lookup"><span data-stu-id="b5d4c-106">Member</span></span>|<span data-ttu-id="b5d4c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b5d4c-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="b5d4c-108">Число блоков аргументов.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-108">The number of blocks of arguments.</span></span> <span data-ttu-id="b5d4c-109">То есть это значение равно количеству структур [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) в массиве `ranges`.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="b5d4c-110">Общий размер всех аргументов.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-110">The total size of all arguments.</span></span> <span data-ttu-id="b5d4c-111">Иными словами, это значение является суммой длин аргументов.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="b5d4c-112">Массив структур `COR_PRF_FUNCTION_ARGUMENT_RANGE`, каждый из которых представляет один блок аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5d4c-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="b5d4c-113">Remarks</span></span>  
 <span data-ttu-id="b5d4c-114">У функции может быть несколько аргументов.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-114">A function may have many arguments.</span></span> <span data-ttu-id="b5d4c-115">Эти аргументы могут не храниться непрерывно в памяти.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="b5d4c-116">У вас может быть блок из трех аргументов в одном месте, блок из двух аргументов в другом месте и последний блок одного аргумента в другом месте.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="b5d4c-117">Все эти аргументы используются для одной и той же функции. они просто хранятся в разных местах.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="b5d4c-118">Структура `COR_PRF_FUNCTION_ARGUMENT_INFO` представляет все аргументы одной функции.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="b5d4c-119">Он использует массив для ссылки на все блоки аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="b5d4c-120">Таким образом, для одной функции имеется одна структура `COR_PRF_FUNCTION_ARGUMENT_INFO`, которая ссылается на несколько `COR_PRF_FUNCTION_ARGUMENT_RANGE`ных структур, каждая из которых указывает на один или несколько аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="b5d4c-121">Аргументы, хранимые в регистрах, загружаются в память для построения структур.</span><span class="sxs-lookup"><span data-stu-id="b5d4c-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5d4c-122">Требования</span><span class="sxs-lookup"><span data-stu-id="b5d4c-122">Requirements</span></span>  
 <span data-ttu-id="b5d4c-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5d4c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5d4c-124">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="b5d4c-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b5d4c-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5d4c-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5d4c-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5d4c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5d4c-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="b5d4c-127">See also</span></span>

- [<span data-ttu-id="b5d4c-128">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="b5d4c-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
