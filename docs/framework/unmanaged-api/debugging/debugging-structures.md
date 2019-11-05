---
title: Структуры отладки
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: 05a321d5025f03d6a0378b462178bf06c0291f48
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123031"
---
# <a name="debugging-structures"></a>Структуры отладки

В этом разделе описаны неуправляемые структуры, которые использует API отладки.

## <a name="in-this-section"></a>Содержание
 [Структура CLRDATA_ADDRESS_RANGE](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Определяет диапазон адресов.

 [Структура CLRDATA_IL_ADDRESS_MAP](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Определяет IL для сопоставления адресов

 [Структура CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Определяет версию продукта среды CLR для целей отладки.

 [Структура кодечункинфо](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Представляет отдельный фрагмент кода в памяти.

 [COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Содержит сведения о функциях, которые в данный момент активны в кадрах потока.

 [Структура COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Предоставляет сведения о макете объекта массива в памяти.

 [COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Содержит смещения, используемые для преобразования кода MSIL в машинный код.

 [COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Содержит сведения о смещении для диапазона кода.

 [Структура COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Предоставляет сведения о поле в объекте.

 [Структура COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Содержит сведения об объекте, который должен быть собран в мусор.

 [Структура COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Содержит общие сведения о куче сборки мусора, в том числе о том, является ли она перечислимой.

 [Структура COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Предоставляет сведения об объекте в управляемой куче.

 [COR_IL_MAP](cor-il-map-structure.md) Задает изменения в относительном смещении функции.

 [Структура COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Содержит сведения о области памяти в управляемой куче.

 [Структура COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Содержит идентификатор типа.

 [Структура COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Предоставляет сведения о макете объекта в памяти.

 [COR_VERSION](cor-version-structure.md) Хранит Стандартный номер версии, сообщая из четырех частей, для общеязыковой среды выполнения.

 [Структура CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Определяет объект, который блокирует поток и причину блокировки потока.

 [Структура кордебужехклаусе](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Представляет предложение обработки исключений (EH) для заданного фрагмента промежуточного языка (IL).

 [Структура кордебужексцептионобжектстаккфраме](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Представляет сведения о кадре стека из объекта исключения.

 [Структура кордебуггуидтотипемаппинг](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Сопоставляет идентификатор GUID среда выполнения Windows с соответствующим объектом [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) .

 [Структура дакпжетмодулеаддресс](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Определяет контейнер для запроса адреса модуля.

 [Структура дакпмесоддескдата](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Определяет транспортный буфер для сведений о среде выполнения метода.

 [Структура дакпмодуледата](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Определяет транспортный буфер для сведений о среде выполнения модуля.

 [Структура дакпрежитдата](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Определяет основные сведения о конкретном инструментированном методе профилирования.

 [Структура StackTrace_SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Предоставляет простой контекст, который можно использовать вместо полной структуры `CONTEXT`.

## <a name="related-sections"></a>Связанные разделы

 [Коклассы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [Глобальные статические функции отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
