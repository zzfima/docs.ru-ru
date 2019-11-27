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
ms.openlocfilehash: 62035d623d56f7521e0a599a13bc20778e3f18d1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449904"
---
# <a name="icorprofilercallbackjitinlining-method"></a>Метод ICorProfilerCallback::JITInlining
Уведомляет профилировщик о том, что JIT-компилятор собирается вставить функцию в строку с другой функцией.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a>Параметры  
 `callerId`  
 окне Идентификатор функции, в которую будет вставлена функция `calleeId`.  
  
 `calleeId`  
 окне Идентификатор вставляемой функции.  
  
 `pfShouldInline`  
 [out] `true`, чтобы разрешить вставку; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Профилировщик может установить `pfShouldInline` `false`, чтобы функция `calleeId` не была вставлена в функцию `callerId`. Кроме того, профилировщик может глобально отключить встроенную вставку, используя значение COR_PRF_DISABLE_INLINING перечисления [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) .  
  
 Встроенные функции не вызывают события для входа или вставки. Таким образом, профилировщик должен задать `pfShouldInline` для `false`, чтобы получить точную граф вызовов. Установка `pfShouldInline` `false` влияет на производительность, так как встроенная вставка обычно увеличивает скорость и сокращает число отдельных событий JIT-компиляции для метода inserted.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
