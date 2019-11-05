---
title: Интерфейсы отладки
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: 07b39666637628102e9ffafd2c059ba0d4b51b92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097198"
---
# <a name="debugging-interfaces"></a>Интерфейсы отладки
В этом разделе описываются неуправляемые интерфейсы отладки, управляющие отладкой программы, выполняемой в среде CLR.  
  
## <a name="in-this-section"></a>Содержание  
 \ [интерфейса иклрдатаенуммеморирегионс](iclrdataenummemoryregions-interface.md)
 Предоставляет метод, выполняющий перечисление областей памяти, заданной вызовами.  
  
 \ [интерфейса иклрдатаенуммеморирегионскаллбакк](iclrdataenummemoryregionscallback-interface.md)
 Предоставляет метод обратного вызова для метода `EnumMemoryRegions`, сообщающий отладчику результат попытки перечисления заданной области памяти.  
  
 \ [интерфейса ICLRDataTarget](iclrdatatarget-interface.md)
 Предоставляет методы для взаимодействия с целевым процессом среды CLR.  
  
 \ [интерфейса ICLRDataTarget2](iclrdatatarget2-interface.md)
 Подкласс `ICLRDataTarget`, используемый уровнем служб доступа к данным с целью управления областями виртуальной памяти в целевом процессе.  
  
 \ [интерфейса метод iclrdatatarget3](iclrdatatarget3-interface.md)
 Подкласс [ICLRDataTarget2](iclrdatatarget2-interface.md) , предоставляющий доступ к сведениям об исключениях.  
  
 \ [интерфейса ICLRDebugging](iclrdebugging-interface.md)
 Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.  
  
 \ [интерфейса иклрдебуггинглибрарипровидер](iclrdebugginglibraryprovider-interface.md)
 Включает метод [метода ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) , который получает интерфейс обратного вызова поставщика библиотеки, который позволяет находить и загружать библиотеки отладки, относящиеся к конкретной версии среды CLR, по запросу.  
  
 \ [интерфейса иклрметадаталокатор](iclrmetadatalocator-interface.md)
 Интерфейс, используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.  
  
 [Интерфейс ICorDebug](icordebug-interface.md)\
 Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR.  
  
 \ [интерфейса ICorDebugAppDomain](icordebugappdomain-interface.md)
 Предоставляет методы для отладки доменов приложения.  
  
 \ [интерфейса ICorDebugAppDomain2](icordebugappdomain2-interface.md)
 Предоставляет методы для работы с массивами, указателями, указателями функций и типами ByRef. Этот интерфейс является расширением интерфейса `ICorDebugAppDomain`.  
  
 \ [интерфейса ICorDebugAppDomain3](icordebugappdomain3-interface.md)
 Предоставляет методы для работы с типами среда выполнения Windows в домене приложения. Этот интерфейс является расширением интерфейса `ICorDebugAppDomain` и `ICorDebugAppDomain2`.  
  
 \ [интерфейса ICorDebugAppDomain4](icordebugappdomain4-interface.md)
 Логически расширяет интерфейс [ICorDebugAppDomain](icordebugappdomain-interface.md) для получения управляемого объекта из вызываемой оболочки COM.  
  
 \ [интерфейса икордебугаппдомаиненум](icordebugappdomainenum-interface.md)
 Предоставляет метод, возвращающий заданное число значений `ICorDebugAppDomain`, начиная со следующего расположения в перечислении.  
  
 \ [интерфейса ICorDebugArrayValue](icordebugarrayvalue-interface.md)
 Подкласс интерфейса `ICorDebugHeapValue`, представляющий одномерный или многомерный массив.  
  
 \ [интерфейса ICorDebugAssembly](icordebugassembly-interface.md)
 Представляет сборку.  
  
 \ [интерфейса ICorDebugAssembly2](icordebugassembly2-interface.md)
 Представляет сборку. Этот интерфейс является расширением интерфейса `ICorDebugAssembly`.  
  
 \ [интерфейса ICorDebugAssembly3](icordebugassembly3-interface.md)
 Логически расширяет интерфейс [ICorDebugAssembly](icordebugassembly-interface.md) , чтобы обеспечить поддержку для сборок контейнеров и содержащихся в них сборок. **Доступно только на .NET Native.**  
  
 \ [интерфейса ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugAssembly`.  
  
 \ [интерфейса икордебугблоккингобжектенум](icordebugblockingobjectenum-interface.md)
 Предоставляет перечислитель для списка структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
 \ [интерфейса икордебугбоксвалуе](icordebugboxvalue-interface.md)
 Подкласс интерфейса `ICorDebugHeapValue`, представляющий упакованное значение объектов класса.  
  
 \ [интерфейса икордебугбреакпоинт](icordebugbreakpoint-interface.md)
 Представляет точку останова в функции или контрольную точку для значения.  
  
 \ [интерфейса ICorDebugBreakpointEnum](icordebugbreakpointenum-interface.md)
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugBreakpoint`.  
  
 \ [интерфейса ICorDebugChain](icordebugchain-interface.md)
 Представляет сегмент физического или логического стека вызовов.  
  
 \ [интерфейса икордебугчаиненум](icordebugchainenum-interface.md)
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugChain`.  
  
 \ [интерфейса ICorDebugClass](icordebugclass-interface.md)
 Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.  
  
 \ [интерфейса ICorDebugClass2](icordebugclass2-interface.md)
 Представляет универсальный класс или класс параметром метода типа <xref:System.Type>. Этот интерфейс расширяет интерфейс `ICorDebugClass`.  
  
 [Интерфейс ICorDebugCode](icordebugcode-interface1.md)\
 Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
 \ [интерфейса ICorDebugCode2](icordebugcode2-interface.md)
 Предоставляет методы, расширяющие возможности интерфейса `ICorDebugCode`.  
  
 \ [интерфейса ICorDebugCode3](icordebugcode3-interface.md)
 Предоставляет метод, расширяющий интерфейс [ICorDebugCode](icordebugcode-interface1.md) и [ICorDebugCode2](icordebugcode2-interface.md) для предоставления сведений об управляемом возвращаемом значении.  
  
 \ [интерфейса ICorDebugCode4](icordebugcode4-interface.md)
 Предоставляет метод, позволяющий отладчику перечислить локальные переменные и аргументы в функции.  
  
 \ [интерфейса икордебугкодинум](icordebugcodeenum-interface.md)
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugCode`.  
  
 \ [интерфейса икордебугкомобжектвалуе](icordebugcomobjectvalue-interface.md)
 Предоставляет методы для получения кэшированных объектов интерфейса.  
  
 \ [интерфейса икордебугконтекст](icordebugcontext-interface.md)
 Представляет объект контекста. Этот интерфейс еще не реализован.  
  
 \ [интерфейса ICorDebugController](icordebugcontroller-interface.md)
 Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.  
  
 \ [интерфейса ICorDebugDataTarget](icordebugdatatarget-interface.md)
 Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.  
  
 \ [интерфейса метод icordebugdatatarget2](icordebugdatatarget2-interface.md)
 Логически расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) . **Доступно только на .NET Native.**  
  
 \ [интерфейса ICorDebugDataTarget3](icordebugdatatarget3-interface.md)
 Логически расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) , чтобы предоставить сведения о загруженных модулях. **Доступно только на .NET Native.**  
  
 \ [интерфейса ICorDebugDebugEvent](icordebugdebugevent-interface.md)
 Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`. **Доступно только на .NET Native.**  
  
 \ [интерфейса икордебужедитандконтинуирроринфо](icordebugeditandcontinueerrorinfo-interface.md)
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 \ [интерфейса метод icordebugeditandcontinuesnapshot](icordebugeditandcontinuesnapshot-interface.md)
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 \ [интерфейса ICorDebugEnum](icordebugenum-interface1.md)
 Служит абстрактным базовым интерфейсом для перечислителей отладки.  
  
 \ [интерфейса ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 \ [интерфейса ICorDebugEval](icordebugeval-interface.md)
 Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.  
  
 \ [интерфейса ICorDebugEval2](icordebugeval2-interface.md)
 Расширяет интерфейс `ICorDebugEval` для предоставления поддержки универсальных типов.  
  
 \ [интерфейса икордебужексцептиондебужевент](icordebugexceptiondebugevent-interface.md)
 Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий исключения. **Доступно только на .NET Native.**  
  
 \ [интерфейса ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)
 Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.  
  
 \ [интерфейса ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)
 Расширяет интерфейс [ICorDebugObjectValue](icordebugobjectvalue-interface.md) для предоставления сведений о трассировке стека из управляемого объекта исключения.  
  
 [Интерфейс ICorDebugFrame](icordebugframe-interface.md)\
 Представляет кадр текущего стека.  
  
 \ [интерфейса ICorDebugFrameEnum](icordebugframeenum-interface.md)
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugFrame`.  
  
 [Интерфейс ICorDebugFunction](icordebugfunction-interface1.md)\
 Представляет управляемую функцию или метод.  
  
 \ [интерфейса ICorDebugFunction2](icordebugfunction2-interface.md)
 Локально расширяет интерфейс `ICorDebugFunction` для предоставления поддержки отладки в пошаговом режиме "Только мой код".  
  
 \ [интерфейса ICorDebugFunction3](icordebugfunction3-interface.md)
 Логически расширяет интерфейс [ICorDebugFunction](icordebugfunction-interface1.md) , чтобы предоставить доступ к коду из запроса ReJIT.  
  
 \ [интерфейса ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)
 Расширяет интерфейс `ICorDebugBreakpoint` для поддержки точек останова в функциях.  
  
 \ [интерфейса ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)
 Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.  
  
 \ [интерфейса ICorDebugGenericValue](icordebuggenericvalue-interface.md)
 Подкласс интерфейса `ICorDebugValue`, применяемый ко всем значениям. Этот интерфейс предоставляет для значения методы Get и Set.  
  
 \ [интерфейса ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)
 Предоставляет перечислитель для объекта, сопоставляющего идентификаторы GUID и соответствующие объекты `ICorDebugType`.  
  
 \ [интерфейса ICorDebugHandleValue](icordebughandlevalue-interface.md)
 Подкласс интерфейса `ICorDebugReferenceValue`, представляющий значение ссылки, для которого отладчик создал дескриптор сборки мусора.  
  
 \ [интерфейса икордебугхеапенум](icordebugheapenum-interface.md)
 Предоставляет перечислитель для объектов в управляемой куче.  
  
 \ [интерфейса икордебугхеапсегментенум](icordebugheapsegmentenum-interface.md)
 Предоставляет перечислитель для областей памяти управляемой кучи.  
  
 \ [интерфейса ICorDebugHeapValue](icordebugheapvalue-interface.md)
 Подкласс интерфейса `ICorDebugValue`, представляющий объект, подобранный сборщиком мусора среды CLR.  
  
 \ [интерфейса ICorDebugHeapValue2](icordebugheapvalue2-interface1.md)
 Расширение интерфейса `ICorDebugHeapValue`, предоставляющее поддержку дескрипторов среды выполнения.  
  
 \ [интерфейса ICorDebugHeapValue3](icordebugheapvalue3-interface.md)
 Предоставляет свойства блокировки монитора объектов.  
  
 \ [интерфейса икордебугилкоде](icordebugilcode-interface.md)
 Представляет сегмент кода промежуточного языка.  
  
 \ [интерфейса ICorDebugILCode2](icordebugilcode2-interface.md)
 Логически расширяет интерфейс [икордебугилкоде](icordebugilcode-interface.md) , чтобы предоставить методы, которые возвращают маркер для сигнатуры локальной переменной функции и сопоставляют смещенные промежуточные языки (IL) профилировщика с исходными смещениями Il метода.  
  
 \ [интерфейса ICorDebugILFrame](icordebugilframe-interface.md)
 Предоставляет кадр стека кода MSIL.  
  
 \ [интерфейса ICorDebugILFrame2](icordebugilframe2-interface.md)
 Логическое расширение интерфейса `ICorDebugILFrame`.  
  
 \ [интерфейса ICorDebugILFrame3](icordebugilframe3-interface.md)
 Предоставляет метод, инкапсулирующий возвращаемое значение функции.  
  
 \ [интерфейса ICorDebugILFrame4](icordebugilframe4-interface.md)
 Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка. Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.  
  
 \ [интерфейса ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)
 Представляет сведения отладочного символа для поля экземпляра. **Доступно только на .NET Native.**  
  
 \ [интерфейса ICorDebugInternalFrame](icordebuginternalframe-interface.md)
 Задает типы кадров для отладчика.  
  
 \ [интерфейса ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)
 Предоставляет сведения о внутренних кадрах, включая адрес стека и расположение по отношению к объектам [ICorDebugFrame](icordebugframe-interface.md) .  
  
 \ [интерфейса икордебуглоадедмодуле](icordebugloadedmodule-interface.md)
 Предоставляет сведения о загруженном модуле. **Доступно только на .NET Native.**  
  
 \ [интерфейса ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
 Предоставляет методы для обработки обратных вызовов отладчика.  
  
 \ [интерфейса ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
 Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA). Интерфейс `ICorDebugManagedCallback2` является логическим расширением интерфейса `ICorDebugManagedCallback`.  
  
 \ [интерфейса ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)
 Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.  
  
 \ [интерфейса ICorDebugMDA](icordebugmda-interface.md)
 Представляет сообщение управляемого помощника по отладке (MDA).  
  
 \ [интерфейса икордебугмеморибуффер](icordebugmemorybuffer-interface.md)
 Представляет буфер в памяти. **Доступно только на .NET Native.**  
  
 \ [интерфейса икордебугмержедассемблирекорд](icordebugmergedassemblyrecord-interface.md)
 Предоставляет сведения о сборке после слияния. **Доступно только на .NET Native.**  
  
 \ [интерфейса икордебугметадаталокатор](icordebugmetadatalocator-interface.md)
 Предоставляет сведения о метаданных для отладчика.  
  
 \ [интерфейса ICorDebugModule](icordebugmodule-interface.md)
 Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).  
  
 \ [интерфейса ICorDebugModule2](icordebugmodule2-interface.md)
 Служит логическим расширением интерфейса `ICorDebugModule`.  
  
 \ [интерфейса метод icordebugmodule3](icordebugmodule3-interface.md)
 Создает средство чтения символов для динамического модуля.  
  
 \ [интерфейса икордебугмодулебреакпоинт](icordebugmodulebreakpoint-interface.md)
 Расширяет интерфейс `ICorDebugBreakpoint` для предоставления доступа к указанным модулям.  
  
 \ [интерфейса икордебугмодуледебужевент](icordebugmoduledebugevent-interface.md)
 Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий уровня модуля. **Доступно только на .NET Native.**  
  
 \ [интерфейса икордебугмодулинум](icordebugmoduleenum-interface.md)
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugModule`.  
  
 \ [интерфейса икордебугмутабледататаржет](icordebugmutabledatatarget-interface.md)
 Расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) для поддержки целевых объектов данных.  
  
 \ [интерфейса ICorDebugNativeFrame](icordebugnativeframe-interface.md)
 Специализированная реализация интерфейса `ICorDebugFrame`, используемая для кадров машинного кода.  
  
 \ [интерфейса ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)
 Предоставляет методы, проверяющие для кадров наличие взаимоотношений типа "дочерний-родительский".  
  
 \ [интерфейса икордебугобжектенум](icordebugobjectenum-interface.md)
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).  
  
 \ [интерфейса ICorDebugObjectValue](icordebugobjectvalue-interface.md)
 Подкласс `ICorDebugValue`, представляющий значение, содержащее объект.  
  
 \ [интерфейса ICorDebugObjectValue2](icordebugobjectvalue2-interface.md)
 Расширяет интерфейс `ICorDebugObjectValue` для поддержки наследования и переопределений.  
  
 \ [интерфейса ICorDebugProcess](icordebugprocess-interface.md)
 Представляет процесс, выполняющий управляемый код.  
  
 \ [интерфейса ICorDebugProcess2](icordebugprocess2-interface1.md)
 Логическое расширение интерфейса `ICorDebugProcess`.  
  
 \ [интерфейса ICorDebugProcess3](icordebugprocess3-interface.md)
 Управляет пользовательскими уведомлениями отладчика.

 \ [интерфейса ICorDebugProcess4](icordebugprocess4-interface.md)
 Обеспечивает поддержку управления выполнением в процессе.
  
 \ [интерфейса метод ICorDebugProcess5](icordebugprocess5-interface.md)
 Расширяет интерфейс [ICorDebugProcess](icordebugprocess-interface.md) для поддержки доступа к управляемой куче, предоставляет сведения о сборке мусора управляемых объектов и определяет, загружает ли отладчик изображения из локального кэша образов в машинном код.  
  
 \ [интерфейса ICorDebugProcess6](icordebugprocess6-interface.md)
 Логически расширяет интерфейс [ICorDebugProcess](icordebugprocess-interface.md) , позволяя выполнять такие функции, как декодирование управляемых событий отладки, которые кодируются в событиях отладки машинного кода и разбиении виртуального модуля. **Доступно только на .NET Native.**  
  
 \ [интерфейса ICorDebugProcess7](icordebugprocess7-interface.md)
 Предоставляет метод, который настраивает отладчик для обработки обновлений находящихся в памяти метаданных в целевом процессе.  
  
 \ [интерфейса ICorDebugProcess8](icordebugprocess8-interface.md)
 Логически расширяет интерфейс [ICorDebugProcess](icordebugprocess-interface.md) , чтобы включать или отключать определенные типы обратных вызовов исключений [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
 \ [интерфейса икордебугпроцессенум](icordebugprocessenum-interface.md)
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugProcess`.  
  
 \ [интерфейса ICorDebugReferenceValue](icordebugreferencevalue-interface.md)
 Подкласс интерфейса `ICorDebugValue`, поддерживающего ссылочные типы.  
  
 \ [интерфейса ICorDebugRegisterSet](icordebugregisterset-interface.md)
 Представляет набор регистров, доступных для компьютера, на котором в данный момент выполняется код.  
  
 \ [интерфейса ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
 Расширяет возможности интерфейса `ICorDebugRegisterSet` для аппаратных платформ, количество регистров которых превышает 64.  
  
 \ [интерфейса метод icordebugremote](icordebugremote-interface.md)
 Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.  
  
 \ [интерфейса ICorDebugRemoteTarget](icordebugremotetarget-interface.md)
 Предоставляет методы, позволяющие отлаживать приложения на основе Silverlight в среде CLR.  
  
 \ [интерфейса икордебугрунтимеунвиндаблефраме](icordebugruntimeunwindableframe-interface.md)
 Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.  
  
 \ [интерфейса икордебугстакквалк](icordebugstackwalk-interface.md)
 Обеспечивает методы для получения управляемых методов или кадров в стеке потока.  
  
 \ [интерфейса икордебугстатикфиелдсимбол](icordebugstaticfieldsymbol-interface.md)
 Представляет сведения символа отладки для статического поля. **Доступно только на .NET Native.**  
  
 [Интерфейс ICorDebugStepper](icordebugstepper-interface.md)\
 Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.  
  
 \ [интерфейса ICorDebugStepper2](icordebugstepper2-interface1.md)
 Предоставляет поддержку отладки "Только мой код".  
  
 \ [интерфейса икордебугстепперенум](icordebugstepperenum-interface.md)
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugStepper`.  
  
 \ [интерфейса ICorDebugStringValue](icordebugstringvalue-interface.md)
 Подкласс `ICorDebugHeapValue`, применяемый к строковым значениям.  
  
 \ [интерфейса метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md)
 Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах. **Доступно только на .NET Native.**  
  
 \ [интерфейса ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)
 Логически расширяет интерфейс [метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md) для получения дополнительных сведений об отладочных символах. **Доступно только на .NET Native.**  
  
 [Интерфейс ICorDebugThread](icordebugthread-interface.md)\
 Представляет поток в процессе. Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.  
  
 \ [интерфейса ICorDebugThread2](icordebugthread2-interface.md)
 Служит логическим расширением интерфейса `ICorDebugThread`.  
  
 \ [интерфейса ICorDebugThread3](icordebugthread3-interface.md)
 Предоставляет точку входа для [икордебугстакквалк](icordebugstackwalk-interface.md) и соответствующих интерфейсов.  
  
 \ [интерфейса ICorDebugThread4](icordebugthread4-interface.md)
 Предоставляет сведения о блокировке потока.  
  
 \ [интерфейса икордебугсреаденум](icordebugthreadenum-interface1.md)
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugThread`.  
  
 \ [интерфейса ICorDebugType](icordebugtype-interface.md)
 Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.  
  
 \ [интерфейса ICorDebugType2](icordebugtype2-interface.md)
 Расширяет интерфейс [ICorDebugType](icordebugtype-interface.md) для получения идентификатора типа базового типа или сложного (определяемого пользователем) типа.  
  
 \ [интерфейса ICorDebugTypeEnum](icordebugtypeenum-interface.md)
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugType`.  
  
 \ [интерфейса икордебугунманажедкаллбакк](icordebugunmanagedcallback-interface.md)
 Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно со средой CLR.  
  
 \ [ICorDebugValue](icordebugvalue-interface.md)
 Представляет значение для записи или чтения в отлаживаемом процессе.  
  
 [ICorDebugValue2](icordebugvalue2-interface.md)\
 Расширяет интерфейс `ICorDebugValue` для предоставления поддержки интерфейса `ICorDebugType`.  
  
 \ [интерфейса ICorDebugValue3](icordebugvalue3-interface.md)
 Расширяет интерфейсы "ICorDebugValue" и "ICorDebugValue2", чтобы обеспечить поддержку массивов, размер которых превышает 2 ГБ.  
  
 [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\
 Расширяет интерфейс `ICorDebugBreakpoint` для обеспечения доступа к указанным значениям.  
  
 [ICorDebugValueEnum](icordebugvalueenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugValue`.  
  
 \ [интерфейса ICorDebugVariableHome](icordebugvariablehome-interface.md)
 Представляет локальную переменную или аргумент функции.  
  
 \ [интерфейса ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)
 Предоставляет перечислитель для локальных переменных и аргументов в функции.  
  
 \ [интерфейса ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)
 Извлекает сведения символа отладки для статического поля. **Доступно только на .NET Native.**  
  
 \ [интерфейса ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)
 Предоставляет методы, помогающие очистить стек. **Доступно только на .NET Native.**  
  
 \ [интерфейса ICorPublish](icorpublish-interface.md)
 Служит универсальным интерфейсом для процессов публикации.  
  
 \ [интерфейса ICorPublishAppDomain](icorpublishappdomain-interface.md)
 Представляет и предоставляет информацию о домене приложения.  
  
 \ [интерфейса ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)
 Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishAppDomain`, существующих в процессе в данный момент.  
  
 \ [интерфейса ICorPublishEnum](icorpublishenum-interface.md)
 Служит абстрактной базой для перечислителей публикации.  
  
 \ [интерфейса ICorPublishProcess](icorpublishprocess-interface.md)
 Предоставляет методы, позволяющие получить доступ к сведениям о процессе.  
  
 \ [интерфейса ICorPublishProcessEnum](icorpublishprocessenum-interface.md)
 Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishProcess`.  

 \ [интерфейса исосдаЦинтерфаце](isosdacinterface-interface.md)
 Предоставляет вспомогательные методы для доступа к данным из `SOS`.

 \ [интерфейса иксклрдатамесоддефинитион](ixclrdatamethoddefinition-interface.md)
 Предоставляет методы для запроса сведений об определении метода.
 
 \ [интерфейса иксклрдатамесодинстанце](ixclrdatamethodinstance-interface.md)
 Предоставляет методы для запроса сведений об экземпляре метода.
 
 \ [интерфейса иксклрдатамодуле](ixclrdatamodule-interface.md)
 Предоставляет методы для запроса сведений о загруженном модуле.
 
 \ [интерфейса иксклрдатапроцесс](ixclrdataprocess-interface.md)
 Предоставляет методы для запроса сведений о процессе.
  
## <a name="related-sections"></a>Связанные разделы  
 [Коклассы отладки](debugging-coclasses.md)\
 [Отладка глобальных статических функций](debugging-global-static-functions.md)\
 \ [перечисления отладки](debugging-enumerations.md)
 [Отладка структур](debugging-structures.md)\
