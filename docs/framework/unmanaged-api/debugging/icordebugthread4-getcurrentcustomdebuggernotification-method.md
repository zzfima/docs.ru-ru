---
title: Метод ICorDebugThread4::GetCurrentCustomDebuggerNotification
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
ms.openlocfilehash: ba4375511fe7f5aaee032c4e132de54808041111
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122446"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="8bd6f-102">Метод ICorDebugThread4::GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="8bd6f-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="8bd6f-103">Возвращает текущий объект [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="8bd6f-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="8bd6f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bd6f-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="8bd6f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8bd6f-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="8bd6f-106">заполняет Указатель на текущий объект `ICorDebugManagedCallback3::CustomNotification` в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="8bd6f-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="8bd6f-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="8bd6f-107">Remarks</span></span>

<span data-ttu-id="8bd6f-108">Значение `ppNotificationObject` равно null, если метод не вызывается из обратного вызова `ICorDebugManagedCallback3::CustomNotification` или если текущий объект уведомления не существует.</span><span class="sxs-lookup"><span data-stu-id="8bd6f-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="8bd6f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8bd6f-109">Requirements</span></span>

<span data-ttu-id="8bd6f-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bd6f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="8bd6f-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bd6f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="8bd6f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bd6f-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="8bd6f-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bd6f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8bd6f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8bd6f-114">See also</span></span>

- [<span data-ttu-id="8bd6f-115">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="8bd6f-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="8bd6f-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8bd6f-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="8bd6f-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="8bd6f-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
