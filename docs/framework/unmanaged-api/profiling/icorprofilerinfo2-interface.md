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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4623fecd210ac716824fdc5fede99ec40145e8d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498873"
---
# <a name="icorprofilerinfo2-interface"></a>Интерфейс ICorProfilerInfo2
Предоставляет методы, используемые профилировщиками кода для взаимодействия с CLR (CLR) для управления отслеживанием событий и сведения о запросе. `ICorProfilerInfo2` Интерфейс является расширением [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) интерфейс. То есть он предоставляет новые методы, поддерживаемые в .NET Framework версии 2.0 и более поздних версий.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|Обращается к стеку заданного потока для передачи кадров управляемого вызова профилировщика.|  
|[Метод EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|Получает перечислитель, позволяющий выполнять итерацию зафиксированных объектов в указанном модуле.|  
|[Метод GetAppDomainStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|Возвращает адрес указанного приложения статического поля домена, в рамках указанного домена приложения.|  
|[Метод GetArrayObjectInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|Получает подробные сведения об объекте массива.|  
|[Метод GetBoxClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|Получает сведения о структуре класса для указанного значения типа значения.|  
|[Метод GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Получает `ClassID` типа, используя указанный токен метаданных и `ClassID` значения любого типа аргументов.|  
|[Метод GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|Получает родительский модуль заданного универсального класса, маркер метаданных для класса, `ClassID` его родительского класса и `ClassID` для каждого аргумента типа, если он имеется, класса.|  
|[Метод GetClassLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|Получает сведения о макете в памяти полей, определенных с помощью указанного класса. То есть этот метод получает смещения полей класса.|  
|[Метод GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|Получает экстенты машинного кода, связанного с указанным `FunctionID`.|  
|[Метод GetContextStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|Возвращает адрес указанного поля статического контекста, в рамках заданного контекста.|  
|[Метод GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Получает `FunctionID` функции с помощью заданным токеном метаданных, содержащий класс, и `ClassID` значения любого типа аргументов.|  
|[Метод GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|Получает родительский класс, токен метаданных и `ClassID` для каждого аргумента типа функции при их наличии.|  
|[Метод GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|Получает области памяти (сегментов кучи), которые образуют поколения кучи сборщиком мусора.|  
|[Метод GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Возвращает собственные сведения о кадре и адрес для условия исключения (`catch`/`finally`/`filter`), будет выполняться или только что запущенного.|  
|[Метод GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|Возвращает сегмент кучи, который содержит указанный объект.|  
|[Метод GetRVAStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|Возвращает адрес указанного относительного виртуального адреса (RVA)-статического поля.|  
|[Метод GetStaticFieldInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|Возвращает область, в которой указанное поле является статическим.|  
|[Метод GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|Получает сведения о структуре строкового объекта.|  
|[Метод GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|Получает идентификатор домена приложения, в котором указанный поток в настоящее время выполняется код.|  
|[Метод GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|Возвращает адрес указанного поля статического потока, который находится в области заданного потока.|  
|[Метод SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Задает реализуемые профилировщиком функции, должен быть вызван в «enter», «проверить» и «tailcall» обработчиков управляемых функций.|  
  
## <a name="remarks"></a>Примечания  
 Профилировщик вызывает метод в `ICorProfilerInfo2` интерфейс для взаимодействия со средой CLR с целью управления мониторингом событий и запроса информации.  
  
 Методы `ICorProfilerInfo2` интерфейса реализуются в среде CLR, с помощью модели свободных потоков. Каждый метод возвращает значение HRESULT, указывающее на успешное выполнение или сбой. Список возможных кодов возврата см. в файле CorError.h.  
  
 Среда CLR передает `ICorProfilerInfo2` интерфейс каждому профилировщику кода во время инициализации, с помощью профилировщика реализации [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Профилировщик кода затем может вызывать методы из `ICorProfilerInfo2` интерфейса для получения сведений об управляемом коде, выполняемом под управлением среды CLR.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы профилирования](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Интерфейс ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
