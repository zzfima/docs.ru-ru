---
title: "Практическое руководство: потоковая передача фрагментов XML из XmlReader (Visual Basic) | Документы Microsoft"
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
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c9c60bb4730ef6569390f76f63c40a2cbd1c9524
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a>Практическое руководство: потоковая передача фрагментов XML из XmlReader (Visual Basic)
При необходимости обработать большой XML-файл загрузка в память полного XML-дерева, возможно, будет неосуществима. В этом разделе показано, как с помощью <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> фрагменты в потоке  
  
 Одним из наиболее эффективных способов использования <xref:System.Xml.XmlReader>для чтения <xref:System.Xml.Linq.XElement>объекты — написать собственный пользовательский метод оси.</xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader> Метод оси обычно возвращает коллекцию например <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>, как показано в примере в этом разделе.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> В пользовательском методе оси после создания фрагмента XML путем вызова <xref:System.Xml.Linq.XNode.ReadFrom%2A>метод, возвращают коллекции с помощью `yield return`.</xref:System.Xml.Linq.XNode.ReadFrom%2A> Тем самым в пользовательском методе оси обеспечивается семантика отложенного выполнения.  
  
 При создании XML-дерева из <xref:System.Xml.XmlReader>объекта, <xref:System.Xml.XmlReader>должен находится на элементе.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> <xref:System.Xml.Linq.XNode.ReadFrom%2A>Метод не осуществляет возврат, пока считает закрывающий тег элемента.</xref:System.Xml.Linq.XNode.ReadFrom%2A>  
  
 Если вы хотите создать частичное дерево, можно создать экземпляр <xref:System.Xml.XmlReader>, поместите объект чтения на узле, который требуется преобразовать в <xref:System.Xml.Linq.XElement>дерева, а затем создайте <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader>  
  
 Раздел [как: поток XML-фрагментов с доступом к сведениям заголовка (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) содержит сведения и пример для потоковой передачи более сложного документа.  
  
 Раздел [как: выполнять потоковые преобразования из больших XML-документов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) содержит пример использования LINQ to XML для преобразования крайне больших документов XML при сохранении небольшой объем памяти.  
  
## <a name="example"></a>Пример  
 В следующем примере создается пользовательский метод оси. Его можно запросить с помощью запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. Пользовательский метод оси `StreamRootChildDoc` специально разработан для чтения документа с повторяющимся элементом `Child`.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 В этом примере выводятся следующие данные:  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 В этом примере документ-источник весьма невелик. Тем не менее, даже если бы он содержал миллионы элементов `Child`, для этого примера потребовался бы очень небольшой объем памяти.  
  
## <a name="see-also"></a>См. также  
 [Пошаговое руководство: Реализация IEnumerable(Of T) в Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md)   
 [Синтаксический анализ XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
