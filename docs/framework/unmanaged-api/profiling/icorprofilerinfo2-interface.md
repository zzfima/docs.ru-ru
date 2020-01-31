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
ms.openlocfilehash: 23fd44a6865b0487296f3ade37c1219e8feba288
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862585"
---
# <a name="icorprofilerinfo2-interface"></a>Интерфейс ICorProfilerInfo2
Предоставляет методы, используемые профилировщиками кода для взаимодействия со средой CLR для управления мониторингом событий и сведениями о запросах. Интерфейс `ICorProfilerInfo2` является расширением интерфейса [ICorProfilerInfo](icorprofilerinfo-interface.md) . То есть он предоставляет новые методы, поддерживаемые в .NET Framework версии 2,0 и более поздних версиях.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)|Проходит по стеку указанного потока для передачи кадров управляемого вызова профилировщику.|  
|[Метод EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md)|Возвращает перечислитель, позволяющий выполнять итерацию зафиксированных объектов в указанном модуле.|  
|[Метод GetAppDomainStaticAddress](icorprofilerinfo2-getappdomainstaticaddress-method.md)|Возвращает адрес указанного поля статического домена приложения, которое находится в области заданного домена приложения.|  
|[Метод GetArrayObjectInfo](icorprofilerinfo2-getarrayobjectinfo-method.md)|Возвращает подробные сведения об объекте массива.|  
|[Метод GetBoxClassLayout](icorprofilerinfo2-getboxclasslayout-method.md)|Возвращает сведения о макете класса для указанного типа значения, который является упакованным.|  
|[Метод GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Возвращает `ClassID` типа, используя указанный токен метаданных и `ClassID` значения любых аргументов типа.|  
|[Метод GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md)|Возвращает родительский модуль указанного универсального класса, маркер метаданных для класса, `ClassID` родительского класса и `ClassID` для каждого аргумента типа, если он имеется, класса.|  
|[Метод GetClassLayout](icorprofilerinfo2-getclasslayout-method.md)|Получает сведения о макете в памяти полей, определенных с помощью указанного класса. То есть этот метод получает смещения полей класса.|  
|[Метод GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md)|Получает экстенты машинного кода, связанного с указанным `FunctionID`.|  
|[Метод GetContextStaticAddress](icorprofilerinfo2-getcontextstaticaddress-method.md)|Возвращает адрес указанного статического поля контекста, который находится в области заданного контекста.|  
|[Метод GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Возвращает `FunctionID` функции с помощью указанного маркера метаданных, содержащего класс, и `ClassID` значений любых аргументов типа.|  
|[Метод GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)|Получает родительский класс, токен метаданных и `ClassID` для каждого аргумента типа функции при их наличии.|  
|[Метод GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md)|Возвращает области памяти (сегменты кучи), составляющие поколения кучи, в которой создается мусор.|  
|[Метод GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Получает сведения о машинном адресе и кадре для предложения исключения (`catch`/`finally`/`filter`), которое будет выполняться или только что было запущено.|  
|[Метод GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md)|Возвращает сегмент кучи, который содержит указанный объект.|  
|[Метод GetRVAStaticAddress](icorprofilerinfo2-getrvastaticaddress-method.md)|Возвращает адрес указанного статического поля (относительного виртуального адреса (RVA)).|  
|[Метод GetStaticFieldInfo](icorprofilerinfo2-getstaticfieldinfo-method.md)|Возвращает область, в которой указанное поле является статическим.|  
|[Метод GetStringLayout](icorprofilerinfo2-getstringlayout-method.md)|Получает сведения о структуре строкового объекта.|  
|[Метод GetThreadAppDomain](icorprofilerinfo2-getthreadappdomain-method.md)|Возвращает идентификатор домена приложения, в котором указанный поток в настоящий момент исполняет код.|  
|[Метод GetThreadStaticAddress](icorprofilerinfo2-getthreadstaticaddress-method.md)|Возвращает адрес указанного статического поля потока, который находится в области заданного потока.|  
|[Метод SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Задает реализованные профилировщиком функции, которые должны вызываться для обработчиков "Ввод", "Leave" и "таилкалл" управляемых функций.|  
  
## <a name="remarks"></a>Заметки  
 Профилировщик вызывает метод в интерфейсе `ICorProfilerInfo2`, чтобы взаимодействовать со средой CLR для управления мониторингом событий и сведениями о запросах.  
  
 Методы интерфейса `ICorProfilerInfo2` реализуются средой CLR с помощью модели свободных потоков. Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой. Список возможных кодов возврата см. в файле CorError.h.  
  
 Среда CLR передает `ICorProfilerInfo2` интерфейс в каждый профилировщик кода во время инициализации, используя реализацию метода [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)профилировщика. Затем профилировщик кода может вызвать методы интерфейса `ICorProfilerInfo2`, чтобы получить сведения об управляемом коде, выполняемом под управлением среды CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы профилирования](profiling-interfaces.md)
- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
