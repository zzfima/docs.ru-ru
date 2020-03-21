---
title: Перечисления отладки
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: c37b6ff42b428184d301d63b6dbbd9d80a72bf3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179143"
---
# <a name="debugging-enumerations"></a>Перечисления отладки
В этом разделе описываются неуправляемые перечисления, которые использует API отладки.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Перечисление CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md)  
 Предоставляет значения, используемые методом [ICLRDebugging::OpenVirtualProcess.](iclrdebugging-openvirtualprocess-method.md)  
  
 [Перечисление CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md)  
 Указывает, в какие области памяти должен быть включен вызов [iCLRDataEnumMemoryRegions::EnumMemoryRegions.](iclrdataenummemoryregions-enummemoryregions-method.md)  
  
 [Перечисление COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md)  
 Идентифицирует тип процесса для перечисления.  
  
 [Перечисление CorDebugBlockingReason](cordebugblockingreason-enumeration.md)  
 Указывает возможные причины блокировки потока на данном объекте.  
  
 CorDebugChainReason  
 Указывает причину или причины запуска цепочки вызовов.  
  
 [Перечисление CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md)  
 Описывает, каким образом экспортируемая функция вызывает управляемый код.  
  
 [Перечисление CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md)  
 Описывает, почему экспортируемая функция вызывает управляемый код.  
  
 CorDebugCreateProcessFlags  
 Предоставляет дополнительные параметры отладки, которые могут быть использованы при вызове к методу [ICorDebug::CreateProcess.](icordebug-createprocess-method.md)  
  
 [Перечисление CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md)  
 Указывает тип события, информация которого расшифровывается методом [DecodeEvent.](icordebugprocess6-decodeevent-method.md)  
  
 [Перечисление CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md)  
 Предоставляет дополнительную информацию о событиях отладки на платформе Windows.  
  
 CorDebugExceptionCallbackType  
 Указывает тип обратного вызова, который сделан из [ICorDebugManagedCallback2::Исключение](icordebugmanagedcallback2-exception-method.md) события.  
  
 [Перечисление CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md)  
 Предоставляет дополнительные сведения об исключении.  
  
 CorDebugExceptionUnwindCallbackType  
 Указывает событие, о котором сообщает обратный вызов во время фазы перемотки.  
  
 [Перечисление CorDebugGCType](cordebuggctype-enumeration.md)  
 Указывает, где выполняется сборщик мусора: на рабочей станции или на сервере.  
  
 [Перечисление CorDebugGenerationTypes](cordebuggenerationtypes-enumeration.md)  
 Указывает на создание области памяти в управляемой куче.  
  
 CorDebugHandleType  
 Указывает тип обработки.  
  
 [Перечисление CorDebugIlToNativeMappingTypes](cordebugiltonativemappingtypes-enumeration.md)  
 Указывает, соответствует ли определенный диапазон машинных инструкций специальной области кода.  
  
 CorDebugIntercept  
 Указывает типы кода, который может быть пошагово выполнен.  
  
 [Перечисление CorDebugInterfaceVersion](cordebuginterfaceversion-enumeration.md)  
 Указывает либо версию платформы .NET Framework, либо версию платформы .NET Framework, в которой был представлен интерфейс.  
  
 CorDebugInternalFrameType  
 Указывает тип кадра стека.  
  
 [Перечисление CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md)  
 Содержит значения, которые влияют на поведение управляемого JIT-компилятора.  
  
 [Перечисление CorDebugJITCompilerFlagsDeprecated](cordebugjitcompilerflagsdeprecated-enumeration.md)  
 Устаревшее. Вместо `CORDEBUG_JIT_DEFAULT` этого используйте список [CorDebugJITCompilerFlags.](cordebugjitcompilerflags-enumeration.md)  
  
 CorDebugMappingResult  
 Предоставляет сведения о том, как было получено значение указателя инструкций.  
  
 [Перечисление CorDebugMDAFlags](cordebugmdaflags-enumeration.md)  
 Указывает состояние потока, по которому был вызван помощник по отладке управляемого кода.  
  
 [Перечисление CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md)  
 Предоставляет значение, который определяет, загружает ли отладчик образы в машинном коде (NGen) из кэша образов в машинном коде.  
  
 [Перечисление CorDebugPlatform](cordebugplatform-enumeration.md)  
 Предоставляет значения целевой платформы, которые используются методом [ICorDebugDataTarget::GetPlatform.](icordebugdatatarget-getplatform-method.md)  
  
 [Перечисление CorDebugRecordFormat](cordebugrecordformat-enumeration.md)  
 Описывает формат данных в массиве байтов, который содержит информацию о событии отладки собственного исключения.  
  
 CorDebugRegister  
 Указывает регистры, связанные с данной архитектурой процессора.  
  
 [Перечисление CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md)  
 Указывает происхождение контекста: взят из активного (или листового) кадра в стеке или был вычислен в результате освобождения другого кадра.  
  
 [Перечисление CorDebugStateChange](cordebugstatechange-enumeration.md)  
 Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.  
  
 CorDebugStepReason  
 Указывает результат отдельного шага.  
  
 CorDebugThreadState  
 Указывает состояние потока для отладки.  
  
 \>CorDebugUnmappedStop  
 Указывает тип несопоставимого кода, который может привести к прерыванию выполнения кода пошаговым средством.  
  
 CorDebugUserState  
 Указывает состояние пользователя потока.  
  
 [Перечисление CorGCReferenceType](corgcreferencetype-enumeration.md)  
 Идентифицирует источник объекта, в котором должна быть выполнена сборка мусора.  
  
 [Перечисление ILCodeKind](ilcodekind-enumeration.md)  
 Предоставляет значения, которые указывают, может ли отладчик получить доступ к локальным переменным или коду, добавленным в инструментарий ReJIT профилировщика.  
  
 [Перечисление LoggingLevelEnum](logginglevelenum-enumeration.md)  
 Указывает уровень важности описательного сообщения, записанного в журнале событий при регистрации события управляемым потоком.  
  
 [Перечисление LogSwitchCallReason](logswitchcallreason-enumeration.md)  
 Указывает операцию, выполненную на переключателе отладки и трассировки.  
  
 [Перечисление VariableLocationType](variablelocationtype-enumeration.md)  
 Указывает тип родного местоположения переменной.  
  
 [Перечисление WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md)  
 Предоставляет значения, указывающие, будут ли видны в отладчике обновления копии метаданных в памяти.

 [Цифра ClrDataSourceType](clrdatasourcetype-enumeration.md) Обеспечивает значения, используемые структурой CLRDATA_IL_ADDRESS_MAP.

## <a name="related-sections"></a>См. также  
 [Компонентные классы отладки](debugging-coclasses.md)  
  
 [Интерфейсы отладки](debugging-interfaces.md)  
  
 [Глобальные статические функции отладки](debugging-global-static-functions.md)  
  
 [Структуры отладки](debugging-structures.md)
