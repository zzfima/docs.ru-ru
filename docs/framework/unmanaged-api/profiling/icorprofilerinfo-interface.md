---
title: Интерфейс ICorProfilerInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo
helpviewer_keywords:
- ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: eb4e4ce0-06e7-4469-bbc4-edc2eb5da4b1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da5a041e8a18420b4cf9962e4315683be8857711
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo-interface"></a>Интерфейс ICorProfilerInfo
Предоставляет методы для использования профилировщиками кода для взаимодействия с общеязыковой среды выполнения (CLR), целью управления мониторингом событий и запроса информации.  
  
> [!NOTE]
>  Каждый метод в `ICorProfilerInfo` интерфейса возвращает значение HRESULT, которое указывает успешность или сбой. Список возможных кодов возврата см. CorError.h.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)|Инициализирует внутрипроцессную поддержку отладки. Этот метод является устаревшим в .NET Framework версии 2.0.|  
|[Метод EndInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-endinprocdebugging-method.md)|Завершает работу сеанса в процессе отладки. Этот метод является устаревшим в .NET Framework версии 2.0.|  
|[Метод ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)|Принудительно начинает сборку мусора в среде выполнения.|  
|[Метод GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)|Получает сведения о заданный домен приложения.|  
|[Метод GetAssemblyInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getassemblyinfo-method.md)|Возвращает сведения об указанной сборки.|  
|[Метод GetClassFromObject](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromobject-method.md)|Возвращает `ClassID` из<br /><br /> Объект, которому передан его `ObjectID`.|  
|[Метод GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)|Получает идентификатор класса, получает маркер метаданных. Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) метод вместо него.|  
|[Метод GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)|Получает родительский модуль и токен метаданных для указанного класса.|  
|[Метод GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)|Получает экстент машинного кода, связанного с указанным идентификатором функции. Этот метод устарел. Используйте [ICorProfilerInfo2::GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) метод вместо него.|  
|[Метод GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)|Получает идентификатор текущего потока, если это управляемого потока.|  
|[Метод GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)|Получает текущие категории событий, для которых профилировщик хочет получать уведомления о событиях от среды CLR.|  
|[Метод GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)|Сопоставляет указатель инструкции управляемого кода `FunctionID`.|  
|[Метод GetFunctionFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromtoken-method.md)|Получает идентификатор функции. Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) метод вместо него.|  
|[Метод GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)|Получает родительский класс и токен метаданных для указанной функции.|  
|[Метод GetHandleFromThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gethandlefromthread-method.md)|Сопоставляет идентификатор потока дескриптору потока Win32.|  
|[Метод GetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md)|Возвращает указатель на основной части метода в код MSIL (MSIL), начиная с его заголовка.|  
|[Метод GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)|Возвращает интерфейс, предоставляющий метод выделения памяти, используемый для замены тела метода в коде MSIL.|  
|[Метод GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)|Получает сопоставление из смещений MSIL в собственные смещения для кода, содержащегося в указанной функции.|  
|[Метод GetInprocInspectionInterface](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectioninterface-method.md)|Возвращает объект, который может запрашиваться для ICorDebugProcess-интерфейс. Этот метод является устаревшим в .NET Framework версии 2.0.|  
|[Метод GetInprocInspectionIThisThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectionithisthread-method.md)|Возвращает объект, который может запрашиваться для ICorDebugThread-интерфейс. Этот метод является устаревшим в .NET Framework версии 2.0.|  
|[Метод GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)|Возвращает имя файла модуля и идентификатор его родительской сборки для указанного идентификатора модуля.|  
|[Метод GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)|Получает экземпляр интерфейса метаданных, сопоставляемый с указанным модулем.|  
|[Метод GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)|Возвращает размер указанного объекта.|  
|[Метод GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)|Возвращает идентификатор контекста, в текущий момент связан с указанным потоком.|  
|[Метод GetThreadInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadinfo-method.md)|Получает текущую идентификацию потока Win32 для указанного потока.|  
|[Метод GetTokenAndMetadataFromFunction](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gettokenandmetadatafromfunction-method.md)|Получает маркер метаданных и экземпляр интерфейса метаданных, который может использоваться в отношении маркера для указанной функции.|  
|[Метод IsArrayClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)|Определяет, является ли указанный класс классом массива.|  
|[Метод SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)|Задает реализуемые профилировщиком функции, вызываемого при «введите», «оставьте» и «tailcall» обработчиках управляемых функций.|  
|[Метод SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)|Задает значение, указывающее типы событий, для которых профилировщик хочет получать уведомления от среды CLR.|  
|[Метод SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)|Задает реализуемую профилировщиком функцию, которая будет вызвана для сопоставления значений `FunctionID` с альтернативными значениями, передаваемыми обработчикам входа и выхода для функции профилировщика.|  
|[Метод SetFunctionReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionrejit-method.md)|Не реализовано. Не используется.|  
|[Метод SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)|Заменяет тело указанной функции в указанном модуле.|  
|[Метод SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)|Задает способ сопоставления смещения исходного MSIL указанной функции с новыми смещениями изменяемого профилировщиком MSIL функции.|  
  
## <a name="remarks"></a>Примечания  
 Профилировщик вызывает метод в `ICorProfilerInfo` интерфейс для взаимодействия со средой CLR с целью управления мониторингом событий и запроса информации.  
  
 Методы `ICorProfilerInfo` интерфейса реализуются с помощью модели свободных потоков среды CLR. Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой. Список возможных кодов возврата см. CorError.h.  
  
 Среда CLR передает через реализацию профилировщика [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md), `ICorProfilerInfo` интерфейс каждому профилировщику кода во время инициализации. Профилировщик кода затем может вызывать методы `ICorProfilerInfo` интерфейса для получения информации об управляемом коде, выполняемом под управлением среды CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
