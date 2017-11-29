---
title: "Функция StackSnapshotCallback"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackSnapshotCallback
api_location: mscorwks.dll
api_type: COM
f1_keywords: StackSnapshotCallback
helpviewer_keywords: StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 92f7071ebcf7664b3622c180b9f1bade50909cea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="stacksnapshotcallback-function"></a>Функция StackSnapshotCallback
Предоставляет сведения о каждого управляемого кадра и каждом запуске неуправляемого кадра в стеке во время стека, который инициируется профилировщик [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) метод.  
  
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
 [in] Если это значение равно нулю, этот обратный вызов предназначен для управляемого кадра. в противном случае оно является идентификатором управляемой функции, и этот обратный вызов предназначен для управляемого кадра.  
  
 `ip`  
 [in] Значение указателя инструкций машинного кода в кадре.  
  
 `frameInfo`  
 [in] Объект `COR_PRF_FRAME_INFO` значение, которое ссылается на сведения о кадре стека. Это значение является допустимым для использования только во время этого обратного вызова.  
  
 `contextSize`  
 [in] Размер `CONTEXT` структуры, который ссылается `context` параметра.  
  
 `context`  
 [in] Указатель на объект Win32 `CONTEXT` структуры, который представляет состояние ЦП для этого кадра.  
  
 `context` Параметр допустим только в том случае, если переданный флаг COR_PRF_SNAPSHOT_CONTEXT `ICorProfilerInfo2::DoStackSnapshot`.  
  
 `clientData`  
 [in] Указатель на данные клиента, которые передаются непосредственно от `ICorProfilerInfo2::DoStackSnapshot`.  
  
## <a name="remarks"></a>Примечания  
 `StackSnapshotCallback` Функция реализуется разработчиком профилировщика. Необходимо установить ограничение сложности работы, проделанной `StackSnapshotCallback`. Например, при использовании `ICorProfilerInfo2::DoStackSnapshot` в асинхронном режиме, целевой поток может удерживать блокировки. Если код в `StackSnapshotCallback` требуются те же блокировки, можно гарантировать взаимоблокировку.  
  
 `ICorProfilerInfo2::DoStackSnapshot` Вызовы метода `StackSnapshotCallback` функцию один раз за кадр управляемого или один раз на выполнение неуправляемого кадра. Если `StackSnapshotCallback` вызывается для запуска неуправляемых кадров, профилировщик может использовать контекст регистра (ссылается `context` параметр) для выполнения собственного неуправляемого стека. В этом случае Win32 `CONTEXT` структура представляет состояние ЦП для наиболее недавно отправленных кадров в запуске неуправляемого кадра. Несмотря на то что Win32 `CONTEXT` структура включает в себя значения для всех регистров, следует полагаться только на значениях регистр указателя стека, регистр указателя фрейма, регистр указателя инструкции и постоянные (хранимые) регистры целых чисел.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Метод DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [Глобальные статические функции профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
