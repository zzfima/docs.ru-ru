---
title: pInvokeStackImbalance MDA
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- stack depth
- platform invoke stack imbalance
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- PInvokeStackImbalance MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: 34ddc6bd-1675-4f35-86aa-de1645d5c631
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc4a48c79fc39b12f8231bd913b4ca8970c0f46f
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052357"
---
# <a name="pinvokestackimbalance-mda"></a>PInvokeStackImbalance MDA

Помощник по отладке <xref:System.Runtime.InteropServices.DllImportAttribute> управляемогокода(MDA)активируется,когдасредаCLRобнаруживает,чтоглубинастекапослевызованеуправляемогокоданесоответствуетожидаемойглубинестека,учитываясоглашениеовызовах,указанное`PInvokeStackImbalance` в атрибуте и объявление параметров в управляемой сигнатуре.

MDA `PInvokeStackImbalance` реализован только для 32-разрядных платформ x86.

> [!NOTE]
> По `PInvokeStackImbalance` умолчанию MDA отключен. В Visual `PInvokeStackImbalance` Studio 2017 MDA отображается в списке **помощников по отладке управляемого** кода в диалоговом окне **параметры исключений** (отображается при выборе**окна**  >  >  **Отладка). Параметры исключений**). Однако установка или снятие флажка **прерывать при возникновении** не включает и не отключает MDA. Он только определяет, создает ли Visual Studio исключение при активации MDA.

## <a name="symptoms"></a>Симптомы

В приложении обнаружено нарушение прав доступа или повреждение памяти при выполнении или отслеживании вызова неуправляемого кода.

## <a name="cause"></a>Причина

Управляемая сигнатура вызова неуправляемого кода может не соответствовать неуправляемой сигнатуре вызываемого метода.  Это несоответствие может быть вызвано тем, что управляемая сигнатура не объявляет правильное количество параметров или не задает соответствующий размер для этих параметров.  MDA также может активироваться, поскольку соглашение о вызовах, возможно указанное атрибутом <xref:System.Runtime.InteropServices.DllImportAttribute>, не соответствует соглашению о вызовах неуправляемого кода.

## <a name="resolution"></a>Решение

Просмотрите сигнатуру вызова неуправляемого кода и соглашение о вызовах, чтобы убедиться, что они соответствуют сигнатуре и соглашению о вызовах исходного целевого объекта.  Попробуйте явным образом задать соглашение о вызовах для управляемой и неуправляемой сторон. Также возможно, хотя и маловероятно, что неуправляемая функция внесла дисбаланс в стек по какой-либо другой причине, например из-за ошибки в неуправляемом компиляторе.

## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения

Заставляет все вызовы неуправляемого кода принимать неоптимизированный путь в среде CLR.

## <a name="output"></a>Вывод

Сообщение MDA предоставляет имя вызова метода вызова неуправляемого кода, который привел к несбалансированности стека вызова. Пример сообщения вызова неуправляемого кода в методе `SampleMethod`:

**Вызов функции PInvoke "SampleMethod" не сбалансирован стек. Скорее всего, это связано с тем, что управляемая сигнатура PInvoke не соответствует неуправляемой сигнатуре целевого объекта. Убедитесь, что соглашение о вызовах и параметры сигнатуры PInvoke соответствуют целевой неуправляемой подписи.**

## <a name="configuration"></a>Конфигурация

```xml
<mdaConfig>
  <assistants>
    <pInvokeStackImbalance />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
