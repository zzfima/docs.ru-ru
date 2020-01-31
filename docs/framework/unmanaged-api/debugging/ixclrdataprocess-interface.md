---
title: Интерфейс IXCLRDataProcess
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a5d707d61513b030e5968af28db3c2a606e4419b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790376"
---
# <a name="ixclrdataprocess-interface"></a><span data-ttu-id="42851-102">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="42851-102">IXCLRDataProcess Interface</span></span>

<span data-ttu-id="42851-103">Предоставляет методы для запроса сведений о процессе.</span><span class="sxs-lookup"><span data-stu-id="42851-103">Provides methods for querying information about a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="42851-104">Методы</span><span class="sxs-lookup"><span data-stu-id="42851-104">Methods</span></span>

| <span data-ttu-id="42851-105">Метод</span><span class="sxs-lookup"><span data-stu-id="42851-105">Method</span></span>                                                                                                                                               | <span data-ttu-id="42851-106">Описание</span><span class="sxs-lookup"><span data-stu-id="42851-106">Description</span></span>                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="42851-107">жетаппдомаинбюникуеид</span><span class="sxs-lookup"><span data-stu-id="42851-107">GetAppDomainByUniqueId</span></span>](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | <span data-ttu-id="42851-108">Возвращает `AppDomain` в процессе по его уникальному идентификатору.</span><span class="sxs-lookup"><span data-stu-id="42851-108">Gets an `AppDomain` in a process by its unique id.</span></span>                                              |
| [<span data-ttu-id="42851-109">стартенуммодулес</span><span class="sxs-lookup"><span data-stu-id="42851-109">StartEnumModules</span></span>](ixclrdataprocess-startenummodules-method.md)                                   | <span data-ttu-id="42851-110">Предоставляет описатель для перечисления модулей процесса.</span><span class="sxs-lookup"><span data-stu-id="42851-110">Provides a handle to enumerate the modules of a process.</span></span>                                        |
| [<span data-ttu-id="42851-111">енуммодуле</span><span class="sxs-lookup"><span data-stu-id="42851-111">EnumModule</span></span>](ixclrdataprocess-enummodule-method.md)                                               | <span data-ttu-id="42851-112">Перечисляет модули этого процесса.</span><span class="sxs-lookup"><span data-stu-id="42851-112">Enumerates the modules of this process.</span></span>                                                         |
| [<span data-ttu-id="42851-113">енденуммодулес</span><span class="sxs-lookup"><span data-stu-id="42851-113">EndEnumModules</span></span>](ixclrdataprocess-endenummodules-method.md)                                       | <span data-ttu-id="42851-114">Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении модулей.</span><span class="sxs-lookup"><span data-stu-id="42851-114">Releases the resources used by internal iterators used during module enumeration.</span></span>               |
| [<span data-ttu-id="42851-115">стартенуммесодинстанцесбяддресс</span><span class="sxs-lookup"><span data-stu-id="42851-115">StartEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | <span data-ttu-id="42851-116">Предоставляет описатель для перечисления экземпляров методов `AppDomain`, начиная с заданного адреса.</span><span class="sxs-lookup"><span data-stu-id="42851-116">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span> |
| [<span data-ttu-id="42851-117">енуммесодинстанцебяддресс</span><span class="sxs-lookup"><span data-stu-id="42851-117">EnumMethodInstanceByAddress</span></span>](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | <span data-ttu-id="42851-118">Перечисляет экземпляры методов этого процесса, начиная с смещения адреса.</span><span class="sxs-lookup"><span data-stu-id="42851-118">Enumerates the method instances of this process starting at an address offset.</span></span>                  |
| [<span data-ttu-id="42851-119">енденуммесодинстанцесбяддресс</span><span class="sxs-lookup"><span data-stu-id="42851-119">EndEnumMethodInstancesByAddress</span></span>](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | <span data-ttu-id="42851-120">Освобождает ресурсы, используемые внутренними итераторами, используемыми при перечислении экземпляров.</span><span class="sxs-lookup"><span data-stu-id="42851-120">Releases the resources used by internal iterators used during instance enumeration.</span></span>             |

## <a name="remarks"></a><span data-ttu-id="42851-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="42851-121">Remarks</span></span>

<span data-ttu-id="42851-122">Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="42851-122">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="42851-123">Однако это COM-интерфейс, производный от `IUnknown` с GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7`, который можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="42851-123">However, it's a COM interface that derives from `IUnknown` with GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="42851-124">Требования</span><span class="sxs-lookup"><span data-stu-id="42851-124">Requirements</span></span>

<span data-ttu-id="42851-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42851-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="42851-126">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="42851-126">**Header:** None</span></span>  
<span data-ttu-id="42851-127">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="42851-127">**Library:** None</span></span>  
<span data-ttu-id="42851-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="42851-128">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="42851-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="42851-129">See also</span></span>

- [<span data-ttu-id="42851-130">Отладка</span><span class="sxs-lookup"><span data-stu-id="42851-130">Debugging</span></span>](index.md)
- [<span data-ttu-id="42851-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="42851-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
