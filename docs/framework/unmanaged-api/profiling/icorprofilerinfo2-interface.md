---
title: Интерфейс ICorProfilerInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2
helpviewer_keywords:
- ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: 91bd49b6-4d12-494f-a8f1-2f251e8c65e3
topic_type:
- apiref
ms.openlocfilehash: fdac9eedb0ae442d6dd2646859cab13398020a87
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449771"
---
# <a name="icorprofilerinfo2-interface"></a>Интерфейс ICorProfilerInfo2
Provides methods that code profilers use to communicate with the common language runtime (CLR) to control event monitoring and request information. The `ICorProfilerInfo2` interface is an extension of the [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface. That is, it provides new methods supported in the .NET Framework version 2.0 and later versions.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|Walks the stack of the specified thread to report managed call frames to the profiler.|  
|[Метод EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|Gets an enumerator that allows iteration over the frozen objects in the specified module.|  
|[Метод GetAppDomainStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|Gets the address of the specified application domain-static field that is in the scope of the specified application domain.|  
|[Метод GetArrayObjectInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|Gets detailed information about an array object.|  
|[Метод GetBoxClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|Gets information about the class layout for a specified value type that is boxed.|  
|[Метод GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.|  
|[Метод GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|Gets the parent module of the specified generic class, the metadata token for the class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.|  
|[Метод GetClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|Получает сведения о макете в памяти полей, определенных с помощью указанного класса. То есть этот метод получает смещения полей класса.|  
|[Метод GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|Получает экстенты машинного кода, связанного с указанным `FunctionID`.|  
|[Метод GetContextStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|Gets the address of the specified context-static field that is in the scope of the specified context.|  
|[Метод GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Gets the `FunctionID` of a function by using the specified metadata token, containing class, and `ClassID` values of any type arguments.|  
|[Метод GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|Получает родительский класс, токен метаданных и `ClassID` для каждого аргумента типа функции при их наличии.|  
|[Метод GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|Gets the memory regions (the segments of the heap) that make up the generations of the garbage-collected heap.|  
|[Метод GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.|  
|[Метод GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|Gets the segment of the heap that contains the specified object.|  
|[Метод GetRVAStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|Gets the address of the specified relative virtual address (RVA)-static field.|  
|[Метод GetStaticFieldInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|Gets the scope in which the specified field is static.|  
|[Метод GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|Получает сведения о структуре строкового объекта.|  
|[Метод GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|Gets the ID of the application domain in which the specified thread is currently executing code.|  
|[Метод GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|Gets the address of the specified thread-static field that is in the scope of the specified thread.|  
|[Метод SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.|  
  
## <a name="remarks"></a>Заметки  
 A profiler calls a method in the `ICorProfilerInfo2` interface to communicate with the CLR to control event monitoring and request information.  
  
 The methods of the `ICorProfilerInfo2` interface are implemented by the CLR using the free-threaded model. Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой. Список возможных кодов возврата см. в файле CorError.h.  
  
 The CLR passes an `ICorProfilerInfo2` interface to each code profiler during initialization, using the profiler's implementation of [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). A code profiler can then call methods of the `ICorProfilerInfo2` interface to get information about managed code being executed under the control of the CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
