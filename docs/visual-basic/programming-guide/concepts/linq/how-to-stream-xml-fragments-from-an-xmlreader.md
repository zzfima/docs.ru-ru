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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c9c60bb4730ef6569390f76f63c40a2cbd1c9524
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a><span data-ttu-id="d99a2-102">Практическое руководство: потоковая передача фрагментов XML из XmlReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d99a2-102">How to: Stream XML Fragments from an XmlReader (Visual Basic)</span></span>
<span data-ttu-id="d99a2-103">При необходимости обработать большой XML-файл загрузка в память полного XML-дерева, возможно, будет неосуществима.</span><span class="sxs-lookup"><span data-stu-id="d99a2-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="d99a2-104">В этом разделе показано, как с помощью <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> фрагменты в потоке</span><span class="sxs-lookup"><span data-stu-id="d99a2-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="d99a2-105">Одним из наиболее эффективных способов использования <xref:System.Xml.XmlReader>для чтения <xref:System.Xml.Linq.XElement>объекты — написать собственный пользовательский метод оси.</xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="d99a2-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="d99a2-106">Метод оси обычно возвращает коллекцию например <xref:System.Collections.Generic.IEnumerable%601>из <xref:System.Xml.Linq.XElement>, как показано в примере в этом разделе.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="d99a2-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="d99a2-107">В пользовательском методе оси после создания фрагмента XML путем вызова <xref:System.Xml.Linq.XNode.ReadFrom%2A>метод, возвращают коллекции с помощью `yield return`.</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="d99a2-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="d99a2-108">Тем самым в пользовательском методе оси обеспечивается семантика отложенного выполнения.</span><span class="sxs-lookup"><span data-stu-id="d99a2-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="d99a2-109">При создании XML-дерева из <xref:System.Xml.XmlReader>объекта, <xref:System.Xml.XmlReader>должен находится на элементе.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="d99a2-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="d99a2-110"><xref:System.Xml.Linq.XNode.ReadFrom%2A>Метод не осуществляет возврат, пока считает закрывающий тег элемента.</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="d99a2-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="d99a2-111">Если вы хотите создать частичное дерево, можно создать экземпляр <xref:System.Xml.XmlReader>, поместите объект чтения на узле, который требуется преобразовать в <xref:System.Xml.Linq.XElement>дерева, а затем создайте <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="d99a2-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="d99a2-112">Раздел [как: поток XML-фрагментов с доступом к сведениям заголовка (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) содержит сведения и пример для потоковой передачи более сложного документа.</span><span class="sxs-lookup"><span data-stu-id="d99a2-112">The topic [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>  
  
 <span data-ttu-id="d99a2-113">Раздел [как: выполнять потоковые преобразования из больших XML-документов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) содержит пример использования LINQ to XML для преобразования крайне больших документов XML при сохранении небольшой объем памяти.</span><span class="sxs-lookup"><span data-stu-id="d99a2-113">The topic [How to: Perform Streaming Transform of Large XML Documents (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d99a2-114">Пример</span><span class="sxs-lookup"><span data-stu-id="d99a2-114">Example</span></span>  
 <span data-ttu-id="d99a2-115">В следующем примере создается пользовательский метод оси.</span><span class="sxs-lookup"><span data-stu-id="d99a2-115">This example creates a custom axis method.</span></span> <span data-ttu-id="d99a2-116">Его можно запросить с помощью запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="d99a2-116">You can query it by using a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query.</span></span> <span data-ttu-id="d99a2-117">Пользовательский метод оси `StreamRootChildDoc` специально разработан для чтения документа с повторяющимся элементом `Child`.</span><span class="sxs-lookup"><span data-stu-id="d99a2-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
<span data-ttu-id="d99a2-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="d99a2-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="d99a2-119">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="d99a2-119">This example produces the following output:</span></span>  
  
<span data-ttu-id="d99a2-120"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="d99a2-120"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="d99a2-121">В этом примере документ-источник весьма невелик.</span><span class="sxs-lookup"><span data-stu-id="d99a2-121">In this example, the source document is very small.</span></span> <span data-ttu-id="d99a2-122">Тем не менее, даже если бы он содержал миллионы элементов `Child`, для этого примера потребовался бы очень небольшой объем памяти.</span><span class="sxs-lookup"><span data-stu-id="d99a2-122">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d99a2-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d99a2-123">See Also</span></span>  
 <span data-ttu-id="d99a2-124">[Пошаговое руководство: Реализация IEnumerable(Of T) в Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md) </span><span class="sxs-lookup"><span data-stu-id="d99a2-124">[Walkthrough: Implementing IEnumerable(Of T) in Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md) </span></span>  
<span data-ttu-id="d99a2-125"> [Синтаксический анализ XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)</span><span class="sxs-lookup"><span data-stu-id="d99a2-125"> [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)</span></span>
