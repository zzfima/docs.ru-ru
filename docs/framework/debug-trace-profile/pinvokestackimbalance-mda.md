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
ms.openlocfilehash: 5594166081c36fbda1e5d1a62e017aaceb7a553d
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42912118"
---
# <a name="pinvokestackimbalance-mda"></a>PInvokeStackImbalance MDA

`PInvokeStackImbalance` Помощник по отладке управляемого (кода MDA) активируется в том случае, когда среда CLR обнаруживает, что глубина стека после вызова неуправляемого кода не соответствует ожидаемой глубине стека, учитывая соглашение о вызовах, указанное в <xref:System.Runtime.InteropServices.DllImportAttribute> атрибут и Объявление параметров в управляемой подписи.

MDA `PInvokeStackImbalance` реализован только для 32-разрядных платформ x86.

> [!NOTE]
> `PInvokeStackImbalance` MDA отключен по умолчанию. В Visual Studio 2017 `PInvokeStackImbalance` MDA отображается в **Помощники отладки управляемого кода** в списке **параметры исключений** диалоговое окно (которое отображается при выборе **Отладка**  >  **Windows** > **параметры исключений**). Тем не менее, установив или сняв **прервать при исключение** "флажок" включить или отключить MDA; управляет только тем, вызывает ли Visual Studio исключение, когда MDA активирован.

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

**Вызов функции PInvoke «SampleMethod» внесла дисбаланс в стек. Это обусловлено тем, скорее всего, управляемая сигнатура PInvoke не соответствует сигнатуре неуправляемого целевой. Проверьте, что соглашение о вызовах и параметры подписи PInvoke соответствовать неуправляемой сигнатуре целевой объект.**

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
- [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../../../docs/framework/interop/interop-marshaling.md)
