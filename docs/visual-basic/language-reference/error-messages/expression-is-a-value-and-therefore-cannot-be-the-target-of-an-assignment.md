---
title: Нельзя присвоить значение выражению, поскольку оно является значением
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: d5aae4d30abbf9ed2af260412352a5e0452e0dcc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513040"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>Нельзя присвоить значение выражению, поскольку оно является значением

Оператор пытается присвоить значение выражению. Значение можно назначить только переменной с возможностью записи, свойству или элементу массива во время выполнения. В следующем примере показано, как может произойти эта ошибка.

```vb
Dim yesterday As Integer
ReadOnly maximum As Integer = 45
yesterday + 1 = DatePart(DateInterval.Day, Now)
' The preceding line is an ERROR because of an expression on the left.
maximum = 50
' The preceding line is an ERROR because maximum is declared ReadOnly.
```

Аналогичные примеры могут применяться к свойствам и элементам массива.

**Косвенный доступ.** Непрямой доступ через тип значения может также вызвать эту ошибку. Рассмотрим следующий пример кода, который пытается задать значение <xref:System.Drawing.Point> путем прямого доступа к нему через. <xref:System.Windows.Forms.Control.Location%2A>

```vb
' Assume this code runs inside Form1.
Dim exitButton As New System.Windows.Forms.Button()
exitButton.Text = "Exit this form"
exitButton.Location.X = 140
' The preceding line is an ERROR because of no storage for Location.
```

Последняя инструкция из предыдущего примера завершается сбоем, так как создает только временное выделение для <xref:System.Drawing.Point> структуры, возвращаемой <xref:System.Windows.Forms.Control.Location%2A> свойством. Структура является типом значения, а временная структура не сохраняется после выполнения инструкции. Проблема решается путем объявления и использования переменной для <xref:System.Windows.Forms.Control.Location%2A>, которая создает более постоянное выделение <xref:System.Drawing.Point> для структуры. В следующем примере показан код, который может заменить последнюю инструкцию из предыдущего примера.

```vb
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)
exitButton.Location = exitLocation
```

**Идентификатор ошибки:** BC30068

## <a name="to-correct-this-error"></a>Исправление ошибки

- Если оператор присваивает значение выражению, замените выражение одной записываемой переменной, свойством или элементом массива.

- Если инструкция делает косвенный доступ через тип значения (обычно это структура), создайте переменную для хранения типа значения.

- Назначьте переменной соответствующую структуру (или другой тип значения).

- Используйте переменную для доступа к свойству, чтобы присвоить ему значение.

## <a name="see-also"></a>См. также

- [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
- [Рекомендации по устранению неполадок](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
