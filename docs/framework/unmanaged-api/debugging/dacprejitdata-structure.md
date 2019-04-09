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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122802"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="d0152-102">Структура DacpReJitData</span><span class="sxs-lookup"><span data-stu-id="d0152-102">DacpReJitData Structure</span></span>

<span data-ttu-id="d0152-103">Определяет основные сведения о данный метод инструментированного профилировщиком.</span><span class="sxs-lookup"><span data-stu-id="d0152-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="d0152-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0152-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="d0152-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d0152-105">Members</span></span>

| <span data-ttu-id="d0152-106">Член</span><span class="sxs-lookup"><span data-stu-id="d0152-106">Member</span></span>           | <span data-ttu-id="d0152-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d0152-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="d0152-108">Номер редакции ReJit для метода.</span><span class="sxs-lookup"><span data-stu-id="d0152-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="d0152-109">Флаг, указывающий текущее состояние метода инструментарий ReJit для данной версии.</span><span class="sxs-lookup"><span data-stu-id="d0152-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="d0152-110">Базовый адрес rejitted реализацию метода.</span><span class="sxs-lookup"><span data-stu-id="d0152-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="d0152-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0152-111">Remarks</span></span>

<span data-ttu-id="d0152-112">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="d0152-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="d0152-113">Чтобы использовать его, определите структуру, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="d0152-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="d0152-114">Структуры также должен быть определен с помощью `ms_struct` упаковки в противном случае с помощью компиляторов Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d0152-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="d0152-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d0152-115">Requirements</span></span>
<span data-ttu-id="d0152-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0152-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="d0152-117">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="d0152-117">**Header:** None</span></span>  
<span data-ttu-id="d0152-118">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="d0152-118">**Library:** None</span></span>  
**<span data-ttu-id="d0152-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d0152-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="d0152-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d0152-120">See also</span></span>

- [<span data-ttu-id="d0152-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="d0152-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="d0152-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="d0152-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
