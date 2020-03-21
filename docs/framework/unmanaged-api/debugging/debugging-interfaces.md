---
title: Интерфейсы отладки
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: c4b9cdc2bc90096ab7c3b041bd8aa2742b48c35c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179166"
---
# <a name="debugging-interfaces"></a>Интерфейсы отладки
В этом разделе описываются неуправляемые интерфейсы отладки, управляющие отладкой программы, выполняемой в среде CLR.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Интерфейс ICLRDataEnumMemoryРегионы](iclrdataenummemoryregions-interface.md)\
 Предоставляет метод, выполняющий перечисление областей памяти, заданной вызовами.  
  
 [Интерфейс ICLRDataEnumMemoryCallback](iclrdataenummemoryregionscallback-interface.md)\
 Предоставляет метод обратного вызова для метода `EnumMemoryRegions`, сообщающий отладчику результат попытки перечисления заданной области памяти.  
  
 [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)\
 Предоставляет методы для взаимодействия с целевым процессом среды CLR.  
  
 [Интерфейс ICLRDataTarget2](iclrdatatarget2-interface.md)\
 Подкласс `ICLRDataTarget`, используемый уровнем служб доступа к данным с целью управления областями виртуальной памяти в целевом процессе.  
  
 [Интерфейс ICLRDataTarget3](iclrdatatarget3-interface.md)\
 Подкласс [ICLRDataTarget2,](iclrdatatarget2-interface.md) предоставляющий доступ к информации об исключениях.  
  
 [Интерфейс ICLRDebugging](iclrdebugging-interface.md)\
 Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.  
  
 [Интерфейс ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)\
 Включает метод [ProvideLibrary Method,](iclrdebugginglibraryprovider-providelibrary-method.md) который получает интерфейс обратного вызова поставщика библиотек, который позволяет находить и загружать библиотеки отладки по требованию для общего времени выполнения.  
  
 [Интерфейс ICLRMetadataLocator](iclrmetadatalocator-interface.md)\
 Интерфейс, используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.  
  
 [Интерфейс ICorDebug](icordebug-interface.md)\
 Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR.  
  
 [Интерфейс ICorDebugAppDomain](icordebugappdomain-interface.md)\
 Предоставляет методы для отладки доменов приложения.  
  
 [Интерфейс ICorDebugAppDomain2](icordebugappdomain2-interface.md)\
 Предоставляет методы для работы с массивами, указателями, указателями функций и типами ByRef. Этот интерфейс является расширением интерфейса `ICorDebugAppDomain`.  
  
 [Интерфейс ICorDebugAppDomain3](icordebugappdomain3-interface.md)\
 Предоставляет методы работы с типами Runtime Windows в домене приложения. Этот интерфейс является расширением интерфейса `ICorDebugAppDomain` и `ICorDebugAppDomain2`.  
  
 [Интерфейс ICorDebugAppDomain4](icordebugappdomain4-interface.md)\
 Логически расширяет интерфейс [ICorDebugAppDomain,](icordebugappdomain-interface.md) чтобы получить управляемый объект из вызываемой обертки COM.  
  
 [Интерфейс ICorDebugAppDomainEnum](icordebugappdomainenum-interface.md)\
 Предоставляет метод, возвращающий заданное число значений `ICorDebugAppDomain`, начиная со следующего расположения в перечислении.  
  
 [Интерфейс ICorDebugArrayValueValue](icordebugarrayvalue-interface.md)\
 Подкласс интерфейса `ICorDebugHeapValue`, представляющий одномерный или многомерный массив.  
  
 [Интерфейс ICorDebugAssembly](icordebugassembly-interface.md)\
 Представляет сборку.  
  
 [Интерфейс ICorDebugAssembly2](icordebugassembly2-interface.md)\
 Представляет сборку. Этот интерфейс является расширением интерфейса `ICorDebugAssembly`.  
  
 [Интерфейс ICorDebugAssembly3](icordebugassembly3-interface.md)\
 Логически расширяет интерфейс [ICorDebugAssembly,](icordebugassembly-interface.md) чтобы обеспечить поддержку контейнерных сборок и содержащихся в них сборок. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugAssembly`.  
  
 [Интерфейс ICorDebugBlockingObjectEnum](icordebugblockingobjectenum-interface.md)\
 Предоставляет список для списка структур [CorDebugBlockingObject.](cordebugblockingobject-structure.md)  
  
 [Интерфейс ICorDebugBoxValue](icordebugboxvalue-interface.md)\
 Подкласс интерфейса `ICorDebugHeapValue`, представляющий упакованное значение объектов класса.  
  
 [Интерфейс ICorDebugBreakpoint](icordebugbreakpoint-interface.md)\
 Представляет точку останова в функции или контрольную точку для значения.  
  
 [Интерфейс ICorDebugBreakpointEnum](icordebugbreakpointenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugBreakpoint`.  
  
 [Интерфейс ICorDebugChain](icordebugchain-interface.md)\
 Представляет сегмент физического или логического стека вызовов.  
  
 [Интерфейс ICorDebugChainEnum](icordebugchainenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugChain`.  
  
 [Интерфейс ICorDebugClass](icordebugclass-interface.md)\
 Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.  
  
 [Интерфейс ICorDebugClass2](icordebugclass2-interface.md)\
 Представляет универсальный класс или класс параметром метода типа <xref:System.Type>. Этот интерфейс расширяет интерфейс `ICorDebugClass`.  
  
 [Интерфейс ICorDebugCode](icordebugcode-interface1.md)\
 Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
 [Интерфейс ICorDebugCode2](icordebugcode2-interface.md)\
 Предоставляет методы, расширяющие возможности интерфейса `ICorDebugCode`.  
  
 [Интерфейс ICorDebugCode3](icordebugcode3-interface.md)\
 Предоставляет метод, который расширяет [ICorDebugCode](icordebugcode-interface1.md) и [ICorDebugCode2](icordebugcode2-interface.md) для предоставления информации о управляемой стоимости возврата.  
  
 [Интерфейс ICorDebugCode4](icordebugcode4-interface.md)\
 Предоставляет метод, позволяющий отладчику перечислять локальные переменные и аргументы в функции.  
  
 [Интерфейс ICorDebugCodeEnum](icordebugcodeenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugCode`.  
  
 [Интерфейс ICorDebugComObjectValue](icordebugcomobjectvalue-interface.md)\
 Предоставляет методы для получения кэшированных объектов интерфейса.  
  
 [Интерфейс ICorDebugContext](icordebugcontext-interface.md)\
 Представляет объект контекста. Этот интерфейс еще не реализован.  
  
 [Интерфейс ICorDebugController](icordebugcontroller-interface.md)\
 Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.  
  
 [Интерфейс ICorDebugDataTarget](icordebugdatatarget-interface.md)\
 Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.  
  
 [Интерфейс ICorDebugDataTarget2](icordebugdatatarget2-interface.md)\
 Логически расширяет интерфейс [ICorDebugDataTarget.](icordebugdatatarget-interface.md) **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugDataTarget3](icordebugdatatarget3-interface.md)\
 Логически расширяет интерфейс [ICorDebugDataTarget,](icordebugdatatarget-interface.md) чтобы предоставить информацию о загруженных модулях. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugDebugEvent](icordebugdebugevent-interface.md)\
 Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`. **Доступен только в .NET Native.**  
  
 [ICorDebugEditAndcontinueerrorinfo Интерфейс](icordebugeditandcontinueerrorinfo-interface.md)\
 Устаревшее. Не следует использовать данный интерфейс.  
  
 [Интерфейс ICorDebugEditAndcontinueSnapshot](icordebugeditandcontinuesnapshot-interface.md)\
 Устаревшее. Не следует использовать данный интерфейс.  
  
 [Интерфейс ICorDebugEnum](icordebugenum-interface1.md)\
 Служит абстрактным базовым интерфейсом для перечислителей отладки.  
  
 [Интерфейс ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)\
 Устаревшее. Не следует использовать данный интерфейс.  
  
 [Интерфейс ICorDebugEval](icordebugeval-interface.md)\
 Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.  
  
 [Интерфейс ICorDebugEval2](icordebugeval2-interface.md)\
 Расширяет интерфейс `ICorDebugEval` для предоставления поддержки универсальных типов.  
  
 [ICorDebugИзедебугВент Интерфейс](icordebugexceptiondebugevent-interface.md)\
 Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий исключений. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugExceptionObjectstackStackEnum интерфейс](icordebugexceptionobjectcallstackenum-interface.md)\
 Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.  
  
 [Интерфейс ICorDebugExceptionValueValueValue](icordebugexceptionobjectvalue-interface.md)\
 Расширяет интерфейс [ICorDebugObjectValue,](icordebugobjectvalue-interface.md) чтобы предоставить информацию о стеках из управляемого объекта исключения.  
  
 [Интерфейс ICorDebugFrame](icordebugframe-interface.md)\
 Представляет кадр текущего стека.  
  
 [Интерфейс ICorDebugFrameEnum](icordebugframeenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugFrame`.  
  
 [Интерфейс ICorDebugFunction](icordebugfunction-interface1.md)\
 Представляет управляемую функцию или метод.  
  
 [Интерфейс ICorDebugFunction2](icordebugfunction2-interface.md)\
 Локально расширяет интерфейс `ICorDebugFunction` для предоставления поддержки отладки в пошаговом режиме "Только мой код".  
  
 [Интерфейс ICorDebugFunction3](icordebugfunction3-interface.md)\
 Логически расширяет интерфейс [ICorDebugFunction,](icordebugfunction-interface1.md) чтобы обеспечить доступ к коду из запроса ReJIT.  
  
 [Интерфейс ICorDebugФункцияBreakpoint](icordebugfunctionbreakpoint-interface.md)\
 Расширяет интерфейс `ICorDebugBreakpoint` для поддержки точек останова в функциях.  
  
 [Интерфейс ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)\
 Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.  
  
 [Интерфейс ICorDebugGenericValue](icordebuggenericvalue-interface.md)\
 Подкласс интерфейса `ICorDebugValue`, применяемый ко всем значениям. Этот интерфейс предоставляет для значения методы Get и Set.  
  
 [Интерфейс ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)\
 Предоставляет перечислитель для объекта, сопоставляющего идентификаторы GUID и соответствующие объекты `ICorDebugType`.  
  
 [Интерфейс ICorDebugHandleValue](icordebughandlevalue-interface.md)\
 Подкласс интерфейса `ICorDebugReferenceValue`, представляющий значение ссылки, для которого отладчик создал дескриптор сборки мусора.  
  
 [Интерфейс ICorDebugHeapEnum](icordebugheapenum-interface.md)\
 Предоставляет перечислитель для объектов в управляемой куче.  
  
 [Интерфейс ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md)\
 Предоставляет перечислитель для областей памяти управляемой кучи.  
  
 [Интерфейс ICorDebugHeapValue](icordebugheapvalue-interface.md)\
 Подкласс интерфейса `ICorDebugValue`, представляющий объект, подобранный сборщиком мусора среды CLR.  
  
 [Интерфейс ICorDebugHeapValue2](icordebugheapvalue2-interface1.md)\
 Расширение интерфейса `ICorDebugHeapValue`, предоставляющее поддержку дескрипторов среды выполнения.  
  
 [Интерфейс ICorDebugHeapValue3](icordebugheapvalue3-interface.md)\
 Предоставляет свойства блокировки монитора объектов.  
  
 [Интерфейс ICorDebugILCode](icordebugilcode-interface.md)\
 Представляет сегмент кода промежуточного языка.  
  
 [Интерфейс ICorDebugILCode2](icordebugilcode2-interface.md)\
 Логически расширяет интерфейс [ICorDebugILCode,](icordebugilcode-interface.md) чтобы обеспечить методы, которые возвращают токен для локальной переменной подписи функции, и что карта инструментальный промежуточный язык профайлера (IL) компенсируется оригинальным методом IL смещения.  
  
 [Интерфейс ICorDebugILFrame](icordebugilframe-interface.md)\
 Предоставляет кадр стека кода MSIL.  
  
 [Интерфейс ICorDebugILFrame2](icordebugilframe2-interface.md)\
 Логическое расширение интерфейса `ICorDebugILFrame`.  
  
 [Интерфейс ICorDebugILFrame3](icordebugilframe3-interface.md)\
 Предоставляет метод, инкапсулирующий возвращаемое значение функции.  
  
 [Интерфейс ICorDebugILFrame4](icordebugilframe4-interface.md)\
 Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка. Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.  
  
 [Интерфейс ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)\
 Представляет сведения отладочного символа для поля экземпляра. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugInternalFrame](icordebuginternalframe-interface.md)\
 Задает типы кадров для отладчика.  
  
 [Интерфейс ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)\
 Предоставляет информацию о внутренних кадрах, включая адрес стека и положение по отношению к объектам [ICorDebugFrame.](icordebugframe-interface.md)  
  
 [ICorDebugLoadedModule Интерфейс](icordebugloadedmodule-interface.md)\
 Предоставляет сведения о загруженном модуле. **Доступен только в .NET Native.**  
  
 [ICorDebugManagedCallback Интерфейс](icordebugmanagedcallback-interface.md)\
 Предоставляет методы для обработки обратных вызовов отладчика.  
  
 [ICorDebugManagedCallback2 Интерфейс](icordebugmanagedcallback2-interface.md)\
 Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA). Интерфейс `ICorDebugManagedCallback2` является логическим расширением интерфейса `ICorDebugManagedCallback`.  
  
 [ICorDebugManagedCallback3 Интерфейс](icordebugmanagedcallback3-interface.md)\
 Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.  
  
 [Интерфейс ICorDebugMDA](icordebugmda-interface.md)\
 Представляет сообщение управляемого помощника по отладке (MDA).  
  
 [Интерфейс ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)\
 Представляет буфер в памяти. **Доступен только в .NET Native.**  
  
 [ICorDebugMergedAssemblyЗапись интерфейса](icordebugmergedassemblyrecord-interface.md)\
 Предоставляет сведения о сборке после слияния. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugMetaDataLocator](icordebugmetadatalocator-interface.md)\
 Предоставляет сведения о метаданных для отладчика.  
  
 [Интерфейс ICorDebugМодуль](icordebugmodule-interface.md)\
 Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).  
  
 [Интерфейс ICorDebugModule2](icordebugmodule2-interface.md)\
 Служит логическим расширением интерфейса `ICorDebugModule`.  
  
 [Интерфейс ICorDebugModule3](icordebugmodule3-interface.md)\
 Создает средство чтения символов для динамического модуля.  
  
 [Интерфейс ICorDebugModule](icordebugmodulebreakpoint-interface.md)\
 Расширяет интерфейс `ICorDebugBreakpoint` для предоставления доступа к указанным модулям.  
  
 [ICorDebugModuleDebugEvent Интерфейс](icordebugmoduledebugevent-interface.md)\
 Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий уровня модуля. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugModuleEnum](icordebugmoduleenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugModule`.  
  
 [ICorDebugMutableDataTarget Интерфейс](icordebugmutabledatatarget-interface.md)\
 Расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) для поддержки немых целей данных.  
  
 [Интерфейс ICorDebugNativeFrame](icordebugnativeframe-interface.md)\
 Специализированная реализация интерфейса `ICorDebugFrame`, используемая для кадров машинного кода.  
  
 [Интерфейс ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)\
 Предоставляет методы, проверяющие для кадров наличие взаимоотношений типа "дочерний-родительский".  
  
 [Интерфейс ICorDebugObjectEnum](icordebugobjectenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).  
  
 [Интерфейс ICorDebugObjectValue](icordebugobjectvalue-interface.md)\
 Подкласс `ICorDebugValue`, представляющий значение, содержащее объект.  
  
 [Интерфейс ICorDebugObjectValue2](icordebugobjectvalue2-interface.md)\
 Расширяет интерфейс `ICorDebugObjectValue` для поддержки наследования и переопределений.  
  
 [Интерфейс ICorDebugProcess](icordebugprocess-interface.md)\
 Представляет процесс, выполняющий управляемый код.  
  
 [Интерфейс ICorDebugProcess2](icordebugprocess2-interface1.md)\
 Логическое расширение интерфейса `ICorDebugProcess`.  
  
 [Интерфейс ICorDebugProcess3](icordebugprocess3-interface.md)\
 Управляет пользовательскими уведомлениями отладчика.

 [Интерфейс ICorDebugProcess4](icordebugprocess4-interface.md)\
 Обеспечивает поддержку вне контроля выполнения процесса.
  
 [Интерфейс ICorDebugProcess5](icordebugprocess5-interface.md)\
 Расширяет интерфейс [ICorDebugProcess](icordebugprocess-interface.md) для поддержки доступа к управляемой куче, предоставления информации о сборе мусора управляемых объектов и определения того, загружает ли отладчик изображения из локального кэша изображений приложения.  
  
 [Интерфейс ICorDebugProcess6](icordebugprocess6-interface.md)\
 Логически расширяет интерфейс [ICorDebugProcess,](icordebugprocess-interface.md) чтобы включить такие функции, как декодирование управляемых событий отладки, которые закодированы в событиях отладки родных исключений и расставании виртуального модуля. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugProcess7](icordebugprocess7-interface.md)\
 Предоставляет метод, который настраивает отладчик для обработки обновлений находящихся в памяти метаданных в целевом процессе.  
  
 [Интерфейс ICorDebugProcess8](icordebugprocess8-interface.md)\
 Логически расширяет интерфейс [ICorDebugProcess,](icordebugprocess-interface.md) чтобы включить или отключить определенные типы обратных вызовов [iCorDebugManagedCallback2.](icordebugmanagedcallback2-interface.md)  
  
 [Интерфейс ICorDebugProcessEnum](icordebugprocessenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugProcess`.  
  
 [ICorDebugСправкаИнтерфейс](icordebugreferencevalue-interface.md)\
 Подкласс интерфейса `ICorDebugValue`, поддерживающего ссылочные типы.  
  
 [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)\
 Представляет набор регистров, доступных для компьютера, на котором в данный момент выполняется код.  
  
 [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)\
 Расширяет возможности интерфейса `ICorDebugRegisterSet` для аппаратных платформ, количество регистров которых превышает 64.  
  
 [ICorDebugУдаленный интерфейс](icordebugremote-interface.md)\
 Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.  
  
 [Интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md)\
 Предоставляет методы, позволяющие отлаживать приложения на основе Silverlight в среде CLR.  
  
 [Интерфейс ICorDebugRuntimeUnwindableFrame](icordebugruntimeunwindableframe-interface.md)\
 Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.  
  
 [Интерфейс ICorDebugStackWalk](icordebugstackwalk-interface.md)\
 Обеспечивает методы для получения управляемых методов или кадров в стеке потока.  
  
 [Интерфейс ICorDebugStaticfieldSymbol](icordebugstaticfieldsymbol-interface.md)\
 Представляет сведения символа отладки для статического поля. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugStepper](icordebugstepper-interface.md)\
 Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.  
  
 [Интерфейс ICorDebugStepper2](icordebugstepper2-interface1.md)\
 Предоставляет поддержку отладки "Только мой код".  
  
 [Интерфейс ICorDebugStepperEnum](icordebugstepperenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugStepper`.  
  
 [Интерфейс ICorDebugStringValue](icordebugstringvalue-interface.md)\
 Подкласс `ICorDebugHeapValue`, применяемый к строковым значениям.  
  
 [Интерфейс ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)\
 Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)\
 Логически расширяет интерфейс [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) для получения дополнительной информации о символе отладки. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugThread](icordebugthread-interface.md)\
 Представляет поток в процессе. Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.  
  
 [Интерфейс ICorDebugThread2](icordebugthread2-interface.md)\
 Служит логическим расширением интерфейса `ICorDebugThread`.  
  
 [Интерфейс ICorDebugThread3](icordebugthread3-interface.md)\
 Обеспечивает точку входа в [ICorDebugStackWalk](icordebugstackwalk-interface.md) и соответствующие интерфейсы.  
  
 [Интерфейс ICorDebugThread4](icordebugthread4-interface.md)\
 Предоставляет сведения о блокировке потока.  
  
 [Интерфейс ICorDebugThreadEnum](icordebugthreadenum-interface1.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugThread`.  
  
 [Интерфейс ICorDebugType](icordebugtype-interface.md)\
 Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.  
  
 [Интерфейс ICorDebugType2](icordebugtype2-interface.md)\
 Расширяет интерфейс [ICorDebugType](icordebugtype-interface.md) для получения идентификатора типа базового типа или сложного (определяемого пользователем) типа.  
  
 [Интерфейс ICorDebugTypeEnum](icordebugtypeenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugType`.  
  
 [ICorDebugUnmanagedCallback Интерфейс](icordebugunmanagedcallback-interface.md)\
 Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно со средой CLR.  
  
 [ICorDebugValue](icordebugvalue-interface.md)\
 Представляет значение для записи или чтения в отлаживаемом процессе.  
  
 [ICorDebugValue2](icordebugvalue2-interface.md)\
 Расширяет интерфейс `ICorDebugValue` для предоставления поддержки интерфейса `ICorDebugType`.  
  
 [Интерфейс ICorDebugValue3](icordebugvalue3-interface.md)\
 Расширяет интерфейсы "ICorDebugValue" и "ICorDebugValue2", чтобы обеспечить поддержку массивов, превышают 2 ГБ.  
  
 [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\
 Расширяет интерфейс `ICorDebugBreakpoint` для обеспечения доступа к указанным значениям.  
  
 [ICorDebugValueEnum](icordebugvalueenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugValue`.  
  
 [ICorDebug ПеременныйДомашний Интерфейс](icordebugvariablehome-interface.md)\
 Представляет локальную переменную или аргумент функции.  
  
 [Интерфейс ICorDebug VariableHomeEnum](icordebugvariablehomeenum-interface.md)\
 Обеспечивает перечисление локальных переменных и аргументов в функции.  
  
 [Интерфейс ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)\
 Извлекает сведения символа отладки для статического поля. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)\
 Предоставляет методы, помогающие очистить стек. **Доступен только в .NET Native.**  
  
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

 [Интерфейс ISOSDacИнтерфейс](isosdacinterface-interface.md)\
 Предоставляет вспомогательные методы `SOS`для доступа к данным из .

 [Интерфейс IXCLRDataMethodDefinition](ixclrdatamethoddefinition-interface.md)\
 Предоставляет методы запроса информации об определении метода.

 [Интерфейс IXCLRDataMethodInstance](ixclrdatamethodinstance-interface.md)\
 Предоставляет методы запроса информации о экземпляре метода.

 [Интерфейс IXCLRDataModule](ixclrdatamodule-interface.md)\
 Предоставляет методы запроса информации о загруженном модуле.

 [Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)\
 Предоставляет методы запроса информации о процессе.
  
## <a name="related-sections"></a>См. также  
 [Дебагинг coclasses](debugging-coclasses.md)\
 [Отладка глобальных статических функций](debugging-global-static-functions.md)\
 [Отладка цифр](debugging-enumerations.md)\
 [Структуры отладки](debugging-structures.md)\
