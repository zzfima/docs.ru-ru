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
ms.openlocfilehash: b11cf0fadc9142ee291115cf9f0d84e6429834fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455121"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="519cb-102">Интерфейс IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="519cb-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="519cb-103">Предоставляет метод для выделения памяти для нового тела функции промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="519cb-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="519cb-104">`IMethodMalloc` Интерфейс является простым средством выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="519cb-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="519cb-105">Можно выделить память, но не освободить ее.</span><span class="sxs-lookup"><span data-stu-id="519cb-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="519cb-106">Методы</span><span class="sxs-lookup"><span data-stu-id="519cb-106">Methods</span></span>  
  
|<span data-ttu-id="519cb-107">Метод</span><span class="sxs-lookup"><span data-stu-id="519cb-107">Method</span></span>|<span data-ttu-id="519cb-108">Описание</span><span class="sxs-lookup"><span data-stu-id="519cb-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="519cb-109">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="519cb-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="519cb-110">Пытается выделить указанный объем памяти для нового тела функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="519cb-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="519cb-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="519cb-111">Remarks</span></span>  
 <span data-ttu-id="519cb-112">Каждое средство выделения памяти зависит от конкретного модуля и гарантирует, что тело функции будет положительным смещением от базового модуля.</span><span class="sxs-lookup"><span data-stu-id="519cb-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="519cb-113">Памяти выше базовый модуль может быть ценное, поэтому распределителя должен использоваться для выделения памяти только для тела функции.</span><span class="sxs-lookup"><span data-stu-id="519cb-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="519cb-114">Требования</span><span class="sxs-lookup"><span data-stu-id="519cb-114">Requirements</span></span>  
 <span data-ttu-id="519cb-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="519cb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="519cb-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="519cb-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="519cb-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="519cb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="519cb-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="519cb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="519cb-119">См. также</span><span class="sxs-lookup"><span data-stu-id="519cb-119">See Also</span></span>  
 [<span data-ttu-id="519cb-120">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="519cb-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
