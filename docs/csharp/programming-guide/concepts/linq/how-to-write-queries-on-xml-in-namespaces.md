---
title: "Практическое руководство. Создание запросов к XML в пространствах имен (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 075f0dab486d773cd7dd0616a6432f065b5a5eb5
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a>Практическое руководство. Создание запросов к XML в пространствах имен (C#)
Для записи XML-запросов в пространстве имен необходимо использовать объекты <xref:System.Xml.Linq.XName> с правильно заданным пространством имен.  
  
 Что касается языка C#, то наиболее распространенный подход состоит в инициализации <xref:System.Xml.Linq.XNamespace> с помощью строки, содержащей URI, и последующем использовании перегруженного оператора сложения для объединения пространства имен с локальным именем.  
  
 Первый набор примеров в данном разделе показывает порядок создания XML-дерева в пространстве имен по умолчанию. Второй набор показывает порядок создания XML-дерева в пространстве имен с префиксом.  
  
## <a name="example"></a>Пример  
 В следующем примере создается XML-дерево, находящееся в пространстве имен по умолчанию. Затем извлекается коллекция элементов.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
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
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a>Пример  
 В C# порядок составления запросов одинаков как при выполнении запросов к XML-дереву, использующему пространство имен с префиксом, так и при выполнении запросов к XML-дереву, находящемуся в пространстве имен по умолчанию.  
  
 В следующем примере создается XML-дерево, находящееся в пространстве имен с префиксом. Затем извлекается коллекция элементов.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 В этом примере выводятся следующие данные:  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a>См. также  
 [Работа с пространствами имен XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
