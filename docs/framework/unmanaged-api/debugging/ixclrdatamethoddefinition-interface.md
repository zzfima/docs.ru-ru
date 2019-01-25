---
title: Интерфейс IXCLRDataMethodDefinition
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4b1e8cb1cf34bb1c5ade1353351aab953e2b734a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644251"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="4765e-102">Интерфейс IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="4765e-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="4765e-103">Предоставляет методы для запроса на получение сведений об определении метода.</span><span class="sxs-lookup"><span data-stu-id="4765e-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="4765e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4765e-104">Methods</span></span>

<span data-ttu-id="4765e-105">Следующие методы перечислены методы, доступные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="4765e-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="4765e-106">Метод</span><span class="sxs-lookup"><span data-stu-id="4765e-106">Method</span></span>                                                                                                                          | <span data-ttu-id="4765e-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="4765e-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="4765e-108">StartEnumInstances</span><span class="sxs-lookup"><span data-stu-id="4765e-108">StartEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="4765e-109">Предоставляет дескриптор для перечисления экземпляров метода для заданного `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="4765e-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="4765e-110">EnumInstance</span><span class="sxs-lookup"><span data-stu-id="4765e-110">EnumInstance</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="4765e-111">Перечисление экземпляров класса определения метода.</span><span class="sxs-lookup"><span data-stu-id="4765e-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="4765e-112">EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="4765e-112">EndEnumInstances</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="4765e-113">Освобождает ресурсы, используемые внутренней итераторы, используется в процессе экземпляра перечисления.</span><span class="sxs-lookup"><span data-stu-id="4765e-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="4765e-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="4765e-114">Remarks</span></span>

<span data-ttu-id="4765e-115">Этот интерфейс находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="4765e-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="4765e-116">Однако это COM-интерфейс, наследуемый от `IUnknown` с идентификатором GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` , можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="4765e-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="4765e-117">Требования</span><span class="sxs-lookup"><span data-stu-id="4765e-117">Requirements</span></span>

<span data-ttu-id="4765e-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4765e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4765e-119">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="4765e-119">**Header:** None</span></span>  
<span data-ttu-id="4765e-120">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="4765e-120">**Library:** None</span></span>  
<span data-ttu-id="4765e-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4765e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4765e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4765e-122">See also</span></span>

- [<span data-ttu-id="4765e-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="4765e-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="4765e-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4765e-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
