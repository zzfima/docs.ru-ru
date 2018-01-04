---
title: "Интерфейс IMethodMalloc"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMethodMalloc
api_location: mscorwks.dll
api_type: COM
f1_keywords: IMethodMalloc
helpviewer_keywords: IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1941a46a60219d9dd56d162f89baf268f220c102
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="80ae9-102">Интерфейс IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="80ae9-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="80ae9-103">Предоставляет метод для выделения памяти для нового тела функции промежуточного языка MSIL.</span><span class="sxs-lookup"><span data-stu-id="80ae9-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80ae9-104">`IMethodMalloc` Интерфейс является простым средством выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="80ae9-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="80ae9-105">Можно выделить память, но не освободить ее.</span><span class="sxs-lookup"><span data-stu-id="80ae9-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80ae9-106">Методы</span><span class="sxs-lookup"><span data-stu-id="80ae9-106">Methods</span></span>  
  
|<span data-ttu-id="80ae9-107">Метод</span><span class="sxs-lookup"><span data-stu-id="80ae9-107">Method</span></span>|<span data-ttu-id="80ae9-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="80ae9-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80ae9-109">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="80ae9-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="80ae9-110">Пытается выделить указанный объем памяти для нового тела функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="80ae9-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80ae9-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="80ae9-111">Remarks</span></span>  
 <span data-ttu-id="80ae9-112">Каждое средство выделения памяти зависит от конкретного модуля и гарантирует, что тело функции будет положительным смещением от базового модуля.</span><span class="sxs-lookup"><span data-stu-id="80ae9-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="80ae9-113">Памяти выше базовый модуль может быть ценное, поэтому распределителя должен использоваться для выделения памяти только для тела функции.</span><span class="sxs-lookup"><span data-stu-id="80ae9-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80ae9-114">Требования</span><span class="sxs-lookup"><span data-stu-id="80ae9-114">Requirements</span></span>  
 <span data-ttu-id="80ae9-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80ae9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80ae9-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="80ae9-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="80ae9-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80ae9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80ae9-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80ae9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ae9-119">См. также</span><span class="sxs-lookup"><span data-stu-id="80ae9-119">See Also</span></span>  
 [<span data-ttu-id="80ae9-120">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="80ae9-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
