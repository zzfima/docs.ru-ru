---
title: Структуры отладки
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18bf03fee1a95c898e8273fa839e41a86b2d1c32
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828375"
---
# <a name="debugging-structures"></a>Структуры отладки
В этом разделе описаны неуправляемые структуры, которые использует API отладки.

## <a name="in-this-section"></a>В этом разделе
 [Структура CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) определяет диапазон адресов.

 [Структура CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) определяет инструкцию IL для сопоставления адресов

 [Структура CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) определяет версию среды выполнения (CLR) для целей отладки.

 [Структура1 codechunkinfo](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) представляет одинарный блок кода в памяти.

 [COR_ACTIVE_FUNCTION](cor-active-function-structure.md) содержит сведения о функциях, которые в настоящее время активны в кадрах потока.

 [Структура COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) предоставляет сведения о расположении объекта массива в памяти.

 [COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) содержит смещения, которые используются для сопоставления промежуточного языка Майкрософт (MSIL) кода в машинный код.

 [COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) содержит сведения о смещении для диапазона кода.

 [Структура COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) предоставляет сведения о поле в объекте.

 [Структура COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) содержит сведения об объекте, который должен быть сборщиком мусора.

 [Структура COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) содержит общие сведения о куче для сборки мусора, включая ли он является перечислимым.

 [Структура COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) предоставляет сведения об объекте в управляемой куче.

 [COR_IL_MAP](cor-il-map-structure.md) определяет изменения в относительном смещении функции.

 [Структура COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) содержит сведения об области памяти в управляемой куче.

 [Структура COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) содержит идентификатор типа.

 [Структура COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) предоставляет сведения о расположении объекта в памяти.

 [COR_VERSION](cor-version-structure.md) хранит номер версии standard из четырех частей среда CLR.

 [Структура CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) определяет объект, который блокирует поток и причину, почему поток блокируется.

 [Структура CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) представляет предложение обработки (EH) исключения для данной части промежуточный язык (IL).

 [Структура CorDebugExceptionObjectStackFrame](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) представляет сведения о кадре от объекта исключения стека.

 [Структура CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Соответствующим [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) объекта.

 [Структура DacpGetModuleAddress](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) определяет контейнер для запроса адрес модуля.

 [Структура DacpMethodDescData](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) определяет буфер транспорта сведения среды выполнения метода.

 [Структура DacpModuleData](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) определяет буфер транспорта для модуля сведения среды выполнения.

 [Структура DacpReJitData](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) , определяющего основную информацию о данный метод инструментированного профилировщиком.

 [Структура StackTrace_SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) обеспечивает простой контекст, который может использоваться вместо полной `CONTEXT` структуры.



## <a name="related-sections"></a>Связанные разделы
 [Коклассы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
