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
Предоставляет методы, используемые профилировщиками кода для взаимодействия со средой CLR для управления мониторингом событий и сведениями о запросах. Интерфейс `ICorProfilerInfo2` является расширением интерфейса [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) . То есть он предоставляет новые методы, поддерживаемые в .NET Framework версии 2,0 и более поздних версиях.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|Проходит по стеку указанного потока для передачи кадров управляемого вызова профилировщику.|  
|[Метод EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|Возвращает перечислитель, позволяющий выполнять итерацию зафиксированных объектов в указанном модуле.|  
|[Метод GetAppDomainStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|Возвращает адрес указанного поля статического домена приложения, которое находится в области заданного домена приложения.|  
|[Метод GetArrayObjectInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|Возвращает подробные сведения об объекте массива.|  
|[Метод GetBoxClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|Возвращает сведения о макете класса для указанного типа значения, который является упакованным.|  
|[Метод GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Возвращает `ClassID` типа, используя указанный токен метаданных и `ClassID` значения любых аргументов типа.|  
|[Метод GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|Возвращает родительский модуль указанного универсального класса, маркер метаданных для класса, `ClassID` родительского класса и `ClassID` для каждого аргумента типа, если он имеется, класса.|  
|[Метод GetClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|Получает сведения о макете в памяти полей, определенных с помощью указанного класса. То есть этот метод получает смещения полей класса.|  
|[Метод GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|Получает экстенты машинного кода, связанного с указанным `FunctionID`.|  
|[Метод GetContextStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|Возвращает адрес указанного статического поля контекста, который находится в области заданного контекста.|  
|[Метод GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Возвращает `FunctionID` функции с помощью указанного маркера метаданных, содержащего класс, и `ClassID` значений любых аргументов типа.|  
|[Метод GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|Получает родительский класс, токен метаданных и `ClassID` для каждого аргумента типа функции при их наличии.|  
|[Метод GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|Возвращает области памяти (сегменты кучи), составляющие поколения кучи, в которой создается мусор.|  
|[Метод GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Получает сведения о машинном адресе и кадре для предложения исключения (`catch`/`finally`/`filter`), которое будет выполняться или только что было запущено.|  
|[Метод GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|Возвращает сегмент кучи, который содержит указанный объект.|  
|[Метод GetRVAStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|Возвращает адрес указанного статического поля (относительного виртуального адреса (RVA)).|  
|[Метод GetStaticFieldInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|Возвращает область, в которой указанное поле является статическим.|  
|[Метод GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|Получает сведения о структуре строкового объекта.|  
|[Метод GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|Возвращает идентификатор домена приложения, в котором указанный поток в настоящий момент исполняет код.|  
|[Метод GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|Возвращает адрес указанного статического поля потока, который находится в области заданного потока.|  
|[Метод SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Задает реализованные профилировщиком функции, которые должны вызываться для обработчиков "Ввод", "Leave" и "таилкалл" управляемых функций.|  
  
## <a name="remarks"></a>Примечания  
 Профилировщик вызывает метод в интерфейсе `ICorProfilerInfo2`, чтобы взаимодействовать со средой CLR для управления мониторингом событий и сведениями о запросах.  
  
 Методы интерфейса `ICorProfilerInfo2` реализуются средой CLR с помощью модели свободных потоков. Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой. Список возможных кодов возврата см. в файле CorError.h.  
  
 Среда CLR передает `ICorProfilerInfo2` интерфейс в каждый профилировщик кода во время инициализации, используя реализацию метода [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)профилировщика. Затем профилировщик кода может вызвать методы интерфейса `ICorProfilerInfo2`, чтобы получить сведения об управляемом коде, выполняемом под управлением среды CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
