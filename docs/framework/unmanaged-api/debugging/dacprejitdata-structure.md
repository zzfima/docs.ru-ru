---
title: Структура DacpReJitData
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: a2850add9acb2f7c5297ac6956e349c9277be291
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122802"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="6cd3c-102">Структура DacpReJitData</span><span class="sxs-lookup"><span data-stu-id="6cd3c-102">DacpReJitData Structure</span></span>

<span data-ttu-id="6cd3c-103">Определяет основные сведения о данный метод инструментированного профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="6cd3c-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6cd3c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6cd3c-104">Syntax</span></span>

```
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a><span data-ttu-id="6cd3c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="6cd3c-105">Members</span></span>

| <span data-ttu-id="6cd3c-106">Член</span><span class="sxs-lookup"><span data-stu-id="6cd3c-106">Member</span></span>           | <span data-ttu-id="6cd3c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6cd3c-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="6cd3c-108">Номер редакции ReJit для метода.</span><span class="sxs-lookup"><span data-stu-id="6cd3c-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="6cd3c-109">Флаг, указывающий текущее состояние метода инструментарий ReJit для данной версии.</span><span class="sxs-lookup"><span data-stu-id="6cd3c-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="6cd3c-110">Базовый адрес rejitted реализацию метода.</span><span class="sxs-lookup"><span data-stu-id="6cd3c-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="6cd3c-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="6cd3c-111">Remarks</span></span>

<span data-ttu-id="6cd3c-112">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="6cd3c-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="6cd3c-113">Чтобы использовать его, определите структуру, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="6cd3c-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="6cd3c-114">Структуры также должен быть определен с помощью `ms_struct` упаковки в противном случае с помощью компиляторов Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6cd3c-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="6cd3c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="6cd3c-115">Requirements</span></span>
<span data-ttu-id="6cd3c-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cd3c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6cd3c-117">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="6cd3c-117">**Header:** None</span></span>  
<span data-ttu-id="6cd3c-118">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="6cd3c-118">**Library:** None</span></span>  
<span data-ttu-id="6cd3c-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6cd3c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6cd3c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6cd3c-120">See also</span></span>

- [<span data-ttu-id="6cd3c-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="6cd3c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6cd3c-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="6cd3c-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
