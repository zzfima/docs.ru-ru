---
title: Метод ICorProfilerCallback::JITInlining
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 844ac2a8aad4ce2cc6f70de2d5a53c7c0b6f4f6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackjitinlining-method"></a>Метод ICorProfilerCallback::JITInlining
Уведомляет профилировщик, что время JIT-компилятор намерен вставить функцию в одну строку другой функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
#### <a name="parameters"></a>Параметры  
 `callerId`  
 [in] Идентификатор функции, в которую `calleeId` функции будут вставлены.  
  
 `calleeId`  
 [in] Идентификатор функции для вставки.  
  
 `pfShouldInline`  
 [out] `true` на разрешение вставки синхронизации; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Можно задать профилировщик `pfShouldInline` для `false` для предотвращения `calleeId` функции из, вставляемого в `callerId` функции. Кроме того, профилировщик глобально можно отключить встроенные вставки с помощью значения COR_PRF_DISABLE_INLINING [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.  
  
 Встроенные функции не вызывают событий входа или выхода. Таким образом, профилировщик должен установить `pfShouldInline` для `false` чтобы обеспечить точность графа. Установка `pfShouldInline` для `false` повлияет на производительность, так как встроенный вставки повышается скорость и сокращает число отдельных событий JIT-компиляции для вставляемого метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
