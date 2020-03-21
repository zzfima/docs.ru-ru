---
title: ICorDebugПроцесс4::ProcessStateChanged Метод
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178632"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="caefb-102">ICorDebugПроцесс4::ProcessStateChanged Метод</span><span class="sxs-lookup"><span data-stu-id="caefb-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="caefb-103">Уведомляет конвейер ICorDebug о том, что недогибающий процесс продолжает выполнение debugee.</span><span class="sxs-lookup"><span data-stu-id="caefb-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="caefb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="caefb-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="caefb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="caefb-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="caefb-106">(в) Участник [перечисления CorDebugStateChange,](cordebugstatechange-enumeration.md) описывающий состояние выполнения процесса.</span><span class="sxs-lookup"><span data-stu-id="caefb-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="caefb-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="caefb-107">Remarks</span></span>

<span data-ttu-id="caefb-108">Предоставленный метод является `ICorDebugProcess4` частью интерфейса и соответствует четвертому слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="caefb-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="caefb-109">Требования</span><span class="sxs-lookup"><span data-stu-id="caefb-109">Requirements</span></span>

 <span data-ttu-id="caefb-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caefb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="caefb-111">**Заголовок:** Ни один</span><span class="sxs-lookup"><span data-stu-id="caefb-111">**Header:** None</span></span>

 <span data-ttu-id="caefb-112">**Библиотека:** Ни один</span><span class="sxs-lookup"><span data-stu-id="caefb-112">**Library:** None</span></span>

 <span data-ttu-id="caefb-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caefb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="caefb-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="caefb-114">See also</span></span>

- [<span data-ttu-id="caefb-115">Интерфейс ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="caefb-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="caefb-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="caefb-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="caefb-117">Отладки</span><span class="sxs-lookup"><span data-stu-id="caefb-117">Debugging</span></span>](index.md)
