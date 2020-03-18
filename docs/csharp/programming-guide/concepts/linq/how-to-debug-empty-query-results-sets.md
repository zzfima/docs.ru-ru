---
title: Практическое руководство. Отладка пустых результирующих наборов запроса (C#)
ms.date: 07/20/2015
ms.assetid: b569f0dc-425e-45a6-acbf-770fb761c981
ms.openlocfilehash: 2716f7c525ac6bee8d2fb374e4ecc4c975d852a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141289"
---
# <a name="how-to-debug-empty-query-results-sets-c"></a>Практическое руководство. Отладка пустых результирующих наборов запроса (C#)
Одной из наиболее типичных проблем при запросах к XML-деревьям является то, что, если XML-дерево содержит пространство имен по умолчанию, разработчик иногда пишет запрос так, как если бы XML-код не располагался в пространстве имен.  
  
 Первый набор примеров в данном разделе показывает типичный способ загрузки XML в пространстве имен по умолчанию и неправильного запроса к нему.  
  
 Второй набор примеров показывает необходимые исправления для запроса XML в пространстве имен.  
  
 Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).  
  
## <a name="example"></a>Пример  
 Этот пример показывает создание XML в пространстве имен, а также запрос, возвращающий пустой результирующий набор.  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 Этот пример выдает следующий результат:  
  
```output  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>Пример  
 Этот пример показывает создание XML в пространстве имен, а также запрос, код которого написан правильно.  
  
 Решение заключается в объявлении и инициализации объекта <xref:System.Xml.Linq.XNamespace> и его использовании при указании объектов <xref:System.Xml.Linq.XName>. В данном случае аргументом для метода <xref:System.Xml.Linq.XContainer.Elements%2A> является объект <xref:System.Xml.Linq.XName>.  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 Этот пример выдает следующий результат:  
  
```output  
Result set follows:  
1  
2  
3  
End of result set  
```  
