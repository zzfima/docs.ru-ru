---
title: Рефакторинг в чистые функции
ms.date: 07/20/2015
ms.assetid: 99e7d27b-a3ff-4577-bdb2-5a8278d6d7af
ms.openlocfilehash: 22b371c6136836d6e0f1281f824b69378c0d3e4a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346523"
---
# <a name="refactoring-into-pure-functions-visual-basic"></a>Refactoring Into Pure Functions (Visual Basic)

Важным аспектом чисто функциональных преобразований является освоение способов оптимизации существующего кода для получения чистых функций.

Как отмечалось ранее в этом разделе, чистые функции имеют две полезные характеристики.

- У них отсутствуют побочные эффекты. Функции не изменяют значения или данные любого типа, не входящие в область их определения.

- Функции действуют единообразно. После получения того же набора входных данных они всегда возвращают одно и то же выходное значение.

 Одним из способов перехода к функциональному программированию является оптимизация существующего кода с целью устранения ненужных побочных эффектов и внешних зависимостей. Таким образом, из существующего кода создаются чистые функции.

В этом разделе объясняется, что представляет собой чистая функция и чем она не является. The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.

## <a name="eliminating-side-effects-and-external-dependencies"></a>Устранение побочных эффектов и внешних зависимостей

В следующих примерах сравниваются обычные и чистые функции.

### <a name="non-pure-function-that-changes-a-class-member"></a>Обычная функция, изменяющая член класса

В следующем примере кода функция `HyphenatedConcat` представляет собой обычную функцию, поскольку изменяет элемент данных `aMember` в классе.

```vb
Module Module1
    Dim aMember As String = "StringOne"

    Public Sub HyphenatedConcat(ByVal appendStr As String)
        aMember = aMember & "-" & appendStr
    End Sub

    Sub Main()
        HyphenatedConcat("StringTwo")
        Console.WriteLine(aMember)
    End Sub
End Module
```

Этот код выводит следующие результаты:

```console
StringOne-StringTwo
```

Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a  `shared` member or an instance member. Чистая функция не изменяет не относящиеся к ней данные.

### <a name="non-pure-function-that-changes-an-argument"></a>Обычная функция, изменяющая аргумент

Более того, следующая версия той же функции представляет собой обычную функцию, поскольку изменяет содержимое своего параметра `sb`.

```vb
Module Module1
    Public Sub HyphenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)
        sb.Append("-" & appendStr)
    End Sub

    Sub Main()
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")
        HyphenatedConcat(sb1, "StringTwo")
        Console.WriteLine(sb1)
    End Sub
End Module
```

Эта версия программы дает те же выходные данные, что и первая версия, поскольку функция `HyphenatedConcat` изменила значение (состояние) своего первого параметра, вызвав функцию-член <xref:System.Text.StringBuilder.Append%2A>. Обратите внимание, что это изменение происходит несмотря на то, что функция `HyphenatedConcat` использует передачу параметра по значению.

> [!IMPORTANT]
> Передача параметров по значению для ссылочных типов приводит к созданию копии ссылки на передаваемый объект. Эта копия все еще связана с теми же данными экземпляра, что и первоначальная ссылка (пока ссылочная переменная не будет присвоена новому объекту). Вызов по значению необязательно требуется функции для изменения параметра.

### <a name="pure-function"></a>Чистая функция

Следующая версия этой программы реализует функцию `HyphenatedConcat` в виде чистой функции.

```vb
Module Module1
    Public Function HyphenatedConcat(ByVal s As String, ByVal appendStr As String) As String
        Return (s & "-" & appendStr)
    End Function

    Sub Main()
        Dim s1 As String = "StringOne"
        Dim s2 As String = HyphenatedConcat(s1, "StringTwo")
        Console.WriteLine(s2)
    End Sub
End Module
```

И снова она дает ту же строку вывода: `StringOne-StringTwo`. Обратите внимание, что для сохранения соединенного значения оно сохраняется в промежуточной переменной `s2`.

Одним из полезных подходов является написание функций, которые локально являются обычными (то есть в них объявляются и изменяются локальные переменные), но глобально остаются чистыми. Такие функции имеют многие характеристики, благоприятные с точки зрения компоновки, но позволяют обойтись без использования некоторых более сложных средств функционального программирования, тех, что диктуют, например, необходимость использовать рекурсию, невзирая на возможность добиться того же результата с помощью простого цикла.

## <a name="standard-query-operators"></a>Стандартные операторы запроса

Важной характеристикой стандартных операторов запросов является то, что они реализуются как чистые функции.

For more information, see [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).

## <a name="see-also"></a>См. также

- [Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [Functional Programming vs. Imperative Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)
