---
title: Интерфейсы отладки
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b6d00d17615769a5d03d58e0eda5af62ca58368
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415966"
---
# <a name="debugging-interfaces"></a>Интерфейсы отладки
В этом разделе описываются неуправляемые интерфейсы отладки, управляющие отладкой программы, выполняемой в среде CLR.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Интерфейс ICLRDataEnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 Предоставляет метод, выполняющий перечисление областей памяти, заданной вызовами.  
  
 [Интерфейс ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 Предоставляет метод обратного вызова для метода `EnumMemoryRegions`, сообщающий отладчику результат попытки перечисления заданной области памяти.  
  
 [Интерфейс ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 Предоставляет методы для взаимодействия с целевым процессом среды CLR.  
  
 [Интерфейс ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 Подкласс `ICLRDataTarget`, используемый уровнем служб доступа к данным с целью управления областями виртуальной памяти в целевом процессе.  
  
 [Интерфейс ICLRDataTarget3](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 Подкласс [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) , обеспечивающий доступ к сведениям об исключении.  
  
 [Интерфейс ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.  
  
 [Интерфейс ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 Включает в себя [метод ProvideLibrary](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) метод, получающий интерфейс обратного вызова, который позволяет библиотеки отладки конкретной версии среды выполнения, находить и загружать по мере необходимости поставщика библиотеки.  
  
 [Интерфейс ICLRMetadataLocator](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 Интерфейс, используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.  
  
 [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR.  
  
 [Интерфейс1 ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 Предоставляет методы для отладки доменов приложения.  
  
 [Интерфейс1 ICorDebugAppDomain2](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 Предоставляет методы для работы с массивами, указателями, указателями функций и типами ByRef. Этот интерфейс является расширением интерфейса `ICorDebugAppDomain`.  
  
 [Интерфейс ICorDebugAppDomain3](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 Предоставляет методы для работы с типами [!INCLUDE[wrt](../../../../includes/wrt-md.md)] в домене приложения. Этот интерфейс является расширением интерфейса `ICorDebugAppDomain` и `ICorDebugAppDomain2`.  
  
 [Интерфейс ICorDebugAppDomain4](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 Логически расширяет [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) интерфейса для получения управляемого объекта из вызываемой оболочки COM.  
  
 [Интерфейс1 ICorDebugAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 Предоставляет метод, возвращающий заданное число значений `ICorDebugAppDomain`, начиная со следующего расположения в перечислении.  
  
 [Интерфейс1 ICorDebugArrayValue](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 Подкласс интерфейса `ICorDebugHeapValue`, представляющий одномерный или многомерный массив.  
  
 [Интерфейс1 ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 Представляет сборку.  
  
 [Интерфейс1 ICorDebugAssembly2](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 Представляет сборку. Этот интерфейс является расширением интерфейса `ICorDebugAssembly`.  
  
 [Интерфейс ICorDebugAssembly3](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 Логически расширяет [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) интерфейса для обеспечения поддержки контейнерных сборок и их вложенных сборок. **Доступно только в .NET Native.**  
  
 [Интерфейс1 ICorDebugAssemblyEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugAssembly`.  
  
 [Интерфейс ICorDebugBlockingObjectEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 Предоставляет перечислитель для списка [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры.  
  
 [Интерфейс1 ICorDebugBoxValue](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 Подкласс интерфейса `ICorDebugHeapValue`, представляющий упакованное значение объектов класса.  
  
 [Интерфейс1 ICorDebugBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 Представляет точку останова в функции или контрольную точку для значения.  
  
 [Интерфейс1 ICorDebugBreakpointEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugBreakpoint`.  
  
 [Интерфейс1 ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 Представляет сегмент физического или логического стека вызовов.  
  
 [Интерфейс1 ICorDebugChainEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugChain`.  
  
 [Интерфейс1 ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.  
  
 [Интерфейс1 ICorDebugClass2](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 Представляет универсальный класс или класс параметром метода типа <xref:System.Type>. Этот интерфейс расширяет интерфейс `ICorDebugClass`.  
  
 [Интерфейс1 ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
 [Интерфейс1 ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 Предоставляет методы, расширяющие возможности интерфейса `ICorDebugCode`.  
  
 [Интерфейс ICorDebugCode3](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 Предоставляет метод, который расширяет [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) и [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) для предоставления сведений об управляемом возвращаемом значении.  
  
 [Интерфейс ICorDebugCode4](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 Предоставляет метод, который позволяет отладчику выполнить перечисление локальных переменных и аргументов в функции.  
  
 [Интерфейс1 ICorDebugCodeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugCode`.  
  
 [Интерфейс ICorDebugComObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 Предоставляет методы для получения кэшированных объектов интерфейса.  
  
 [Интерфейс1 ICorDebugContext](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 Представляет объект контекста. Этот интерфейс еще не реализован.  
  
 [Интерфейс1 ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.  
  
 [Интерфейс ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.  
  
 [Интерфейс ICorDebugDataTarget2](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 Логически расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugDataTarget3](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 Логически расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс для предоставления сведений о загруженных модулях. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugEditAndContinueErrorInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 [Интерфейс1 ICorDebugEditAndContinueSnapshot](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 [Интерфейс1 ICorDebugEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 Служит абстрактным базовым интерфейсом для перечислителей отладки.  
  
 [Интерфейс1 ICorDebugErrorInfoEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 [Интерфейс1 ICorDebugEval](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.  
  
 [Интерфейс1 ICorDebugEval2](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 Расширяет интерфейс `ICorDebugEval` для предоставления поддержки универсальных типов.  
  
 [Интерфейс ICorDebugExceptionDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 Расширяет [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) интерфейс для поддержки событий исключения. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.  
  
 [Интерфейс ICorDebugExceptionObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 Расширяет [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) интерфейс, чтобы предоставить сведения о трассировке стека из управляемого объекта исключения.  
  
 [Интерфейс1ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 Представляет кадр текущего стека.  
  
 [Интерфейс1 ICorDebugFrameEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugFrame`.  
  
 [Интерфейс1 ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 Представляет управляемую функцию или метод.  
  
 [Интерфейс1 ICorDebugFunction2](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 Локально расширяет интерфейс `ICorDebugFunction` для предоставления поддержки отладки в пошаговом режиме "Только мой код".  
  
 [Интерфейс ICorDebugFunction3](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 Логически расширяет [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) интерфейс для предоставления доступа к коду из запроса ReJIT.  
  
 [Интерфейс1 ICorDebugFunctionBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 Расширяет интерфейс `ICorDebugBreakpoint` для поддержки точек останова в функциях.  
  
 [Интерфейс ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.  
  
 [Интерфейс1 ICorDebugGenericValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 Подкласс интерфейса `ICorDebugValue`, применяемый ко всем значениям. Этот интерфейс предоставляет для значения методы Get и Set.  
  
 [Интерфейс ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 Предоставляет перечислитель для объекта, сопоставляющего идентификаторы GUID и соответствующие объекты `ICorDebugType`.  
  
 [Интерфейс1 ICorDebugHandleValue](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 Подкласс интерфейса `ICorDebugReferenceValue`, представляющий значение ссылки, для которого отладчик создал дескриптор сборки мусора.  
  
 [Интерфейс ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 Предоставляет перечислитель для объектов в управляемой куче.  
  
 [Интерфейс ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 Предоставляет перечислитель для областей памяти управляемой кучи.  
  
 [Интерфейс1 ICorDebugHeapValue](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 Подкласс интерфейса `ICorDebugValue`, представляющий объект, подобранный сборщиком мусора среды CLR.  
  
 [Интерфейс1 ICorDebugHeapValue2](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 Расширение интерфейса `ICorDebugHeapValue`, предоставляющее поддержку дескрипторов среды выполнения.  
  
 [Интерфейс ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 Предоставляет свойства блокировки монитора объектов.  
  
 [Интерфейс ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 Представляет сегмент кода промежуточного языка.  
  
 [Интерфейс ICorDebugILCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 Логически расширяет [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) интерфейс, чтобы предоставить методы, возвращающие маркер для подписи локальной переменной функции и сопоставлены инструментированного профилировщиком промежуточного языка (IL) смещений в исходный метод IL смещения.  
  
 [Интерфейс1 ICorDebugILFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 Предоставляет кадр стека кода MSIL.  
  
 [Интерфейс1 ICorDebugILFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 Логическое расширение интерфейса `ICorDebugILFrame`.  
  
 [Интерфейс ICorDebugILFrame3](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 Предоставляет метод, инкапсулирующий возвращаемое значение функции.  
  
 [Интерфейс ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка. Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.  
  
 [Интерфейс ICorDebugInstanceFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 Представляет сведения отладочного символа для поля экземпляра. **Доступно только в .NET Native.**  
  
 [Интерфейс1 ICorDebugInternalFrame](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 Задает типы кадров для отладчика.  
  
 [Интерфейс ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 Предоставляет сведения о внутренних кадрах, включая стековый адрес и положение относительно [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) объектов.  
  
 [Интерфейс ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 Предоставляет сведения о загруженном модуле. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 Предоставляет методы для обработки обратных вызовов отладчика.  
  
 [Интерфейс ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA). Интерфейс `ICorDebugManagedCallback2` является логическим расширением интерфейса `ICorDebugManagedCallback`.  
  
 [Интерфейс ICorDebugManagedCallback3](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.  
  
 [Интерфейс ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 Представляет сообщение управляемого помощника по отладке (MDA).  
  
 [Интерфейс ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 Представляет буфер в памяти. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 Предоставляет сведения о сборке после слияния. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugMetaDataLocator](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 Предоставляет сведения о метаданных для отладчика.  
  
 [Интерфейс1 ICorDebugModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).  
  
 [Интерфейс1 ICorDebugModule2](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 Служит логическим расширением интерфейса `ICorDebugModule`.  
  
 [Интерфейс ICorDebugModule3](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 Создает средство чтения символов для динамического модуля.  
  
 [Интерфейс1 ICorDebugModuleBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 Расширяет интерфейс `ICorDebugBreakpoint` для предоставления доступа к указанным модулям.  
  
 [Интерфейс ICorDebugModuleDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 Расширяет [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) интерфейс для поддержки событий на уровне модуля. **Доступно только в .NET Native.**  
  
 [Интерфейс1 ICorDebugModuleEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugModule`.  
  
 [Интерфейс ICorDebugMutableDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 Расширяет [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс для поддержки целевых объектов изменяемых данных.  
  
 [Интерфейс1 ICorDebugNativeFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 Специализированная реализация интерфейса `ICorDebugFrame`, используемая для кадров машинного кода.  
  
 [Интерфейс ICorDebugNativeFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 Предоставляет методы, проверяющие для кадров наличие взаимоотношений типа "дочерний-родительский".  
  
 [Интерфейс1 ICorDebugObjectEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).  
  
 [Интерфейс1 ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 Подкласс `ICorDebugValue`, представляющий значение, содержащее объект.  
  
 [Интерфейс1 ICorDebugObjectValue2](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 Расширяет интерфейс `ICorDebugObjectValue` для поддержки наследования и переопределений.  
  
 [Интерфейс1 ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 Представляет процесс, выполняющий управляемый код.  
  
 [Интерфейс1 ICorDebugProcess2](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 Логическое расширение интерфейса `ICorDebugProcess`.  
  
 [Интерфейс ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 Управляет пользовательскими уведомлениями отладчика.  
  
 [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 Расширяет [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) локального интерфейса для поддержки доступа к управляемой куче, для предоставления сведений о сборке мусора управляемых объектов и для определения, загружает ли отладчик образы из приложения кэш образов в машинном коде.  
  
 [Интерфейс ICorDebugProcess6](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 Логически расширяет [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) интерфейс для включения функции, такие как декодирование событий управляемой отладки, которые кодируются в события отладки собственных исключений и разделение виртуальных модулей. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugProcess7](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 Предоставляет метод, который настраивает отладчик для обработки обновлений находящихся в памяти метаданных в целевом процессе.  
  
 [Интерфейс ICorDebugProcess8](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 Логически расширяет [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) интерфейс, чтобы включить или отключить определенные виды [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) обратных вызовов исключения.  
  
 [Интерфейс1 ICorDebugProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugProcess`.  
  
 [Интерфейс1 ICorDebugReferenceValue](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 Подкласс интерфейса `ICorDebugValue`, поддерживающего ссылочные типы.  
  
 [Интерфейс ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 Представляет набор регистров, доступных для компьютера, на котором в данный момент выполняется код.  
  
 [Интерфейс ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 Расширяет возможности интерфейса `ICorDebugRegisterSet` для аппаратных платформ, количество регистров которых превышает 64.  
  
 [Интерфейс ICorDebugRemote](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.  
  
 [Интерфейс ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 Предоставляет методы, позволяющие отлаживать приложения на основе Silverlight в среде CLR.  
  
 [Интерфейс ICorDebugRuntimeUnwindableFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.  
  
 [Интерфейс ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 Обеспечивает методы для получения управляемых методов или кадров в стеке потока.  
  
 [Интерфейс ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 Представляет сведения отладочного символа для статического поля. **Доступно только в .NET Native.**  
  
 [Интерфейс1 ICorDebugStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.  
  
 [Интерфейс1 ICorDebugStepper2](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 Предоставляет поддержку отладки "Только мой код".  
  
 [Интерфейс1 ICorDebugStepperEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugStepper`.  
  
 [Интерфейс1 ICorDebugStringValue](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 Подкласс `ICorDebugHeapValue`, применяемый к строковым значениям.  
  
 [Интерфейс ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugSymbolProvider2](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 Логически расширяет [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) интерфейс для извлечения дополнительных символов отладки. **Доступно только в .NET Native.**  
  
 [Интерфейс1 ICorDebugThread](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 Представляет поток в процессе. Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.  
  
 [Интерфейс1 ICorDebugThread2](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 Служит логическим расширением интерфейса `ICorDebugThread`.  
  
 [Интерфейс ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 Предоставляет точку входа для [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) и соответствующие интерфейсы.  
  
 [Интерфейс ICorDebugThread4](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 Предоставляет сведения о блокировке потока.  
  
 [Интерфейс1 ICorDebugThreadEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugThread`.  
  
 [Интерфейс1 ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.  
  
 [Интерфейс ICorDebugType2](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 Расширяет [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) интерфейс для извлечения идентификатора типа базового типа или сложного типа (определяемый пользователем).  
  
 [Интерфейс1 ICorDebugTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugType`.  
  
 [Интерфейс ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно со средой CLR.  
  
 "ICorDebugValue"  
 Представляет значение для записи или чтения в отлаживаемом процессе.  
  
 "ICorDebugValue2"  
 Расширяет интерфейс `ICorDebugValue` для предоставления поддержки интерфейса `ICorDebugType`.  
  
 [Интерфейс ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 Расширяет интерфейс «ICorDebugValue» и «ICorDebugValue2» для обеспечения поддержки массивов, размер которых превышает 2 ГБ.  
  
 "ICorDebugValueBreakpoint"  
 Расширяет интерфейс `ICorDebugBreakpoint` для обеспечения доступа к указанным значениям.  
  
 "ICorDebugValueEnum"  
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugValue`.  
  
 [Интерфейс ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 Представляет локальную переменную или аргумент функции.  
  
 [Интерфейс ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 Предоставляет перечислитель для локальных переменных и аргументов в функции.  
  
 [Интерфейс ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 Извлекает сведения отладочного символа для статического поля. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugVirtualUnwinder](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 Предоставляет методы, помогающие очистить стек. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 Служит универсальным интерфейсом для процессов публикации.  
  
 [Интерфейс ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 Представляет и предоставляет информацию о домене приложения.  
  
 [Интерфейс ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishAppDomain`, существующих в процессе в данный момент.  
  
 [Интерфейс ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 Служит абстрактной базой для перечислителей публикации.  
  
 [Интерфейс ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 Предоставляет методы, позволяющие получить доступ к сведениям о процессе.  
  
 [Интерфейс ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishProcess`.  

 [Интерфейс ISOSDacInterface](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md) предоставляет вспомогательные методы для доступа к данным из `SOS`.

 [Интерфейс IXCLRDataMethodDefinition](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md) предоставляет методы для запроса на получение сведений об определении метода.
 
 [Интерфейс IXCLRDataMethodInstance](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md) предоставляет методы для запроса на получение сведений о экземпляра метода.
 
 [Интерфейс IXCLRDataModule](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md) предоставляет методы для запроса на получение сведений о загруженном модуле.
 
 [Интерфейс IXCLRDataProcess](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md) предоставляет методы для запроса на получение сведений о процессе.
  
## <a name="related-sections"></a>Связанные разделы  
 [Коклассы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
