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
ms.openlocfilehash: 77ef2c65157df4a033700bb8d0295875ede46554
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739109"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="5f5de-102">Структура DacpReJitData</span><span class="sxs-lookup"><span data-stu-id="5f5de-102">DacpReJitData Structure</span></span>

<span data-ttu-id="5f5de-103">Определяет основные сведения о данный метод инструментированного профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="5f5de-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5f5de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f5de-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="5f5de-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5f5de-105">Members</span></span>

| <span data-ttu-id="5f5de-106">Член</span><span class="sxs-lookup"><span data-stu-id="5f5de-106">Member</span></span>           | <span data-ttu-id="5f5de-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5f5de-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="5f5de-108">Номер редакции ReJit для метода.</span><span class="sxs-lookup"><span data-stu-id="5f5de-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="5f5de-109">Флаг, указывающий текущее состояние метода инструментарий ReJit для данной версии.</span><span class="sxs-lookup"><span data-stu-id="5f5de-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="5f5de-110">Базовый адрес rejitted реализацию метода.</span><span class="sxs-lookup"><span data-stu-id="5f5de-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="5f5de-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="5f5de-111">Remarks</span></span>

<span data-ttu-id="5f5de-112">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="5f5de-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="5f5de-113">Чтобы использовать его, определите структуру, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="5f5de-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="5f5de-114">Структуры также должен быть определен с помощью `ms_struct` упаковки в противном случае с помощью компиляторов Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f5de-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="5f5de-115">Требования</span><span class="sxs-lookup"><span data-stu-id="5f5de-115">Requirements</span></span>
<span data-ttu-id="5f5de-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f5de-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5f5de-117">**Заголовок.** None</span><span class="sxs-lookup"><span data-stu-id="5f5de-117">**Header:** None</span></span>  
<span data-ttu-id="5f5de-118">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="5f5de-118">**Library:** None</span></span>  
<span data-ttu-id="5f5de-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5f5de-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5f5de-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5f5de-120">See also</span></span>

- [<span data-ttu-id="5f5de-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="5f5de-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="5f5de-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="5f5de-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
