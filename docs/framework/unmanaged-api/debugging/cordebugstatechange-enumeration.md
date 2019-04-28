---
title: Перечисление CorDebugStateChange
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05a29022d3ebad37322aef9826f10689d2b5b06b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723073"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="23c97-102">Перечисление CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="23c97-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="23c97-103">Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.</span><span class="sxs-lookup"><span data-stu-id="23c97-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="23c97-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23c97-104">Syntax</span></span>

```
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="23c97-105">Участники</span><span class="sxs-lookup"><span data-stu-id="23c97-105">Members</span></span>

| <span data-ttu-id="23c97-106">Член</span><span class="sxs-lookup"><span data-stu-id="23c97-106">Member</span></span>            | <span data-ttu-id="23c97-107">Описание</span><span class="sxs-lookup"><span data-stu-id="23c97-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="23c97-108">Процесс достиг нового состояния памяти с помощью механизма прямого выполнения.</span><span class="sxs-lookup"><span data-stu-id="23c97-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="23c97-109">Память процесса может отличаться произвольным образом от предыдущего варианта.</span><span class="sxs-lookup"><span data-stu-id="23c97-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="23c97-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="23c97-110">Remarks</span></span>

 <span data-ttu-id="23c97-111">Является членом `CorDebugStateChange` перечисление предоставляется в качестве аргумента при вызове отладчиком `ProcessStateChanged` метод с помощью [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) или [ICorDebugProcess6:: ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="23c97-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="23c97-112">Требования</span><span class="sxs-lookup"><span data-stu-id="23c97-112">Requirements</span></span>

 <span data-ttu-id="23c97-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23c97-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="23c97-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23c97-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="23c97-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23c97-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="23c97-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23c97-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="23c97-117">См. также</span><span class="sxs-lookup"><span data-stu-id="23c97-117">See also</span></span>

- [<span data-ttu-id="23c97-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="23c97-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="23c97-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="23c97-119">Debugging</span></span>](index.md)
