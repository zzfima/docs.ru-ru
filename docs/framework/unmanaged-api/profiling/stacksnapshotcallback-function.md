---
title: Функция StackSnapshotCallback
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
ms.openlocfilehash: c0cec9eb7bb8bbc94b255152a9b4d79108bdd1b1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427078"
---
# <a name="stacksnapshotcallback-function"></a>Функция StackSnapshotCallback
Предоставляет профилировщику сведения о каждом управляемом кадре и каждом запуске неуправляемых кадров в стеке во время прохода стека, который инициируется методом [ICorProfilerInfo2::D остаккснапшот](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `funcId`  
 окне Если это значение равно нулю, этот обратный вызов предназначен для запуска неуправляемых кадров; в противном случае это идентификатор управляемой функции, и этот обратный вызов предназначен для управляемого фрейма.  
  
 `ip`  
 окне Значение указателя инструкций машинного кода в кадре.  
  
 `frameInfo`  
 окне Значение `COR_PRF_FRAME_INFO`, которое ссылается на сведения о кадре стека. Это значение допустимо для использования только во время этого обратного вызова.  
  
 `contextSize`  
 окне Размер структуры `CONTEXT`, на которую ссылается параметр `context`.  
  
 `context`  
 окне Указатель на структуру Win32 `CONTEXT`, которая представляет состояние ЦП для этого кадра.  
  
 Параметр `context` действителен, только если флаг COR_PRF_SNAPSHOT_CONTEXT был передан `ICorProfilerInfo2::DoStackSnapshot`.  
  
 `clientData`  
 окне Указатель на данные клиента, которые передаются непосредственно через `ICorProfilerInfo2::DoStackSnapshot`.  
  
## <a name="remarks"></a>Примечания  
 Функция `StackSnapshotCallback` реализуется модулем записи профилировщика. Необходимо ограничить сложность работы, выполненной в `StackSnapshotCallback`. Например, при использовании `ICorProfilerInfo2::DoStackSnapshot` в асинхронном режиме целевой поток может удерживать блокировки. Если код в `StackSnapshotCallback` требует одних и тех же блокировок, может возникнуть взаимоблокировка.  
  
 Метод `ICorProfilerInfo2::DoStackSnapshot` вызывает функцию `StackSnapshotCallback` один раз для каждого управляемого кадра или один раз для каждого запуска неуправляемых фреймов. Если `StackSnapshotCallback` вызывается для запуска неуправляемых кадров, профилировщик может использовать контекст Register (на который ссылается параметр `context`) для выполнения собственного анализа неуправляемого стека. В этом случае структура Win32 `CONTEXT` представляет состояние ЦП для последнего отправленного кадра в рамках выполнения неуправляемых кадров. Несмотря на то, что структура Win32 `CONTEXT` включает значения для всех регистров, следует полагаться только на значения регистра указателя стека, регистра указателя кадра, регистра указателя инструкций и неизменяемых (то есть сохраненных) целочисленных регистров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf. idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Метод DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
