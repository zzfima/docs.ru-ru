---
title: Практическое руководство. Создание запросов к XML в пространствах имен
ms.date: 07/20/2015
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
ms.openlocfilehash: 496cf8daf5136e8aafff000312bbd730a5152e9f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344463"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a>Как создавать запросы к XML в пространствах имен (Visual Basic)
Для записи XML-запросов в пространстве имен необходимо использовать объекты <xref:System.Xml.Linq.XName> с правильно заданным пространством имен.  
  
 В Visual Basic наиболее распространенным подходом является определение глобального пространства имен и последующее применение XML-литералов и XML-свойств, в которых указано это пространство имен. Можно определить глобальное пространство имен по умолчанию, и в этом случае элементы XML-литералов будут представлены в этом пространстве имен по умолчанию. Иначе можно определить глобальное пространство имен с помощью префикса, а затем использовать этот префикс в XML-литералах и XML-свойствах в соответствии с необходимостью. Как и в других формах XML, по умолчанию атрибуты всегда находятся вне пространства имен.  
  
 Первый набор примеров в данном разделе показывает порядок создания XML-дерева в пространстве имен по умолчанию. Второй набор показывает порядок создания XML-дерева в пространстве имен с префиксом.  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-дерево, находящееся в пространстве имен по умолчанию. Затем извлекается коллекция элементов.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
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
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
    End Sub  
End Module  
```  
  
 В этом примере выводятся следующие данные:  
  
```console  
1  
2  
3  
```  
  
## <a name="example"></a>Пример  
 Однако в Visual Basic при составлении запросов к XML-дереву, в котором используется пространство имен с префиксом, используется совершенно другой подход, чем при составлении запросов к XML-дереву, находящемуся в пространстве имен по умолчанию. Как правило, пространство имен с префиксом импортируется с помощью инструкции `Imports`. Затем префикс используется в именах элементов и атрибутов для построения XML-дерева. Префикс также используется при выполнении запросов к XML-дереву с помощью XML-свойств.  
  
 В следующем примере создается XML-дерево, находящееся в пространстве имен с префиксом. Затем извлекается коллекция элементов.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>1</aw:Child>  
                <aw:Child>2</aw:Child>  
                <aw:Child>3</aw:Child>  
                <aw:AnotherChild>4</aw:AnotherChild>  
                <aw:AnotherChild>5</aw:AnotherChild>  
                <aw:AnotherChild>6</aw:AnotherChild>  
            </aw:Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<aw:Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
    End Sub  
End Module  
```  
  
 В этом примере выводятся следующие данные:  
  
```console  
1  
2  
3  
```  
  
## <a name="see-also"></a>См. также

- [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
