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
ms.openlocfilehash: c67ce15175f8667139f99cec1ed17531eab473e1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935650"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="1373d-102">Интерфейс IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="1373d-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="1373d-103">Предоставляет метод для выделения памяти для нового текста функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="1373d-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1373d-104">`IMethodMalloc` Интерфейс — это простой механизм выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="1373d-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="1373d-105">Она позволяет выделить память, но не освобождает ее.</span><span class="sxs-lookup"><span data-stu-id="1373d-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1373d-106">Методы</span><span class="sxs-lookup"><span data-stu-id="1373d-106">Methods</span></span>  
  
|<span data-ttu-id="1373d-107">Метод</span><span class="sxs-lookup"><span data-stu-id="1373d-107">Method</span></span>|<span data-ttu-id="1373d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="1373d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1373d-109">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="1373d-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="1373d-110">Пытается выделить указанный объем памяти для нового текста функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="1373d-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1373d-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1373d-111">Remarks</span></span>  
 <span data-ttu-id="1373d-112">Каждый распределитель зависит от конкретного модуля и гарантирует, что текст функции будет иметь положительное смещение от базового модуля.</span><span class="sxs-lookup"><span data-stu-id="1373d-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="1373d-113">Память над базовым модулем может быть ценной, поэтому распределитель должен использоваться для выделения памяти только для тела функции.</span><span class="sxs-lookup"><span data-stu-id="1373d-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1373d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1373d-114">Requirements</span></span>  
 <span data-ttu-id="1373d-115">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1373d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1373d-116">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="1373d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1373d-117">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="1373d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1373d-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1373d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1373d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1373d-119">See also</span></span>

- [<span data-ttu-id="1373d-120">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="1373d-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
