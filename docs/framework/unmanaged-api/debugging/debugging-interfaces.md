---
title: Интерфейсы отладки
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afa4e6cd4e99540030d3a9e151da4bbe711d973a
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219832"
---
# <a name="debugging-interfaces"></a>Интерфейсы отладки
В этом разделе описываются неуправляемые интерфейсы отладки, управляющие отладкой программы, выполняемой в среде CLR.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Интерфейс ICLRDataEnumMemoryRegions](iclrdataenummemoryregions-interface.md)\
 Предоставляет метод, выполняющий перечисление областей памяти, заданной вызовами.  
  
 [Интерфейс ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)\
 Предоставляет метод обратного вызова для метода `EnumMemoryRegions`, сообщающий отладчику результат попытки перечисления заданной области памяти.  
  
 [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)\
 Предоставляет методы для взаимодействия с целевым процессом среды CLR.  
  
 [Интерфейс ICLRDataTarget2](iclrdatatarget2-interface.md)\
 Подкласс `ICLRDataTarget`, используемый уровнем служб доступа к данным с целью управления областями виртуальной памяти в целевом процессе.  
  
 [Интерфейс ICLRDataTarget3](iclrdatatarget3-interface.md)\
 Подкласс [ICLRDataTarget2](iclrdatatarget2-interface.md) , обеспечивающий доступ к сведениям об исключении.  
  
 [Интерфейс ICLRDebugging](iclrdebugging-interface.md)\
 Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.  
  
 [Интерфейс ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)\
 Включает в себя [метод ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) метод, получающий интерфейс обратного вызова, который позволяет библиотеки отладки конкретной версии среды выполнения, находить и загружать по мере необходимости поставщика библиотеки.  
  
 [Интерфейс ICLRMetadataLocator](iclrmetadatalocator-interface.md)\
 Интерфейс, используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.  
  
 [Интерфейс ICorDebug](icordebug-interface.md)\
 Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR.  
  
 [Интерфейс1 ICorDebugAppDomain](icordebugappdomain-interface.md)\
 Предоставляет методы для отладки доменов приложения.  
  
 [ICorDebugAppDomain2 Interface1](icordebugappdomain2-interface.md)\
 Предоставляет методы для работы с массивами, указателями, указателями функций и типами ByRef. Этот интерфейс является расширением интерфейса `ICorDebugAppDomain`.  
  
 [Интерфейс ICorDebugAppDomain3](icordebugappdomain3-interface.md)\
 Предоставляет методы для работы с типами [!INCLUDE[wrt](../../../../includes/wrt-md.md)] в домене приложения. Этот интерфейс является расширением интерфейса `ICorDebugAppDomain` и `ICorDebugAppDomain2`.  
  
 [Интерфейс ICorDebugAppDomain4](icordebugappdomain4-interface.md)\
 Логически расширяет [ICorDebugAppDomain](icordebugappdomain-interface.md) интерфейса для получения управляемого объекта из вызываемой оболочки COM.  
  
 [ICorDebugAppDomainEnum Interface1](icordebugappdomainenum-interface.md)\
 Предоставляет метод, возвращающий заданное число значений `ICorDebugAppDomain`, начиная со следующего расположения в перечислении.  
  
 [ICorDebugArrayValue Interface1](icordebugarrayvalue-interface.md)\
 Подкласс интерфейса `ICorDebugHeapValue`, представляющий одномерный или многомерный массив.  
  
 [Интерфейс1 ICorDebugAssembly](icordebugassembly-interface.md)\
 Представляет сборку.  
  
 [Интерфейс1 ICorDebugAssembly2](icordebugassembly2-interface.md)\
 Представляет сборку. Этот интерфейс является расширением интерфейса `ICorDebugAssembly`.  
  
 [Интерфейс ICorDebugAssembly3](icordebugassembly3-interface.md)\
 Логически расширяет [ICorDebugAssembly](icordebugassembly-interface.md) интерфейса для обеспечения поддержки контейнерных сборок и их вложенных сборок. **Доступно только в .NET Native.**  
  
 [Интерфейс1 ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugAssembly`.  
  
 [Интерфейс ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)\
 Предоставляет перечислитель для списка [CorDebugBlockingObject](cordebugblockingobject-structure.md) структуры.  
  
 [ICorDebugBoxValue Interface1](icordebugboxvalue-interface.md)\
 Подкласс интерфейса `ICorDebugHeapValue`, представляющий упакованное значение объектов класса.  
  
 [Интерфейс1 ICorDebugBreakpoint](icordebugbreakpoint-interface.md)\
 Представляет точку останова в функции или контрольную точку для значения.  
  
 [ICorDebugBreakpointEnum Interface1](icordebugbreakpointenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugBreakpoint`.  
  
 [Интерфейс1 ICorDebugChain](icordebugchain-interface.md)\
 Представляет сегмент физического или логического стека вызовов.  
  
 [ICorDebugChainEnum Interface1](icordebugchainenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugChain`.  
  
 [Интерфейс1 ICorDebugClass](icordebugclass-interface.md)\
 Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.  
  
 [ICorDebugClass2 Interface1](icordebugclass2-interface.md)\
 Представляет универсальный класс или класс параметром метода типа <xref:System.Type>. Этот интерфейс расширяет интерфейс `ICorDebugClass`.  
  
 [Интерфейс1 ICorDebugCode](icordebugcode-interface1.md)\
 Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
 [Интерфейс1 ICorDebugCode2](icordebugcode2-interface.md)\
 Предоставляет методы, расширяющие возможности интерфейса `ICorDebugCode`.  
  
 [Интерфейс ICorDebugCode3](icordebugcode3-interface.md)\
 Предоставляет метод, который расширяет [ICorDebugCode](icordebugcode-interface1.md) и [ICorDebugCode2](icordebugcode2-interface.md) для предоставления сведений об управляемом возвращаемом значении.  
  
 [Интерфейс ICorDebugCode4](icordebugcode4-interface.md)\
 Предоставляет метод, который позволяет отладчику выполнить перечисление локальных переменных и аргументов в функции.  
  
 [ICorDebugCodeEnum Interface1](icordebugcodeenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugCode`.  
  
 [Интерфейс ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)\
 Предоставляет методы для получения кэшированных объектов интерфейса.  
  
 [Интерфейс1 ICorDebugContext](icordebugcontext-interface.md)\
 Представляет объект контекста. Этот интерфейс еще не реализован.  
  
 [Интерфейс1 ICorDebugController](icordebugcontroller-interface.md)\
 Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.  
  
 [Интерфейс ICorDebugDataTarget](icordebugdatatarget-interface.md)\
 Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.  
  
 [Интерфейс ICorDebugDataTarget2](icordebugdatatarget2-interface.md)\
 Логически расширяет [ICorDebugDataTarget](icordebugdatatarget-interface.md) интерфейс. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugDataTarget3](icordebugdatatarget3-interface.md)\
 Логически расширяет [ICorDebugDataTarget](icordebugdatatarget-interface.md) интерфейс для предоставления сведений о загруженных модулях. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugDebugEvent](icordebugdebugevent-interface.md)\
 Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugEditAndContinueErrorInfo](icordebugeditandcontinueerrorinfo-interface.md)\
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 [Интерфейс1 ICorDebugEditAndContinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)\
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 [Интерфейс1 ICorDebugEnum](icordebugenum-interface1.md)\
 Служит абстрактным базовым интерфейсом для перечислителей отладки.  
  
 [Интерфейс1 ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)\
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 [Интерфейс1 ICorDebugEval](icordebugeval-interface.md)\
 Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.  
  
 [ICorDebugEval2 Interface1](icordebugeval2-interface.md)\
 Расширяет интерфейс `ICorDebugEval` для предоставления поддержки универсальных типов.  
  
 [Интерфейс ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)\
 Расширяет [ICorDebugDebugEvent](icordebugdebugevent-interface.md) интерфейс для поддержки событий исключения. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)\
 Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.  
  
 [Интерфейс ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)\
 Расширяет [ICorDebugObjectValue](icordebugobjectvalue-interface.md) интерфейс, чтобы предоставить сведения о трассировке стека из управляемого объекта исключения.  
  
 [Интерфейс1 ICorDebugFrame](icordebugframe-interface.md)\
 Представляет кадр текущего стека.  
  
 [Интерфейс1 ICorDebugFrameEnum](icordebugframeenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugFrame`.  
  
 [Интерфейс1 ICorDebugFunction](icordebugfunction-interface1.md)\
 Представляет управляемую функцию или метод.  
  
 [Интерфейс1 ICorDebugFunction2](icordebugfunction2-interface.md)\
 Локально расширяет интерфейс `ICorDebugFunction` для предоставления поддержки отладки в пошаговом режиме "Только мой код".  
  
 [Интерфейс ICorDebugFunction3](icordebugfunction3-interface.md)\
 Логически расширяет [ICorDebugFunction](icordebugfunction-interface1.md) интерфейс для предоставления доступа к коду из запроса ReJIT.  
  
 [Интерфейс1 ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)\
 Расширяет интерфейс `ICorDebugBreakpoint` для поддержки точек останова в функциях.  
  
 [Интерфейс ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)\
 Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.  
  
 [ICorDebugGenericValue Interface1](icordebuggenericvalue-interface.md)\
 Подкласс интерфейса `ICorDebugValue`, применяемый ко всем значениям. Этот интерфейс предоставляет для значения методы Get и Set.  
  
 [Интерфейс ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)\
 Предоставляет перечислитель для объекта, сопоставляющего идентификаторы GUID и соответствующие объекты `ICorDebugType`.  
  
 [Интерфейс1 ICorDebugHandleValue](icordebughandlevalue-interface.md)\
 Подкласс интерфейса `ICorDebugReferenceValue`, представляющий значение ссылки, для которого отладчик создал дескриптор сборки мусора.  
  
 [Интерфейс ICorDebugHeapEnum](icordebugheapenum-interface.md)\
 Предоставляет перечислитель для объектов в управляемой куче.  
  
 [Интерфейс ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)\
 Предоставляет перечислитель для областей памяти управляемой кучи.  
  
 [Интерфейс1 ICorDebugHeapValue](icordebugheapvalue-interface.md)\
 Подкласс интерфейса `ICorDebugValue`, представляющий объект, подобранный сборщиком мусора среды CLR.  
  
 [Интерфейс1 ICorDebugHeapValue2](icordebugheapvalue2-interface1.md)\
 Расширение интерфейса `ICorDebugHeapValue`, предоставляющее поддержку дескрипторов среды выполнения.  
  
 [Интерфейс ICorDebugHeapValue3](icordebugheapvalue3-interface.md)\
 Предоставляет свойства блокировки монитора объектов.  
  
 [Интерфейс ICorDebugILCode](icordebugilcode-interface.md)\
 Представляет сегмент кода промежуточного языка.  
  
 [Интерфейс ICorDebugILCode2](icordebugilcode2-interface.md)\
 Логически расширяет [ICorDebugILCode](icordebugilcode-interface.md) интерфейс, чтобы предоставить методы, возвращающие маркер для подписи локальной переменной функции и сопоставлены инструментированного профилировщиком промежуточного языка (IL) смещений в исходный метод IL смещения.  
  
 [Интерфейс1 ICorDebugILFrame](icordebugilframe-interface.md)\
 Предоставляет кадр стека кода MSIL.  
  
 [Интерфейс1 ICorDebugILFrame2](icordebugilframe2-interface.md)\
 Логическое расширение интерфейса `ICorDebugILFrame`.  
  
 [Интерфейс ICorDebugILFrame3](icordebugilframe3-interface.md)\
 Предоставляет метод, инкапсулирующий возвращаемое значение функции.  
  
 [Интерфейс ICorDebugILFrame4](icordebugilframe4-interface.md)\
 Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка. Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.  
  
 [Интерфейс ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)\
 Представляет сведения отладочного символа для поля экземпляра. **Доступно только в .NET Native.**  
  
 [Интерфейс1 ICorDebugInternalFrame](icordebuginternalframe-interface.md)\
 Задает типы кадров для отладчика.  
  
 [Интерфейс ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)\
 Предоставляет сведения о внутренних кадрах, включая стековый адрес и положение относительно [ICorDebugFrame](icordebugframe-interface.md) объектов.  
  
 [Интерфейс ICorDebugLoadedModule](icordebugloadedmodule-interface.md)\
 Предоставляет сведения о загруженном модуле. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)\
 Предоставляет методы для обработки обратных вызовов отладчика.  
  
 [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)\
 Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA). Интерфейс `ICorDebugManagedCallback2` является логическим расширением интерфейса `ICorDebugManagedCallback`.  
  
 [Интерфейс ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)\
 Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.  
  
 [Интерфейс ICorDebugMDA](icordebugmda-interface.md)\
 Представляет сообщение управляемого помощника по отладке (MDA).  
  
 [Интерфейс ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)\
 Представляет буфер в памяти. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)\
 Предоставляет сведения о сборке после слияния. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugMetaDataLocator](icordebugmetadatalocator-interface.md)\
 Предоставляет сведения о метаданных для отладчика.  
  
 [Интерфейс1 ICorDebugModule](icordebugmodule-interface.md)\
 Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).  
  
 [Интерфейс1 ICorDebugModule2](icordebugmodule2-interface.md)\
 Служит логическим расширением интерфейса `ICorDebugModule`.  
  
 [Интерфейс ICorDebugModule3](icordebugmodule3-interface.md)\
 Создает средство чтения символов для динамического модуля.  
  
 [Интерфейс1 ICorDebugModuleBreakpoint](icordebugmodulebreakpoint-interface.md)\
 Расширяет интерфейс `ICorDebugBreakpoint` для предоставления доступа к указанным модулям.  
  
 [Интерфейс ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)\
 Расширяет [ICorDebugDebugEvent](icordebugdebugevent-interface.md) интерфейс для поддержки событий на уровне модуля. **Доступно только в .NET Native.**  
  
 [Интерфейс1 ICorDebugModuleEnum](icordebugmoduleenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugModule`.  
  
 [Интерфейс ICorDebugMutableDataTarget](icordebugmutabledatatarget-interface.md)\
 Расширяет [ICorDebugDataTarget](icordebugdatatarget-interface.md) интерфейс для поддержки целевых объектов изменяемых данных.  
  
 [Интерфейс1 ICorDebugNativeFrame](icordebugnativeframe-interface.md)\
 Специализированная реализация интерфейса `ICorDebugFrame`, используемая для кадров машинного кода.  
  
 [Интерфейс ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)\
 Предоставляет методы, проверяющие для кадров наличие взаимоотношений типа "дочерний-родительский".  
  
 [Интерфейс1 ICorDebugObjectEnum](icordebugobjectenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).  
  
 [Интерфейс1 ICorDebugObjectValue](icordebugobjectvalue-interface.md)\
 Подкласс `ICorDebugValue`, представляющий значение, содержащее объект.  
  
 [Интерфейс1 ICorDebugObjectValue2](icordebugobjectvalue2-interface.md)\
 Расширяет интерфейс `ICorDebugObjectValue` для поддержки наследования и переопределений.  
  
 [Интерфейс1 ICorDebugProcess](icordebugprocess-interface.md)\
 Представляет процесс, выполняющий управляемый код.  
  
 [Интерфейс1 ICorDebugProcess2](icordebugprocess2-interface1.md)\
 Логическое расширение интерфейса `ICorDebugProcess`.  
  
 [Интерфейс ICorDebugProcess3](icordebugprocess3-interface.md)\
 Управляет пользовательскими уведомлениями отладчика.

 [Интерфейс ICorDebugProcess4](icordebugprocess4-interface.md)\
 Обеспечивает поддержку вне контроля выполнения процесса.
  
 [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)\
 Расширяет [ICorDebugProcess](icordebugprocess-interface.md) локального интерфейса для поддержки доступа к управляемой куче, для предоставления сведений о сборке мусора управляемых объектов и для определения, загружает ли отладчик образы из приложения кэш образов в машинном коде.  
  
 [Интерфейс ICorDebugProcess6](icordebugprocess6-interface.md)\
 Логически расширяет [ICorDebugProcess](icordebugprocess-interface.md) интерфейс для включения функции, такие как декодирование событий управляемой отладки, которые кодируются в события отладки собственных исключений и разделение виртуальных модулей. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugProcess7](icordebugprocess7-interface.md)\
 Предоставляет метод, который настраивает отладчик для обработки обновлений находящихся в памяти метаданных в целевом процессе.  
  
 [Интерфейс ICorDebugProcess8](icordebugprocess8-interface.md)\
 Логически расширяет [ICorDebugProcess](icordebugprocess-interface.md) интерфейс, чтобы включить или отключить определенные виды [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) обратных вызовов исключения.  
  
 [ICorDebugProcessEnum Interface1](icordebugprocessenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugProcess`.  
  
 [Интерфейс1 ICorDebugReferenceValue](icordebugreferencevalue-interface.md)\
 Подкласс интерфейса `ICorDebugValue`, поддерживающего ссылочные типы.  
  
 [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)\
 Представляет набор регистров, доступных для компьютера, на котором в данный момент выполняется код.  
  
 [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)\
 Расширяет возможности интерфейса `ICorDebugRegisterSet` для аппаратных платформ, количество регистров которых превышает 64.  
  
 [Интерфейс ICorDebugRemote](icordebugremote-interface.md)\
 Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.  
  
 [Интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md)\
 Предоставляет методы, позволяющие отлаживать приложения на основе Silverlight в среде CLR.  
  
 [Интерфейс ICorDebugRuntimeUnwindableFrame](icordebugruntimeunwindableframe-interface.md)\
 Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.  
  
 [Интерфейс ICorDebugStackWalk](icordebugstackwalk-interface.md)\
 Обеспечивает методы для получения управляемых методов или кадров в стеке потока.  
  
 [Интерфейс ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)\
 Представляет сведения символа отладки для статического поля. **Доступно только в .NET Native.**  
  
 [Интерфейс1 ICorDebugStepper](icordebugstepper-interface.md)\
 Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.  
  
 [Интерфейс1 ICorDebugStepper2](icordebugstepper2-interface1.md)\
 Предоставляет поддержку отладки "Только мой код".  
  
 [Интерфейс1 ICorDebugStepperEnum](icordebugstepperenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugStepper`.  
  
 [Интерфейс1 ICorDebugStringValue](icordebugstringvalue-interface.md)\
 Подкласс `ICorDebugHeapValue`, применяемый к строковым значениям.  
  
 [Интерфейс ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)\
 Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)\
 Логически расширяет [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) интерфейс для извлечения дополнительных символов отладки. **Доступно только в .NET Native.**  
  
 [Интерфейс1 ICorDebugThread](icordebugthread-interface.md)\
 Представляет поток в процессе. Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.  
  
 [Интерфейс1 ICorDebugThread2](icordebugthread2-interface.md)\
 Служит логическим расширением интерфейса `ICorDebugThread`.  
  
 [Интерфейс ICorDebugThread3](icordebugthread3-interface.md)\
 Предоставляет точку входа для [ICorDebugStackWalk](icordebugstackwalk-interface.md) и соответствующие интерфейсы.  
  
 [Интерфейс ICorDebugThread4](icordebugthread4-interface.md)\
 Предоставляет сведения о блокировке потока.  
  
 [ICorDebugThreadEnum Interface1](icordebugthreadenum-interface1.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugThread`.  
  
 [Интерфейс1 ICorDebugType](icordebugtype-interface.md)\
 Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.  
  
 [Интерфейс ICorDebugType2](icordebugtype2-interface.md)\
 Расширяет [ICorDebugType](icordebugtype-interface.md) интерфейс для извлечения идентификатора типа базового типа или сложного типа (определяемый пользователем).  
  
 [ICorDebugTypeEnum Interface1](icordebugtypeenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugType`.  
  
 [Интерфейс ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)\
 Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно со средой CLR.  
  
 [ICorDebugValue](icordebugvalue-interface.md)\
 Представляет значение для записи или чтения в отлаживаемом процессе.  
  
 [ICorDebugValue2](icordebugvalue2-interface.md)\
 Расширяет интерфейс `ICorDebugValue` для предоставления поддержки интерфейса `ICorDebugType`.  
  
 [Интерфейс ICorDebugValue3](icordebugvalue3-interface.md)\
 Расширяет интерфейс «ICorDebugValue» и «ICorDebugValue2» для обеспечения поддержки массивов, размер которых превышает 2 ГБ.  
  
 [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\
 Расширяет интерфейс `ICorDebugBreakpoint` для обеспечения доступа к указанным значениям.  
  
 [ICorDebugValueEnum](icordebugvalueenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugValue`.  
  
 [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)\
 Представляет локальную переменную или аргумент функции.  
  
 [ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)\
 Предоставляет перечислитель для локальных переменных и аргументов в функции.  
  
 [Интерфейс ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)\
 Извлекает сведения символа отладки для статического поля. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)\
 Предоставляет методы, помогающие очистить стек. **Доступно только в .NET Native.**  
  
 [Интерфейс ICorPublish](icorpublish-interface.md)\
 Служит универсальным интерфейсом для процессов публикации.  
  
 [Интерфейс ICorPublishAppDomain](icorpublishappdomain-interface.md)\
 Представляет и предоставляет информацию о домене приложения.  
  
 [Интерфейс ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)\
 Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishAppDomain`, существующих в процессе в данный момент.  
  
 [Интерфейс ICorPublishEnum](icorpublishenum-interface.md)\
 Служит абстрактной базой для перечислителей публикации.  
  
 [Интерфейс ICorPublishProcess](icorpublishprocess-interface.md)\
 Предоставляет методы, позволяющие получить доступ к сведениям о процессе.  
  
 [Интерфейс ICorPublishProcessEnum](icorpublishprocessenum-interface.md)\
 Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishProcess`.  

 [Интерфейс ISOSDacInterface](isosdacinterface-interface.md)\
 Предоставляет вспомогательные методы для доступа к данным из `SOS`.

 [Интерфейс IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)\
 Предоставляет методы для запроса на получение сведений об определении метода.
 
 [Интерфейс IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)\
 Предоставляет методы для запроса на получение сведений о экземпляра метода.
 
 [Интерфейс IXCLRDataModule](ixclrdatamodule-interface.md)\
 Предоставляет методы для запроса на получение сведений о загруженном модуле.
 
 [Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)\
 Предоставляет методы для запроса на получение сведений о процессе.
  
## <a name="related-sections"></a>Связанные разделы  
 [Коклассы отладки](debugging-coclasses.md)\
 [Глобальные статические функции отладки](debugging-global-static-functions.md)\
 [Перечисления отладки](debugging-enumerations.md)\
 [Структуры отладки](debugging-structures.md)\
