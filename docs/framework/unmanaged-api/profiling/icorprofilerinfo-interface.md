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
ms.openlocfilehash: b979b5f4ee849b96cd29b6c8e2e6a8932e88c182
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049561"
---
# <a name="icorprofilerinfo-interface"></a>Интерфейс ICorProfilerInfo
Предоставляет методы для использования профилировщиками кода для взаимодействия с общеязыковой среды выполнения (CLR) для управления отслеживанием событий и запроса информации.  
  
> [!NOTE]
>  Каждый метод в `ICorProfilerInfo` интерфейс возвращает значение HRESULT, чтобы указать успех или неудачу. См. в разделе CorError.h список возможных кодов возврата.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)|Инициализирует внутрипроцессную поддержку отладки. Этот метод является устаревшим в .NET Framework версии 2.0.|  
|[Метод EndInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-endinprocdebugging-method.md)|Завершает сеанс отладки в процессе. Этот метод является устаревшим в .NET Framework версии 2.0.|  
|[Метод ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)|Принудительно запускает сборку мусора в среде выполнения.|  
|[Метод GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)|Получает сведения о указанного домена приложения.|  
|[Метод GetAssemblyInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getassemblyinfo-method.md)|Возвращает сведения об указанной сборки.|  
|[Метод GetClassFromObject](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromobject-method.md)|Получает `ClassID` из<br /><br /> Объект, которому передан его `ObjectID`.|  
|[Метод GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)|Получает идентификатор класса, заданным токеном метаданных. Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) метод вместо этого.|  
|[Метод GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)|Получает родительский модуль и маркер метаданных для указанного класса.|  
|[Метод GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)|Получает экстент машинного кода, связанного с указанным идентификатором функции. Этот метод устарел. Используйте [ICorProfilerInfo2::GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) метод вместо этого.|  
|[Метод GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)|Получает идентификатор текущего потока, в случае управляемого потока.|  
|[Метод GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)|Получает текущие категории событий, для которых профилировщик хочет получать уведомления о событиях от среды CLR.|  
|[Метод GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)|Сопоставляет указатель инструкции управляемого кода на `FunctionID`.|  
|[Метод GetFunctionFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromtoken-method.md)|Получает идентификатор функции. Этот метод является устаревшим в .NET Framework версии 2.0. Используйте [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) метод вместо этого.|  
|[Метод GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)|Получает маркер родительского класса и метаданные для указанной функции.|  
|[Метод GetHandleFromThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gethandlefromthread-method.md)|Сопоставляет идентификатор потока, поток Win32-дескриптором.|  
|[Метод GetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md)|Получает указатель в теле метода в код MSIL (MSIL), начиная с его заголовка.|  
|[Метод GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)|Возвращает интерфейс, который предоставляет метод для выделения памяти, используемый для замены в тело метода в коде MSIL.|  
|[Метод GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)|Получает сопоставление из смещений MSIL в собственные смещения для кода, содержащегося в указанной функции.|  
|[Метод GetInprocInspectionInterface](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectioninterface-method.md)|Возвращает объект, который можно запросить для интерфейс ICorDebugProcess. Этот метод является устаревшим в .NET Framework версии 2.0.|  
|[Метод GetInprocInspectionIThisThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectionithisthread-method.md)|Получает объект, который можно запросить для ICorDebugThread-интерфейс. Этот метод является устаревшим в .NET Framework версии 2.0.|  
|[Метод GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)|Возвращает имя файла модуля и идентификатор его родительской сборки для указанного идентификатора модуля.|  
|[Метод GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)|Получает экземпляр интерфейса метаданных, который сопоставляется указанного модуля.|  
|[Метод GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)|Возвращает размер указанного объекта.|  
|[Метод GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)|Получает идентификатор контекста ассоциированы с указанным потоком.|  
|[Метод GetThreadInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadinfo-method.md)|Возвращает удостоверение текущего потока Win32 для указанного потока.|  
|[Метод GetTokenAndMetadataFromFunction](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gettokenandmetadatafromfunction-method.md)|Получает маркер метаданных и экземпляр интерфейса метаданных, который может использоваться в отношении маркера для указанной функции.|  
|[Метод IsArrayClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)|Определяет, является ли указанный класс класса массива.|  
|[Метод SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)|Задает реализуемые профилировщиком функции, должен быть вызван в «enter», «проверить» и «tailcall» обработчиков управляемых функций.|  
|[Метод SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)|Задает значение, указывающее типы событий, для которых профилировщик хочет получать уведомления от среды CLR.|  
|[Метод SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)|Задает реализуемую профилировщиком функцию, которая будет вызвана для сопоставления значений `FunctionID` с альтернативными значениями, передаваемыми обработчикам входа и выхода для функции профилировщика.|  
|[Метод SetFunctionReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionrejit-method.md)|Не реализовано. Не используется.|  
|[Метод SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)|Заменяет текст в указанном модуле указанной функции.|  
|[Метод SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)|Указывает, как смещения исходного MSIL указанной функции сопоставляются с новыми смещениями изменяемого профилировщиком MSIL функции.|  
  
## <a name="remarks"></a>Примечания  
 Профилировщик вызывает метод в `ICorProfilerInfo` интерфейс для взаимодействия со средой CLR с целью управления мониторингом событий и запроса информации.  
  
 Методы `ICorProfilerInfo` интерфейса реализуются в среде CLR, с помощью модели свободных потоков. Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой. См. в разделе CorError.h список возможных кодов возврата.  
  
 Среда CLR передает с помощью профилировщика реализация [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md), `ICorProfilerInfo` интерфейс каждому профилировщику кода во время инициализации. Профилировщик кода затем может вызывать методы из `ICorProfilerInfo` интерфейса для получения сведений об управляемом коде, выполняемом под управлением среды CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Интерфейс ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
