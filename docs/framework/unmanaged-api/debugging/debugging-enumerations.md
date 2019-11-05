---
title: Перечисления отладки
ms.date: 03/30/2017
helpviewer_keywords:
- debugging enumerations [.NET Framework]
- unmanaged enumerations [.NET Framework], debugging
- enumerations [.NET Framework debugging]
ms.assetid: 3af9f584-f1b4-4154-aeaa-8fce7c9f8b50
ms.openlocfilehash: 7948b78da1db5267ce53364af1e4a26ff73801e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124335"
---
# <a name="debugging-enumerations"></a>Перечисления отладки
В этом разделе описываются неуправляемые перечисления, которые использует API отладки.  
  
## <a name="in-this-section"></a>Содержание  
 [Перечисление CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)  
 Предоставляет значения, используемые методом [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) .  
  
 [Перечисление CLRDataEnumMemoryFlags](../../../../docs/framework/unmanaged-api/debugging/clrdataenummemoryflags-enumeration.md)  
 Указывает, к каким областям памяти должен быть вызван вызов метода [иклрдатаенуммеморирегионс:: енуммеморирегионс](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) .  
  
 [Перечисление COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md)  
 Идентифицирует тип процесса для перечисления.  
  
 [Перечисление CorDebugBlockingReason](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingreason-enumeration.md)  
 Указывает возможные причины блокировки потока на данном объекте.  
  
 кордебугчаинреасон  
 Указывает причину или причины запуска цепочки вызовов.  
  
 [Перечисление CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md)  
 Описывает, каким образом экспортируемая функция вызывает управляемый код.  
  
 [Перечисление CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md)  
 Описывает, почему экспортируемая функция вызывает управляемый код.  
  
 кордебугкреатепроцессфлагс  
 Предоставляет дополнительные параметры отладки, которые можно использовать при вызове метода [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) .  
  
 [Перечисление CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md)  
 Указывает тип события, сведения о котором декодированы методом [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) .  
  
 [Перечисление CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md)  
 Предоставляет дополнительную информацию о событиях отладки на платформе Windows.  
  
 CorDebugExceptionCallbackType  
 Указывает тип обратного вызова, сделанный из события [ICorDebugManagedCallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) .  
  
 [Перечисление CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)  
 Предоставляет дополнительные сведения об исключении.  
  
 кордебужексцептионунвиндкаллбакктипе  
 Указывает событие, о котором сообщает обратный вызов во время фазы перемотки.  
  
 [Перечисление CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)  
 Указывает, где выполняется сборщик мусора: на рабочей станции или на сервере.  
  
 [Перечисление CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md)  
 Указывает на создание области памяти в управляемой куче.  
  
 кордебугхандлетипе  
 Указывает тип обработки.  
  
 [Перечисление CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md)  
 Указывает, соответствует ли определенный диапазон машинных инструкций специальной области кода.  
  
 CorDebugIntercept  
 Указывает типы кода, который может быть пошагово выполнен.  
  
 [Перечисление CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md)  
 Указывает либо версию платформы .NET Framework, либо версию платформы .NET Framework, в которой был представлен интерфейс.  
  
 CorDebugInternalFrameType  
 Указывает тип кадра стека.  
  
 [Перечисление CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md)  
 Содержит значения, которые влияют на поведение управляемого JIT-компилятора.  
  
 [Перечисление CorDebugJITCompilerFlagsDeprecated](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflagsdeprecated-enumeration.md)  
 Является устаревшей. Вместо этого используйте элемент `CORDEBUG_JIT_DEFAULT` перечисления [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) .  
  
 кордебугмаппингресулт  
 Предоставляет сведения о том, как было получено значение указателя инструкций.  
  
 [Перечисление CorDebugMDAFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugmdaflags-enumeration.md)  
 Указывает состояние потока, по которому был вызван помощник по отладке управляемого кода.  
  
 [Перечисление CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)  
 Предоставляет значение, который определяет, загружает ли отладчик образы в машинном коде (NGen) из кэша образов в машинном коде.  
  
 [Перечисление CorDebugPlatform](../../../../docs/framework/unmanaged-api/debugging/cordebugplatform-enumeration.md)  
 Предоставляет значения целевой платформы, используемые методом [ICorDebugDataTarget::](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) WebMethod.  
  
 [Перечисление CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
 Описывает формат данных в массиве байтов, который содержит информацию о событии отладки собственного исключения.  
  
 CorDebugRegister  
 Указывает регистры, связанные с данной архитектурой процессора.  
  
 [Перечисление CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md)  
 Указывает происхождение контекста: взят из активного (или листового) кадра в стеке или был вычислен в результате освобождения другого кадра.  
  
 [Перечисление CorDebugStateChange](../../../../docs/framework/unmanaged-api/debugging/cordebugstatechange-enumeration.md)  
 Описывает объем кэшированных данных, которые должны быть отброшены на основе изменений, внесенных в процесс.  
  
 кордебугстепреасон  
 Указывает результат отдельного шага.  
  
 кордебугсреадстате  
 Указывает состояние потока для отладки.  
  
 \>Кордебугунмаппедстоп  
 Указывает тип несопоставимого кода, который может привести к прерыванию выполнения кода пошаговым средством.  
  
 кордебугусерстате  
 Указывает состояние пользователя потока.  
  
 [Перечисление CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md)  
 Идентифицирует источник объекта, в котором должна быть выполнена сборка мусора.  
  
 [Перечисление ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md)  
 Предоставляет значения, которые указывают, может ли отладчик получить доступ к локальным переменным или коду, добавленным в инструментарий ReJIT профилировщика.  
  
 [Перечисление LoggingLevelEnum](../../../../docs/framework/unmanaged-api/debugging/logginglevelenum-enumeration.md)  
 Указывает уровень важности описательного сообщения, записанного в журнале событий при регистрации события управляемым потоком.  
  
 [Перечисление LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md)  
 Указывает операцию, выполненную на переключателе отладки и трассировки.  
  
 [Перечисление VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 Указывает тип собственного расположения переменной.  
  
 [Перечисление WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md)  
 Предоставляет значения, указывающие, будут ли видны в отладчике обновления копии метаданных в памяти. 

 [Перечисление клрдатасаурцетипе](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md) Предоставляет значения, используемые структурой CLRDATA_IL_ADDRESS_MAP.

## <a name="related-sections"></a>Связанные разделы  
 [Коклассы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [Структуры отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
