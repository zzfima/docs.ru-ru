---
title: Интерфейс IMethodMalloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee825da1f3f0fd72a3b47b48783f0f344af99b65
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077788"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="13487-102">Интерфейс IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="13487-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="13487-103">Предоставляет метод для выделения памяти для нового тела функции промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="13487-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13487-104">`IMethodMalloc` Интерфейс является простым средством выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="13487-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="13487-105">Можно выделить память, но не освободит его.</span><span class="sxs-lookup"><span data-stu-id="13487-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13487-106">Методы</span><span class="sxs-lookup"><span data-stu-id="13487-106">Methods</span></span>  
  
|<span data-ttu-id="13487-107">Метод</span><span class="sxs-lookup"><span data-stu-id="13487-107">Method</span></span>|<span data-ttu-id="13487-108">Описание</span><span class="sxs-lookup"><span data-stu-id="13487-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13487-109">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="13487-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="13487-110">Пытается выделить указанный объем памяти для нового тела функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="13487-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13487-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="13487-111">Remarks</span></span>  
 <span data-ttu-id="13487-112">Каждый распределитель конкретного модуля и гарантирует, что тело функции будет использовать с положительным смещением от базового модуля.</span><span class="sxs-lookup"><span data-stu-id="13487-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="13487-113">Память сверх базового модуля может быть драгоценное, поэтому распределителя должен использоваться для выделения памяти только для тела функции.</span><span class="sxs-lookup"><span data-stu-id="13487-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13487-114">Требования</span><span class="sxs-lookup"><span data-stu-id="13487-114">Requirements</span></span>  
 <span data-ttu-id="13487-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13487-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13487-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="13487-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="13487-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13487-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="13487-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="13487-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="13487-119">См. также</span><span class="sxs-lookup"><span data-stu-id="13487-119">See also</span></span>

- [<span data-ttu-id="13487-120">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="13487-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
