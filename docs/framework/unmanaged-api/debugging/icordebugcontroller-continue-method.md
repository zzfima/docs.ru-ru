---
title: Метод ICorDebugController::Continue
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62e2be44165472e2fbf368f61b865d39a5e9fc28
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395470"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="0be9e-102">Метод ICorDebugController::Continue</span><span class="sxs-lookup"><span data-stu-id="0be9e-102">ICorDebugController::Continue Method</span></span>

<span data-ttu-id="0be9e-103">Возобновляет выполнение управляемых потоков после вызова [метода остановкой](icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="0be9e-103">Resumes execution of managed threads after a call to [Stop Method](icordebugcontroller-stop-method.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="0be9e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0be9e-104">Syntax</span></span>

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a><span data-ttu-id="0be9e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0be9e-105">Parameters</span></span>

`fIsOutOfBand`  
<span data-ttu-id="0be9e-106">окне Задайте значение `true`, если продолжить выполнение события внешнего управления. в противном случае задайте значение `false`.</span><span class="sxs-lookup"><span data-stu-id="0be9e-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0be9e-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="0be9e-107">Remarks</span></span>

<span data-ttu-id="0be9e-108">`Continue` возобновляет процесс после вызова метода `ICorDebugController::Stop`.</span><span class="sxs-lookup"><span data-stu-id="0be9e-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>

<span data-ttu-id="0be9e-109">При отладке в смешанном режиме не вызывайте `Continue` в потоке событий Win32, если не продолжить работу по внешнему событию.</span><span class="sxs-lookup"><span data-stu-id="0be9e-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>

<span data-ttu-id="0be9e-110">*Событие с чередованием* — это управляемое событие или нормальное неуправляемое событие, в течение которого отладчик поддерживает взаимодействие с управляемым состоянием процесса.</span><span class="sxs-lookup"><span data-stu-id="0be9e-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="0be9e-111">В этом случае отладчик получает обратный вызов [икордебугунманажедкаллбакк::D ебужевент](icordebugunmanagedcallback-debugevent-method.md) с параметром `fOutOfBand`, для которого задано значение `false`.</span><span class="sxs-lookup"><span data-stu-id="0be9e-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>

<span data-ttu-id="0be9e-112">*Событие внешнего вида* — это неуправляемое событие, в течение которого взаимодействие с управляемым состоянием процесса невозможно, пока процесс остановлен из-за события.</span><span class="sxs-lookup"><span data-stu-id="0be9e-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="0be9e-113">В этом случае отладчик получает обратный вызов `ICorDebugUnmanagedCallback::DebugEvent` с параметром `fOutOfBand`, установленным в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="0be9e-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>

## <a name="requirements"></a><span data-ttu-id="0be9e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0be9e-114">Requirements</span></span>

<span data-ttu-id="0be9e-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0be9e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="0be9e-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0be9e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="0be9e-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0be9e-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0be9e-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0be9e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
