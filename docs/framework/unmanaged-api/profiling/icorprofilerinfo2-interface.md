---
title: "Интерфейс ICorProfilerInfo2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2
helpviewer_keywords: ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: 91bd49b6-4d12-494f-a8f1-2f251e8c65e3
topic_type: apiref
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cbc0b4ad46c6a49313a42c4c232873988e7f4e99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2-interface"></a>Интерфейс ICorProfilerInfo2
Предоставляет методы, используемые профилировщиками кода для взаимодействия с CLR (CLR) и управления мониторингом событий и сведения о запросе. `ICorProfilerInfo2` Интерфейс является расширением [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) интерфейса. То есть он предоставляет новые методы, поддерживаемые в .NET Framework версии 2.0 и более поздних версиях.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|Выполняет обход стека заданного потока для сообщения о кадрах управляемого вызова профилировщика.|  
|[Метод EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|Возвращает перечислитель, позволяющий выполнять итерацию по замороженным объектам в указанном модуле.|  
|[Метод GetAppDomainStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|Получает адрес поля статического домена указанное приложение, которое находится в области указанного домена приложения.|  
|[Метод GetArrayObjectInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|Получает подробные сведения об объекте массива.|  
|[Метод GetBoxClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|Возвращает сведения о структуре класса для указанного значения типа значения.|  
|[Метод GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Возвращает `ClassID` типа, используя указанный токен метаданных и `ClassID` значения любого типа аргументов.|  
|[Метод GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|Получает родительский модуль заданного универсального класса, токен метаданных для класса, `ClassID` его родительского класса и `ClassID` для каждого аргумента типа, если имеется этого класса.|  
|[Метод GetClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|Получает сведения о макете в памяти полей, определенных с помощью указанного класса. То есть этот метод получает смещения полей класса.|  
|[Метод GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|Получает экстенты машинного кода, связанного с указанным `FunctionID`.|  
|[Метод GetContextStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|Возвращает адрес указанного поля статического контекста, который находится в области заданного контекста.|  
|[Метод GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Возвращает `FunctionID` функции, используя указанный токен метаданных, содержащий класс, и `ClassID` значения любого типа аргументов.|  
|[Метод GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|Получает родительский класс, токен метаданных и `ClassID` для каждого аргумента типа функции при их наличии.|  
|[Метод GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|Получает области памяти (сегменты кучи), составляющих поколений в куче сбора мусора.|  
|[Метод GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Получает собственный сведения о кадре и адрес для предложения исключения (`catch`/`finally`/`filter`), будет выполняться, или только что запущенного.|  
|[Метод GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|Возвращает сегмент кучи, содержащей указанный объект.|  
|[Метод GetRVAStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|Возвращает адрес указанного относительного виртуального адреса (RVA)-статического поля.|  
|[Метод GetStaticFieldInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|Возвращает область, в которой заданное поле является статическим.|  
|[Метод GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|Получает сведения о структуре строкового объекта.|  
|[Метод GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|Получает идентификатор домена приложения, в котором заданный поток в данный момент выполняется код.|  
|[Метод GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|Возвращает адрес указанного поля статического потока, которое находится в области действия заданного потока.|  
|[Метод SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Задает реализуемые профилировщиком функции, вызываемого при «введите», «оставьте» и «tailcall» обработчиках управляемых функций.|  
  
## <a name="remarks"></a>Примечания  
 Профилировщик вызывает метод в `ICorProfilerInfo2` интерфейс для взаимодействия со средой CLR с целью управления мониторингом событий и запроса информации.  
  
 Методы `ICorProfilerInfo2` интерфейса реализуются с помощью модели свободных потоков среды CLR. Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой. Список возможных кодов возврата см. в файле CorError.h.  
  
 Среда CLR передает `ICorProfilerInfo2` интерфейс каждому профилировщику кода во время инициализации, используя реализацию профилировщика [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Профилировщик кода затем может вызывать методы `ICorProfilerInfo2` интерфейса для получения информации об управляемом коде, выполняемом под управлением среды CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo-интерфейс](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
