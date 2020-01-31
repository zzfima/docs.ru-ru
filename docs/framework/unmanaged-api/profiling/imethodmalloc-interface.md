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
ms.openlocfilehash: e9cbf4551c2f8b183e9e6c37a74b13aff3a19ec1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860986"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="173ae-102">Интерфейс IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="173ae-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="173ae-103">Предоставляет метод для выделения памяти для нового текста функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="173ae-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="173ae-104">Интерфейс `IMethodMalloc` — это простой механизм выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="173ae-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="173ae-105">Она позволяет выделить память, но не освобождает ее.</span><span class="sxs-lookup"><span data-stu-id="173ae-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="173ae-106">Методы</span><span class="sxs-lookup"><span data-stu-id="173ae-106">Methods</span></span>  
  
|<span data-ttu-id="173ae-107">Метод</span><span class="sxs-lookup"><span data-stu-id="173ae-107">Method</span></span>|<span data-ttu-id="173ae-108">Описание</span><span class="sxs-lookup"><span data-stu-id="173ae-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="173ae-109">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="173ae-109">Alloc Method</span></span>](imethodmalloc-alloc-method.md)|<span data-ttu-id="173ae-110">Пытается выделить указанный объем памяти для нового текста функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="173ae-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="173ae-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="173ae-111">Remarks</span></span>  
 <span data-ttu-id="173ae-112">Каждый распределитель зависит от конкретного модуля и гарантирует, что текст функции будет иметь положительное смещение от базового модуля.</span><span class="sxs-lookup"><span data-stu-id="173ae-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="173ae-113">Память над базовым модулем может быть ценной, поэтому распределитель должен использоваться для выделения памяти только для тела функции.</span><span class="sxs-lookup"><span data-stu-id="173ae-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="173ae-114">Требования</span><span class="sxs-lookup"><span data-stu-id="173ae-114">Requirements</span></span>  
 <span data-ttu-id="173ae-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="173ae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="173ae-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="173ae-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="173ae-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="173ae-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="173ae-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="173ae-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="173ae-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="173ae-119">See also</span></span>

- [<span data-ttu-id="173ae-120">Интерфейсы профилирования</span><span class="sxs-lookup"><span data-stu-id="173ae-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
