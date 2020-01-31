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
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790425"
---
# <a name="ixclrdatamethoddefinition-interface"></a><span data-ttu-id="356de-102">Интерфейс IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="356de-102">IXCLRDataMethodDefinition Interface</span></span>

<span data-ttu-id="356de-103">Предоставляет методы для запроса сведений об определении метода.</span><span class="sxs-lookup"><span data-stu-id="356de-103">Provides methods for querying information about a method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="356de-104">Методы</span><span class="sxs-lookup"><span data-stu-id="356de-104">Methods</span></span>

<span data-ttu-id="356de-105">Ниже перечислены методы, доступные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="356de-105">The following methods are some of the methods available in the interface.</span></span>

| <span data-ttu-id="356de-106">Метод</span><span class="sxs-lookup"><span data-stu-id="356de-106">Method</span></span>                                                                                                                          | <span data-ttu-id="356de-107">Описание</span><span class="sxs-lookup"><span data-stu-id="356de-107">Description</span></span>                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="356de-108">стартенуминстанцес</span><span class="sxs-lookup"><span data-stu-id="356de-108">StartEnumInstances</span></span>](ixclrdatamethoddefinition-startenuminstances-method.md) | <span data-ttu-id="356de-109">Предоставляет обработчик для перечисления экземпляров методов для заданного `IXCLRDataAppDomain`.</span><span class="sxs-lookup"><span data-stu-id="356de-109">Provides a handle for the enumeration of method instances for a given `IXCLRDataAppDomain`.</span></span> |
| [<span data-ttu-id="356de-110">енуминстанце</span><span class="sxs-lookup"><span data-stu-id="356de-110">EnumInstance</span></span>](ixclrdatamethoddefinition-enuminstance-method.md)             | <span data-ttu-id="356de-111">Перечисляет экземпляры этого определения метода.</span><span class="sxs-lookup"><span data-stu-id="356de-111">Enumerates the instances of this method definition.</span></span>                                         |
| [<span data-ttu-id="356de-112">енденуминстанцес</span><span class="sxs-lookup"><span data-stu-id="356de-112">EndEnumInstances</span></span>](ixclrdatamethoddefinition-endenuminstances-method.md)     | <span data-ttu-id="356de-113">Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.</span><span class="sxs-lookup"><span data-stu-id="356de-113">Releases the resources used by internal iterators used during instance enumeration.</span></span>         |

## <a name="remarks"></a><span data-ttu-id="356de-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="356de-114">Remarks</span></span>

<span data-ttu-id="356de-115">Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="356de-115">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="356de-116">Однако это COM-интерфейс, производный от `IUnknown` с GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97`, который можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="356de-116">However, it's a COM interface that derives from `IUnknown` with GUID `AAF60008-FB2C-420b-8FB1-42D244A54A97` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="356de-117">Требования</span><span class="sxs-lookup"><span data-stu-id="356de-117">Requirements</span></span>

<span data-ttu-id="356de-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="356de-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="356de-119">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="356de-119">**Header:** None</span></span>  
<span data-ttu-id="356de-120">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="356de-120">**Library:** None</span></span>  
<span data-ttu-id="356de-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="356de-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="356de-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="356de-122">See also</span></span>

- [<span data-ttu-id="356de-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="356de-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="356de-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="356de-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
