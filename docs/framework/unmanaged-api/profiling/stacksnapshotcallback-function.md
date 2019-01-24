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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e73afa7ef33e12d6bc658c944c79ce1bc4f94f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572431"
---
# <a name="stacksnapshotcallback-function"></a>Функция StackSnapshotCallback
Предоставляет сведения о каждого управляемого кадра и каждом запуске неуправляемых фреймов в стеке во время стека, который инициируется профилировщик [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `funcId`  
 [in] Если это значение равно нулю, этот обратный вызов предназначен для неуправляемых фреймов; в противном случае он представляет собой идентификатор управляемой функции, и этот обратный вызов является для управляемого фрейма.  
  
 `ip`  
 [in] Значение указателя инструкции машинного кода в фрейме.  
  
 `frameInfo`  
 [in] Объект `COR_PRF_FRAME_INFO` значение, которое ссылается на сведения о кадре стека. Это значение является допустимым для использования только во время этого обратного вызова.  
  
 `contextSize`  
 [in] Размер `CONTEXT` структуру, которая ссылается `context` параметра.  
  
 `context`  
 [in] Указатель на Win32 `CONTEXT` структура, представляющая состояние ЦП для данного кадра.  
  
 `context` Параметр допустим только в том случае, если был передан флаг COR_PRF_SNAPSHOT_CONTEXT `ICorProfilerInfo2::DoStackSnapshot`.  
  
 `clientData`  
 [in] Указатель на данные клиента, который передается напрямую через из `ICorProfilerInfo2::DoStackSnapshot`.  
  
## <a name="remarks"></a>Примечания  
 `StackSnapshotCallback` Функция реализуется разработчиком профилировщика. Необходимо ограничить сложность работы, проделанной `StackSnapshotCallback`. Например, при использовании `ICorProfilerInfo2::DoStackSnapshot` в асинхронном режиме, целевой поток может блокироваться. Если код в `StackSnapshotCallback` требуются те же блокировки, взаимоблокировки неприятности.  
  
 `ICorProfilerInfo2::DoStackSnapshot` Вызовы методов `StackSnapshotCallback` функцию один раз в управляемый блок кода, или один раз на серию неуправляемых фреймов. Если `StackSnapshotCallback` вызывается для запуска неуправляемых фреймов, профилировщик может использовать регистров (ссылается `context` параметр) для выполнения свой собственный неуправляемый разбор стека. В данном случае Win32 `CONTEXT` структура представляет состояние ЦП для наиболее недавно отправленных кадра в серию неуправляемых фреймов. Несмотря на то что Win32 `CONTEXT` структура включает значения для всех регистров, следует полагаться только на значениях регистр указателя стека, регистр указателя кадра, регистр указателя инструкции и постоянные (хранимые) целочисленных регистров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Метод DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
