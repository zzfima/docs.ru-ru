---
title: Интерфейс ICorProfilerInfo4
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4
helpviewer_keywords:
- ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 80a5308e-c22f-4201-ba89-31cc8562515b
topic_type:
- apiref
ms.openlocfilehash: cbd7c0d8fff55766a98e727ce22c77dd5214611b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448004"
---
# <a name="icorprofilerinfo4-interface"></a>Интерфейс ICorProfilerInfo4
Предоставляет методы, используемые профилировщиками кода для взаимодействия со средой CLR для управления мониторингом событий и сведениями о запросах. . Интерфейс `ICorProfilerInfo4` является расширением других интерфейсов `ICorProfilerInfo`. Он предоставляет новые методы для поддержки повторной компиляции JIT, добавленной в .NET Framework 4,5.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)|Возвращает перечислитель для всех функций, которые были ранее скомпилированы JIT-компилятором и повторно скомпилированы.|  
|[Метод EnumThreads](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumthreads-method.md)|Возвращает перечислитель, предоставляющий методы для последовательного прохода по коллекции всех управляемых потоков в процессе профилирования.|  
|[Метод GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)|Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.|  
|[Метод GetFunctionFromIP2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getfunctionfromip2-method.md)|Сопоставляет указатель инструкции управляемого кода с JIT-повторно скомпилированной версией указанной функции.|  
|[Метод GetILToNativeMapping2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getiltonativemapping2-method.md)|Возвращает карту из смещений MSIL к собственным смещениям для кода, содержащегося в JIT-повторно скомпилированной версии указанной функции.|  
|[Метод GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md)|Возвращает размер указанного объекта.|  
|[Метод GetReJITIDs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getrejitids-method.md)|Возвращает массив идентификаторов, которые определяют все все повторно скомпилированные версии указанной функции, которые все еще выделены.|  
|[Метод InitializeCurrentThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-initializecurrentthread-method.md)|Инициализирует текущий поток перед последовательными вызовами API профилировщика в том же потоке, что позволяет избежать взаимоблокировки.|  
|[Метод RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md)|Запрашивает перекомпиляцию JIT всех экземпляров указанных функций.|  
|[Метод RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)|Восстанавливает исходные версии всех экземпляров указанных функций.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR реализует методы интерфейса `ICorProfilerInfo4` с помощью модели свободных потоков. Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой. Список возможных кодов возврата см. в файле CorError.h.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
