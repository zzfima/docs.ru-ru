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
ms.openlocfilehash: 14356a12c944ef93dba5e7b818d3ee5cf5adc607
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125423"
---
# <a name="icordebugcontrollercontinue-method"></a>Метод ICorDebugController::Continue

Возобновляет выполнение управляемых потоков после вызова [метода остановкой](icordebugcontroller-stop-method.md).

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a>Параметры

`fIsOutOfBand`  
окне Задайте значение `true`, если продолжить выполнение события внешнего управления. в противном случае задайте значение `false`.

## <a name="remarks"></a>Заметки

`Continue` возобновляет процесс после вызова метода `ICorDebugController::Stop`.

При отладке в смешанном режиме не вызывайте `Continue` в потоке событий Win32, если не продолжить работу по внешнему событию.

*Событие с чередованием* — это управляемое событие или нормальное неуправляемое событие, в течение которого отладчик поддерживает взаимодействие с управляемым состоянием процесса. В этом случае отладчик получает обратный вызов [икордебугунманажедкаллбакк::D ебужевент](icordebugunmanagedcallback-debugevent-method.md) с параметром `fOutOfBand`, для которого задано значение `false`.

*Событие внешнего вида* — это неуправляемое событие, в течение которого взаимодействие с управляемым состоянием процесса невозможно, пока процесс остановлен из-за события. В этом случае отладчик получает обратный вызов `ICorDebugUnmanagedCallback::DebugEvent` с параметром `fOutOfBand`, установленным в значение `true`.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
