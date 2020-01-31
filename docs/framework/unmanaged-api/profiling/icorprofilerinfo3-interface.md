---
title: Интерфейс ICorProfilerInfo3
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3
helpviewer_keywords:
- ICorProfilerInfo3 interface [.NET Framework profiling]
ms.assetid: 044a262f-0fa7-485d-b0c1-64cdc359c654
topic_type:
- apiref
ms.openlocfilehash: c3642154ba5f9798f59ca8fc49cb848d7e2f73c7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862234"
---
# <a name="icorprofilerinfo3-interface"></a>Интерфейс ICorProfilerInfo3
Предоставляет методы, используемые профилировщиками кода для обмена данными со средой CLR с целью управления мониторингом событий и запроса информации. Интерфейс `ICorProfilerInfo3` является расширением интерфейса [ICorProfilerInfo2](icorprofilerinfo2-interface.md) . Он предоставляет новые методы, поддерживаемые в .NET Framework 4 и более поздних версий.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md)|Возвращает перечислитель для всех функций, скомпилированных ранее для JIT-отладки.|  
|[Метод EnumModules](icorprofilerinfo3-enummodules-method.md)|Возвращает перечислитель, предоставляющий методы для последовательного перебора коллекции управляемых модулей, загруженных в приложение.|  
|[Метод GetAppDomainsContainingModule](icorprofilerinfo3-getappdomainscontainingmodule-method.md)|Возвращает идентификаторы доменов приложений, в которые был загружен указанный модуль.|  
|[Метод GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md)|Предоставляет кадр стека и сведения о аргументах функции, о которой сообщается профилировщику функцией [FunctionEnter3WithInfo](functionenter3withinfo-function.md) . может вызываться только во время обратного вызова `FunctionEnter3WithInfo`.|  
|[Метод GetFunctionLeave3Info](icorprofilerinfo3-getfunctionleave3info-method.md)|Предоставляет кадр стека и возвращаемое значение функции, о которой сообщается профилировщику функцией [функции FunctionLeave3WithInfo](functionleave3withinfo-function.md) . может вызываться только во время обратного вызова `FunctionLeave3WithInfo`.|  
|[Метод GetFunctionTailcall3Info](icorprofilerinfo3-getfunctiontailcall3info-method.md)|Предоставляет кадр стека функции, о которой сообщается профилировщику функцией [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) . может вызываться только во время обратного вызова `FunctionTailcall3WithInfo`.|  
|[Метод GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md)|Возвращает имя файла модуля, идентификатор родительской сборки модуля и битовую маску, описывающую свойства модуля, по идентификатору модуля.|  
|[Метод GetRuntimeInformation](icorprofilerinfo3-getruntimeinformation-method.md)|Предоставляет информацию о версии среды выполнения, для которой производится профилирование.|  
|[Метод GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md)|Получает сведения о структуре строкового объекта.|  
|[Метод GetThreadStaticAddress2](icorprofilerinfo3-getthreadstaticaddress2-method.md)|Возвращает адрес указанного поля статического потока, которое находится в области действия заданного потока и домена приложения.|  
|[Метод RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md)|Дает среде выполнения команду на отключение профилировщика.|  
|[Метод SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)|Задает реализованные профилировщиком функции, которые будут вызываться для функций [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)и [FunctionTailcall3](functiontailcall3-function.md) .|  
|[Метод SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)|Задает реализованные профилировщиком функции, которые будут вызываться для обработчиков [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)и [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) управляемых функций.|  
|[Метод SetFunctionIDMapper2](icorprofilerinfo3-setfunctionidmapper2-method.md)|Задает реализуемую профилировщиком функцию, которая будет вызвана для сопоставления значений `FunctionID` с альтернативными значениями, передаваемыми обработчикам входа и выхода для функции профилировщика. Этот метод расширяет [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) с параметром, который профилировщики могут использовать для устранения неоднозначности между средами выполнения.|  
  
## <a name="remarks"></a>Заметки  
 Среда CLR реализует методы интерфейса `ICorProfilerInfo3` с помощью модели свободных потоков. Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой. Список возможных кодов возврата см. в файле CorError.h.  
  
 Среда CLR передает `ICorProfilerInfo3` интерфейс в каждый профилировщик кода во время инициализации, используя реализацию метода [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) или [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) в профилировщике. Профилировщик кода затем может вызывать методы `ICorProfilerInfo3` для получения информации об управляемом коде, выполняемом под управлением среды CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы профилирования](profiling-interfaces.md)
- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
