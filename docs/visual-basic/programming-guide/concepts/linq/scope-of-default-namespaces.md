---
title: "Область действия пространств имен по умолчанию в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c0152250cf7cfb4b6cadbcaab60eaad8ec2fb5ee
ms.lasthandoff: 03/13/2017


---
# <a name="scope-of-default-namespaces-in-visual-basic"></a>Область действия пространств имен по умолчанию в Visual Basic
Применяемые по умолчанию пространства имен, представленные в XML-дереве, находятся вне области запросов. Если имеется XML, который находится в пространстве имен по умолчанию, то необходимо объявить <xref:System.Xml.Linq.XNamespace>переменной и использовать ее в сочетании с локальным именем для получения полного имени для использования в запросе.</xref:System.Xml.Linq.XNamespace>  
  
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
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>Пример  
 Этот пример показывает создание XML в пространстве имен, а также запрос, код которого написан правильно.  
  
 В отличие от вышеприведенного примера неправильным кодом правильный подход с использованием Visual Basic заключается в объявлении и инициализации глобального пространства имен. При этом все свойства XML помещаются в пространство имен по умолчанию. Для последующей правильной работы примера не требуется больше никаких изменений.  
  
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
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a>См. также  
 [Работа с пространствами имен XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
