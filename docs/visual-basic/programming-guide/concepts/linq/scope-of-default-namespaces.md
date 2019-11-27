---
title: Области пространств имен по умолчанию
ms.date: 07/20/2015
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
ms.openlocfilehash: 8ba4d13b6d40180a88651f0503d1323f2b78f36c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343645"
---
# <a name="scope-of-default-namespaces-in-visual-basic"></a>Область пространств имен по умолчанию в Visual Basic
Применяемые по умолчанию пространства имен, представленные в XML-дереве, находятся вне области запросов. Если имеется XML, расположенный в используемом по умолчанию пространстве имен, для получения полного имени, которое может быть применено в запросе, то необходимо объявить переменную <xref:System.Xml.Linq.XNamespace> и использовать ее в сочетании с локальным именем.  
  
 Одной из наиболее типичных проблем при запросах к XML-деревьям является то, что, если XML-дерево содержит пространство имен по умолчанию, разработчик иногда пишет запрос так, как если бы XML-код не располагался в пространстве имен.  
  
 Первый набор примеров в данном разделе показывает типичный способ загрузки XML в пространстве имен по умолчанию и неправильного запроса к нему.  
  
 Второй набор примеров показывает необходимые исправления для запроса XML в пространстве имен.  
  
## <a name="example"></a>Пример  
 Этот пример показывает создание XML в пространстве имен, а также запрос, возвращающий пустой результирующий набор.  
  
### <a name="code"></a>Код  
  
```vb  
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
  
### <a name="comments"></a>Комментарии  
 Этот пример выдает следующий результат:  
  
```console  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>Пример  
 Этот пример показывает создание XML в пространстве имен, а также запрос, код которого написан правильно.  
  
 В отличие от приведенного выше примера, правильный подход при использовании Visual Basic заключается в объявлении и инициализации глобального пространства имен по умолчанию. При этом все свойства XML помещаются в пространство имен по умолчанию. Для последующей правильной работы примера не требуется больше никаких изменений.  
  
### <a name="code"></a>Код  
  
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
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>Комментарии  
 Этот пример выдает следующий результат:  
  
```console  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a>См. также

- [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
