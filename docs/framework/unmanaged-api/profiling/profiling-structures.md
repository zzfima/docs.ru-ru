---
title: "Структуры профилирования"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
caps.latest.revision: "27"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 42762812c9d27073fac34b20df5011b386f05740
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="profiling-structures"></a><span data-ttu-id="43a2c-102">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="43a2c-102">Profiling Structures</span></span>
<span data-ttu-id="43a2c-103">В этом разделе описаны неуправляемые структуры, которые использует API профилирования.</span><span class="sxs-lookup"><span data-stu-id="43a2c-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43a2c-104">Содержание</span><span class="sxs-lookup"><span data-stu-id="43a2c-104">In This Section</span></span>  
 [<span data-ttu-id="43a2c-105">Структура COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="43a2c-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="43a2c-106">Обеспечивает среду CLR информацией о ссылке на сборку, которую ей следует учитывать при выполнении обхода замыкания.</span><span class="sxs-lookup"><span data-stu-id="43a2c-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="43a2c-107">Структура COR_PRF_CODE_INFO</span><span class="sxs-lookup"><span data-stu-id="43a2c-107">COR_PRF_CODE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)  
 <span data-ttu-id="43a2c-108">Представляет один непрерывный блок машинного кода, хранящийся в памяти.</span><span class="sxs-lookup"><span data-stu-id="43a2c-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="43a2c-109">Cor_prf_ex_clause_info-структура</span><span class="sxs-lookup"><span data-stu-id="43a2c-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="43a2c-110">Хранит сведения об определенном экземпляре исключительного предложения и связанном с ним кадре.</span><span class="sxs-lookup"><span data-stu-id="43a2c-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="43a2c-111">Структура COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="43a2c-111">COR_PRF_FUNCTION Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-structure.md)  
 <span data-ttu-id="43a2c-112">Выдает уникальное представление функции, объединяя ее идентификатор с идентификатором перекомпилированной версии этой функции.</span><span class="sxs-lookup"><span data-stu-id="43a2c-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="43a2c-113">COR_PRF_FUNCTION_ARGUMENT_INFO-структура</span><span class="sxs-lookup"><span data-stu-id="43a2c-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="43a2c-114">Представляет аргументы функции слева направо.</span><span class="sxs-lookup"><span data-stu-id="43a2c-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="43a2c-115">Структура COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="43a2c-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="43a2c-116">Представляет блок аргументов функции, которые сохраняются в памяти последовательно слева направо.</span><span class="sxs-lookup"><span data-stu-id="43a2c-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="43a2c-117">COR_PRF_GC_GENERATION_RANGE-структура</span><span class="sxs-lookup"><span data-stu-id="43a2c-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="43a2c-118">Описывает диапазон (т. е., блок) памяти, который занимается сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="43a2c-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="43a2c-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="43a2c-119">Related Sections</span></span>  
 <span data-ttu-id="43a2c-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="43a2c-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="43a2c-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="43a2c-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="43a2c-122">Общие сведения о профилировании</span><span class="sxs-lookup"><span data-stu-id="43a2c-122">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="43a2c-123">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="43a2c-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="43a2c-124">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="43a2c-124">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="43a2c-125">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="43a2c-125">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
