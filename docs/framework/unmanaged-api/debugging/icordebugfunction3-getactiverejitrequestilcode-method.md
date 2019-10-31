---
title: Метод ICorDebugFunction3::GetActiveReJitRequestILCode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
ms.openlocfilehash: 0e706861237ed08700ef0abcc424b6f1de5f462c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134644"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a>Метод ICorDebugFunction3::GetActiveReJitRequestILCode
[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Возвращает указатель интерфейса на [икордебугилкоде](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) , содержащий Il из активного запроса ReJIT.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppReJitedILCode`  
 Указатель на промежуточный язык из активного запроса ReJIT.  
  
## <a name="remarks"></a>Заметки  
 Если метод, представленный этим объектом `ICorDebugFunction3`, имеет активный запрос ReJIT, `ppReJitedILCode` возвращает указатель на его промежуточный язык. Если нет активного запроса, что является распространенным случаем, `ppReJitedILCode` имеет **значение NULL**.  
  
 Запрос ReJIT активируется сразу после того, как выполнение возвращается из вызова метода [ICorProfilerCallback4:: жетрежитпараметерс](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) . Он еще не быть может скомпилирован JIT, а потоки могут по-прежнему выполняться в исходной версии кода. Во время вызова профилировщиком метода [метод icorprofilerinfo4:: рекуестреверт](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) запрос ReJIT станет неактивным. Даже после возврата промежуточного языка поток может все еще выполняться в коде, перекомпилированном JIT (ReJIT).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugFunction3](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT: руководство](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
