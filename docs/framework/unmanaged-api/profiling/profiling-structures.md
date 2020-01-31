---
title: Структуры профилирования
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: c3bbc66079e05abf494ad112b8aa0ac68e3c3e2f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868113"
---
# <a name="profiling-structures"></a><span data-ttu-id="066e4-102">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="066e4-102">Profiling Structures</span></span>
<span data-ttu-id="066e4-103">В этом разделе описаны неуправляемые структуры, которые использует API профилирования.</span><span class="sxs-lookup"><span data-stu-id="066e4-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="066e4-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="066e4-104">In This Section</span></span>  
 [<span data-ttu-id="066e4-105">Структура COR_PRF_ASSEMBLY_REFERENCE_INFO</span><span class="sxs-lookup"><span data-stu-id="066e4-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="066e4-106">Обеспечивает среду CLR информацией о ссылке на сборку, которую ей следует учитывать при выполнении обхода замыкания.</span><span class="sxs-lookup"><span data-stu-id="066e4-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="066e4-107">Структура COR_PRF_CODE_INFO</span><span class="sxs-lookup"><span data-stu-id="066e4-107">COR_PRF_CODE_INFO Structure</span></span>](cor-prf-code-info-structure.md)  
 <span data-ttu-id="066e4-108">Представляет один непрерывный блок машинного кода, хранящийся в памяти.</span><span class="sxs-lookup"><span data-stu-id="066e4-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="066e4-109">Структура COR_PRF_EX_CLAUSE_INFO</span><span class="sxs-lookup"><span data-stu-id="066e4-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="066e4-110">Хранит сведения об определенном экземпляре исключительного предложения и связанном с ним кадре.</span><span class="sxs-lookup"><span data-stu-id="066e4-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="066e4-111">Структура COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="066e4-111">COR_PRF_FUNCTION Structure</span></span>](cor-prf-function-structure.md)  
 <span data-ttu-id="066e4-112">Выдает уникальное представление функции, объединяя ее идентификатор с идентификатором перекомпилированной версии этой функции.</span><span class="sxs-lookup"><span data-stu-id="066e4-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="066e4-113">Структура COR_PRF_FUNCTION_ARGUMENT_INFO</span><span class="sxs-lookup"><span data-stu-id="066e4-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="066e4-114">Представляет аргументы функции слева направо.</span><span class="sxs-lookup"><span data-stu-id="066e4-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="066e4-115">Структура COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="066e4-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="066e4-116">Представляет блок аргументов функции, которые сохраняются в памяти последовательно слева направо.</span><span class="sxs-lookup"><span data-stu-id="066e4-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="066e4-117">Структура COR_PRF_GC_GENERATION_RANGE</span><span class="sxs-lookup"><span data-stu-id="066e4-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="066e4-118">Описывает диапазон (т. е., блок) памяти, который занимается сборкой мусора.</span><span class="sxs-lookup"><span data-stu-id="066e4-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="066e4-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="066e4-119">Related Sections</span></span>  
 <span data-ttu-id="066e4-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="066e4-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="066e4-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="066e4-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="066e4-122">Общие сведения о профилировании</span><span class="sxs-lookup"><span data-stu-id="066e4-122">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="066e4-123">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="066e4-123">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="066e4-124">Глобальные статические функции профилирования</span><span class="sxs-lookup"><span data-stu-id="066e4-124">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="066e4-125">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="066e4-125">Profiling Enumerations</span></span>](profiling-enumerations.md)
