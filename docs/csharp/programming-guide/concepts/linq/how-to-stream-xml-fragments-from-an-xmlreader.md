---
title: "Практическое руководство. Потоковая передача фрагментов XML из XmlReader (C#) | Документы Майкрософт"
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
ms.assetid: 4a8f0e45-768a-42e2-bc5f-68bdf0e0a726
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
ms.openlocfilehash: 4bb11e120a123b701e45916b983032797c0ea8b6
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-c"></a>Практическое руководство. Потоковая передача фрагментов XML из XmlReader (C#)
При необходимости обработать большой XML-файл загрузка в память полного XML-дерева, возможно, будет неосуществима. В этом разделе показано, как обрабатывать фрагменты в потоке с помощью <xref:System.Xml.XmlReader>.  
  
 Одним из наиболее эффективных способов использования <xref:System.Xml.XmlReader> для чтения объектов <xref:System.Xml.Linq.XElement> является написание собственного пользовательского метода оси. Метод оси обычно возвращает коллекцию, например <xref:System.Collections.Generic.IEnumerable%601> из <xref:System.Xml.Linq.XElement>, как показано в примере в этом разделе. В пользовательском методе оси после создания XML-фрагмента с помощью вызова метода <xref:System.Xml.Linq.XNode.ReadFrom%2A> возвратите коллекцию, используя `yield return`. Тем самым в пользовательском методе оси обеспечивается семантика отложенного выполнения.  
  
 При создании XML-дерева из объекта <xref:System.Xml.XmlReader> <xref:System.Xml.XmlReader> должен находиться на элементе. Метод <xref:System.Xml.Linq.XNode.ReadFrom%2A> не выполняет возврат до тех пор, пока не считает закрывающий тег элемента.  
  
 Если вы хотите создать частичное дерево, можно создать экземпляр <xref:System.Xml.XmlReader>, поместить модуль чтения на узле, который требуется преобразовать в дерево <xref:System.Xml.Linq.XElement>, а затем создать объект <xref:System.Xml.Linq.XElement>.  
  
 В разделе [Практическое руководство. Потоковая передача фрагментов XML с доступом к сведениям заголовка (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) приводятся сведения и пример потоковой передачи более сложного документа.  
  
 Раздел [Практическое руководство. Выполнение потокового преобразования крупных XML-документов](../../../../csharp/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) содержит пример использования LINQ to XML для преобразования чрезвычайно больших XML-документов, используя небольшой объем памяти.  
  
## <a name="example"></a>Пример  
 В следующем примере создается пользовательский метод оси. Его можно запросить с помощью запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. Пользовательский метод оси `StreamRootChildDoc` специально разработан для чтения документа с повторяющимся элементом `Child`.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 В этом примере выводятся следующие данные:  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 В этом примере документ-источник весьма невелик. Тем не менее, даже если бы он содержал миллионы элементов `Child`, для этого примера потребовался бы очень небольшой объем памяти.  
  
## <a name="see-also"></a>См. также  
 [Анализ XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
