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
ms.openlocfilehash: 239e3a82df0e6010278669f9f429bfad0d163319
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133724"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="51f76-102">Перечисление CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="51f76-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="51f76-103">Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.</span><span class="sxs-lookup"><span data-stu-id="51f76-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="51f76-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51f76-104">Syntax</span></span>

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="51f76-105">Члены</span><span class="sxs-lookup"><span data-stu-id="51f76-105">Members</span></span>

| <span data-ttu-id="51f76-106">Член</span><span class="sxs-lookup"><span data-stu-id="51f76-106">Member</span></span>            | <span data-ttu-id="51f76-107">Описание</span><span class="sxs-lookup"><span data-stu-id="51f76-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="51f76-108">Процесс достиг нового состояния памяти с помощью механизма прямого выполнения.</span><span class="sxs-lookup"><span data-stu-id="51f76-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="51f76-109">Память процесса может отличаться произвольным образом от предыдущего варианта.</span><span class="sxs-lookup"><span data-stu-id="51f76-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="51f76-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="51f76-110">Remarks</span></span>

 <span data-ttu-id="51f76-111">Член перечисления `CorDebugStateChange` предоставляется в качестве аргумента, когда отладчик вызывает метод `ProcessStateChanged` с помощью [ICorDebugProcess4::P роцессстатечанжед](icordebugprocess4-processstatechanged-method.md) или [ICorDebugProcess6::P роцессстатечанжед](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="51f76-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="51f76-112">Требования</span><span class="sxs-lookup"><span data-stu-id="51f76-112">Requirements</span></span>

 <span data-ttu-id="51f76-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51f76-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="51f76-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51f76-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="51f76-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51f76-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="51f76-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51f76-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="51f76-117">См. также</span><span class="sxs-lookup"><span data-stu-id="51f76-117">See also</span></span>

- [<span data-ttu-id="51f76-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="51f76-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="51f76-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="51f76-119">Debugging</span></span>](index.md)
