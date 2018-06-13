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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fbc41ca1366b412c37d6af09e90e3f1b042ba21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449989"
---
# <a name="corprffunctionargumentinfo-structure"></a><span data-ttu-id="0ea80-102">Структура COR_PRF_FUNCTION_ARGUMENT_INFO</span><span class="sxs-lookup"><span data-stu-id="0ea80-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="0ea80-103">Представляет аргументы функции слева направо.</span><span class="sxs-lookup"><span data-stu-id="0ea80-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ea80-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ea80-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="0ea80-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0ea80-105">Members</span></span>  
  
|<span data-ttu-id="0ea80-106">Член</span><span class="sxs-lookup"><span data-stu-id="0ea80-106">Member</span></span>|<span data-ttu-id="0ea80-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0ea80-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="0ea80-108">Число блоков аргументов.</span><span class="sxs-lookup"><span data-stu-id="0ea80-108">The number of blocks of arguments.</span></span> <span data-ttu-id="0ea80-109">Это значение является число [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) структур в `ranges` массива.</span><span class="sxs-lookup"><span data-stu-id="0ea80-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="0ea80-110">Общий размер всех аргументов.</span><span class="sxs-lookup"><span data-stu-id="0ea80-110">The total size of all arguments.</span></span> <span data-ttu-id="0ea80-111">Другими словами это значение является суммой длин аргументов.</span><span class="sxs-lookup"><span data-stu-id="0ea80-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="0ea80-112">Массив `COR_PRF_FUNCTION_ARGUMENT_RANGE` структуры, каждый из которых представляет один блок аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="0ea80-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ea80-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ea80-113">Remarks</span></span>  
 <span data-ttu-id="0ea80-114">Функция может иметь много аргументов.</span><span class="sxs-lookup"><span data-stu-id="0ea80-114">A function may have many arguments.</span></span> <span data-ttu-id="0ea80-115">Эти аргументы могут храниться в памяти не последовательно.</span><span class="sxs-lookup"><span data-stu-id="0ea80-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="0ea80-116">Возможно, блок из трех аргументов в одном месте, блок из двух аргументов в другом месте и еще один блок из одного аргумента в другом месте.</span><span class="sxs-lookup"><span data-stu-id="0ea80-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="0ea80-117">Эти аргументы являются все для одной и той же функции; они просто сохраняются в разных местах.</span><span class="sxs-lookup"><span data-stu-id="0ea80-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="0ea80-118">`COR_PRF_FUNCTION_ARGUMENT_INFO` Структура представляет все аргументы одной функции.</span><span class="sxs-lookup"><span data-stu-id="0ea80-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="0ea80-119">Она использует массив для ссылки на все блоки аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="0ea80-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="0ea80-120">Таким образом, для одной функции, у вас есть один `COR_PRF_FUNCTION_ARGUMENT_INFO` структуру, которая ссылается на несколько `COR_PRF_FUNCTION_ARGUMENT_RANGE` структуры, каждый из которых указывает на один или несколько аргументов функции.</span><span class="sxs-lookup"><span data-stu-id="0ea80-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="0ea80-121">Аргументы, которые хранятся в регистрах, распределяются в памяти для построения структур.</span><span class="sxs-lookup"><span data-stu-id="0ea80-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ea80-122">Требования</span><span class="sxs-lookup"><span data-stu-id="0ea80-122">Requirements</span></span>  
 <span data-ttu-id="0ea80-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ea80-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ea80-124">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="0ea80-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="0ea80-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ea80-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ea80-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ea80-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea80-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0ea80-127">See Also</span></span>  
 [<span data-ttu-id="0ea80-128">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="0ea80-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
