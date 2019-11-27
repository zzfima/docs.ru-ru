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
ms.openlocfilehash: 3f840154d472dbcea7dfef7ba93e38c80b836734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447547"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="b3c58-102">Интерфейс IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="b3c58-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="b3c58-103">Предоставляет метод для выделения памяти для нового текста функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="b3c58-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3c58-104">Интерфейс `IMethodMalloc` — это простой механизм выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="b3c58-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="b3c58-105">Она позволяет выделить память, но не освобождает ее.</span><span class="sxs-lookup"><span data-stu-id="b3c58-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3c58-106">Методы</span><span class="sxs-lookup"><span data-stu-id="b3c58-106">Methods</span></span>  
  
|<span data-ttu-id="b3c58-107">Метод</span><span class="sxs-lookup"><span data-stu-id="b3c58-107">Method</span></span>|<span data-ttu-id="b3c58-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b3c58-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3c58-109">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="b3c58-109">Alloc Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md)|<span data-ttu-id="b3c58-110">Пытается выделить указанный объем памяти для нового текста функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="b3c58-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3c58-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="b3c58-111">Remarks</span></span>  
 <span data-ttu-id="b3c58-112">Каждый распределитель зависит от конкретного модуля и гарантирует, что текст функции будет иметь положительное смещение от базового модуля.</span><span class="sxs-lookup"><span data-stu-id="b3c58-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="b3c58-113">Память над базовым модулем может быть ценной, поэтому распределитель должен использоваться для выделения памяти только для тела функции.</span><span class="sxs-lookup"><span data-stu-id="b3c58-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3c58-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b3c58-114">Requirements</span></span>  
 <span data-ttu-id="b3c58-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3c58-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3c58-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3c58-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3c58-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3c58-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3c58-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3c58-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c58-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b3c58-119">See also</span></span>

- [<span data-ttu-id="b3c58-120">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="b3c58-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
