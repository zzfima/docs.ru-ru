---
title: Структуры отладки
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
ms.openlocfilehash: a18094fb2621478dbdb4bbf672df436234112ed0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793757"
---
# <a name="debugging-structures"></a>Структуры отладки

В этом разделе описаны неуправляемые структуры, которые использует API отладки.

## <a name="in-this-section"></a>В этом разделе
 [Структура CLRDATA_ADDRESS_RANGE](clrdata-address-range-structure.md) Определяет диапазон адресов.

 [Структура CLRDATA_IL_ADDRESS_MAP](clrdata-il-address-map-structure.md) Определяет IL для сопоставления адресов

 [Структура CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) Определяет версию продукта среды CLR для целей отладки.

 [Структура кодечункинфо](codechunkinfo-structure.md) Представляет отдельный фрагмент кода в памяти.

 [COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Содержит сведения о функциях, которые в данный момент активны в кадрах потока.

 [Структура COR_ARRAY_LAYOUT](cor-array-layout-structure.md) Предоставляет сведения о макете объекта массива в памяти.

 [COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Содержит смещения, используемые для преобразования кода MSIL в машинный код.

 [COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Содержит сведения о смещении для диапазона кода.

 [Структура COR_FIELD](cor-field-structure.md) Предоставляет сведения о поле в объекте.

 [Структура COR_GC_REFERENCE](cor-gc-reference-structure.md) Содержит сведения об объекте, который должен быть собран в мусор.

 [Структура COR_HEAPINFO](cor-heapinfo-structure.md) Содержит общие сведения о куче сборки мусора, в том числе о том, является ли она перечислимой.

 [Структура COR_HEAPOBJECT](cor-heapobject-structure.md) Предоставляет сведения об объекте в управляемой куче.

 [COR_IL_MAP](cor-il-map-structure.md) Задает изменения в относительном смещении функции.

 [Структура COR_SEGMENT](cor-segment-structure.md) Содержит сведения о области памяти в управляемой куче.

 [Структура COR_TYPEID](cor-typeid-structure.md) Содержит идентификатор типа.

 [Структура COR_TYPE_LAYOUT](cor-type-layout-structure.md) Предоставляет сведения о макете объекта в памяти.

 [COR_VERSION](cor-version-structure.md) Хранит Стандартный номер версии, сообщая из четырех частей, для общеязыковой среды выполнения.

 [Структура CorDebugBlockingObject](cordebugblockingobject-structure.md) Определяет объект, который блокирует поток и причину блокировки потока.

 [Структура кордебужехклаусе](cordebugehclause-structure.md) Представляет предложение обработки исключений (EH) для заданного фрагмента промежуточного языка (IL).

 [Структура кордебужексцептионобжектстаккфраме](cordebugexceptionobjectstackframe-structure.md) Представляет сведения о кадре стека из объекта исключения.

 [Структура кордебуггуидтотипемаппинг](cordebugguidtotypemapping-structure.md) Сопоставляет идентификатор GUID среда выполнения Windows с соответствующим объектом [ICorDebugType](icordebugtype-interface.md) .

 [Структура дакпжетмодулеаддресс](dacpgetmoduleaddress-structure.md) Определяет контейнер для запроса адреса модуля.

 [Структура дакпмесоддескдата](dacpmethoddescdata-structure.md) Определяет транспортный буфер для сведений о среде выполнения метода.

 [Структура дакпмодуледата](dacpmoduledata-structure.md) Определяет транспортный буфер для сведений о среде выполнения модуля.

 [Структура дакпрежитдата](dacprejitdata-structure.md) Определяет основные сведения о конкретном инструментированном методе профилирования.

 [Структура StackTrace_SimpleContext](stacktrace-simplecontext-structure.md) Предоставляет простой контекст, который можно использовать вместо полной структуры `CONTEXT`.

## <a name="related-sections"></a>Связанные разделы

 [Коклассы отладки](debugging-coclasses.md)

 [Интерфейсы отладки](debugging-interfaces.md)

 [Глобальные статические функции отладки](debugging-global-static-functions.md)

 [Перечисления отладки](debugging-enumerations.md)

 [Отладка](index.md)
