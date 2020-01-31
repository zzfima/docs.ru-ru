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
ms.openlocfilehash: 46031f29da6916eeaeea863ebef6924a720d7155
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793815"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="94470-102">Структура DacpReJitData</span><span class="sxs-lookup"><span data-stu-id="94470-102">DacpReJitData Structure</span></span>

<span data-ttu-id="94470-103">Определяет основные сведения о конкретном инструментированном методе профилирования.</span><span class="sxs-lookup"><span data-stu-id="94470-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="94470-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94470-104">Syntax</span></span>

```cpp
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

## <a name="members"></a><span data-ttu-id="94470-105">Участники</span><span class="sxs-lookup"><span data-stu-id="94470-105">Members</span></span>

| <span data-ttu-id="94470-106">Член</span><span class="sxs-lookup"><span data-stu-id="94470-106">Member</span></span>           | <span data-ttu-id="94470-107">Описание</span><span class="sxs-lookup"><span data-stu-id="94470-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="94470-108">Номер редакции ReJit для метода.</span><span class="sxs-lookup"><span data-stu-id="94470-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="94470-109">Флаг, указывающий текущее состояние инструментирования ReJit метода для данной версии.</span><span class="sxs-lookup"><span data-stu-id="94470-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="94470-110">Базовый адрес реализации режиттед метода.</span><span class="sxs-lookup"><span data-stu-id="94470-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="94470-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="94470-111">Remarks</span></span>

<span data-ttu-id="94470-112">Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="94470-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="94470-113">Чтобы использовать его, определите структуру, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="94470-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="94470-114">Структура также должна быть определена с помощью `ms_struct` упаковки, если не используются компиляторы Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="94470-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="94470-115">Требования</span><span class="sxs-lookup"><span data-stu-id="94470-115">Requirements</span></span>
<span data-ttu-id="94470-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94470-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="94470-117">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="94470-117">**Header:** None</span></span>  
<span data-ttu-id="94470-118">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="94470-118">**Library:** None</span></span>  
<span data-ttu-id="94470-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="94470-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="94470-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="94470-120">See also</span></span>

- [<span data-ttu-id="94470-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="94470-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="94470-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="94470-122">Debugging Structures</span></span>](debugging-structures.md)
