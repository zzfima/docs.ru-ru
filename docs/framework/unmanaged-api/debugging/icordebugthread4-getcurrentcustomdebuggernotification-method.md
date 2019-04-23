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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f626ff6e562bd9bc94440f31e9470a45cc32cfbd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216331"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="30fa9-102">Метод ICorDebugThread4::GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="30fa9-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="30fa9-103">Получает текущий [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) объекта в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="30fa9-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="30fa9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30fa9-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="30fa9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30fa9-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="30fa9-106">[out] Указатель на текущий `ICorDebugManagedCallback3::CustomNotification` объекта в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="30fa9-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="30fa9-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="30fa9-107">Remarks</span></span>

<span data-ttu-id="30fa9-108">Значение `ppNotificationObject` имеет значение null, если метод не вызывается из `ICorDebugManagedCallback3::CustomNotification` обратного вызова, или если текущий объект уведомления не существует.</span><span class="sxs-lookup"><span data-stu-id="30fa9-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="30fa9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="30fa9-109">Requirements</span></span>

<span data-ttu-id="30fa9-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30fa9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="30fa9-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30fa9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="30fa9-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30fa9-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="30fa9-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30fa9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="30fa9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="30fa9-114">See also</span></span>

- [<span data-ttu-id="30fa9-115">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="30fa9-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="30fa9-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="30fa9-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="30fa9-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="30fa9-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
