---
title: Практическое руководство. Отладка пустых наборов результатов запроса (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b242c90a-d2b8-4309-8a1e-e4e70736c727
ms.openlocfilehash: 076e7109dc89294ba0c1706bf9a66120e6a0b85d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630978"
---
# <a name="how-to-debug-empty-query-results-sets-visual-basic"></a>Практическое руководство. Отладка пустых наборов результатов запроса (Visual Basic)

Одной из наиболее типичных проблем при запросах к XML-деревьям является то, что, если XML-дерево содержит пространство имен по умолчанию, разработчик иногда пишет запрос так, как если бы XML-код не располагался в пространстве имен.

Первый набор примеров в данном разделе показывает типичный способ загрузки XML в пространстве имен по умолчанию и неправильного запроса к нему.

Второй набор примеров показывает необходимые исправления для запроса XML в пространстве имен.

Дополнительные сведения см. в разделе [Работа с пространствами имен XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).

## <a name="example"></a>Пример

Этот пример показывает создание XML в пространстве имен, а также запрос, возвращающий пустой результирующий набор.

```vb
Dim root As XElement = _
    <Root xmlns='http://www.adventure-works.com'>
        <Child>1</Child>
        <Child>2</Child>
        <Child>3</Child>
        <AnotherChild>4</AnotherChild>
        <AnotherChild>5</AnotherChild>
        <AnotherChild>6</AnotherChild>
    </Root>
Dim c1 As IEnumerable(Of XElement) = _
        From el In root.<Child> _
        Select el
Console.WriteLine("Result set follows:")
For Each el As XElement In c1
    Console.WriteLine(el.Value)
Next
Console.WriteLine("End of result set")
```

Этот пример выдает следующий результат:

```
Result set follows:
End of result set
```

## <a name="example"></a>Пример

Этот пример показывает создание XML в пространстве имен, а также запрос, код которого написан правильно.

Решением является объявление и инициализация глобального пространства имен по умолчанию. При этом все свойства XML помещаются в пространство имен по умолчанию. Для последующей правильной работы примера не требуется больше никаких изменений.

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <Root xmlns='http://www.adventure-works.com'>
                <Child>1</Child>
                <Child>2</Child>
                <Child>3</Child>
                <AnotherChild>4</AnotherChild>
                <AnotherChild>5</AnotherChild>
                <AnotherChild>6</AnotherChild>
            </Root>
        Dim c1 As IEnumerable(Of XElement) = _
                From el In root.<Child> _
                Select el
        Console.WriteLine("Result set follows:")
        For Each el As XElement In c1
            Console.WriteLine(CInt(el))
        Next
        Console.WriteLine("End of result set")
    End Sub
End Module
```

Этот пример выдает следующий результат:

```
Result set follows:
1
2
3
End of result set
```

## <a name="see-also"></a>См. также

- [Основные запросы (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
