---
title: "Общие сведения о классах XDocument (Visual Basic) | Документы Microsoft"
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
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3f51808a64d51fb354159df1a7323ad2fc26eedc
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="xdocument-class-overview-visual-basic"></a><span data-ttu-id="98813-102">Общие сведения о классах XDocument (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98813-102">XDocument Class Overview (Visual Basic)</span></span>
<span data-ttu-id="98813-103">В этом разделе описываются <xref:System.Xml.Linq.XDocument>класса.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="98813-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="98813-104">Общие сведения о классе XDocument</span><span class="sxs-lookup"><span data-stu-id="98813-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="98813-105"><xref:System.Xml.Linq.XDocument>Класс содержит сведения, необходимые для допустимого XML-документа.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="98813-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="98813-106">К ним относятся XML-декларация, инструкции по обработке и комментарии.</span><span class="sxs-lookup"><span data-stu-id="98813-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="98813-107">Обратите внимание, что только для создания <xref:System.Xml.Linq.XDocument>объектов, если требуются определенные функциональные возможности, предоставляемые <xref:System.Xml.Linq.XDocument>класса.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="98813-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="98813-108">Во многих случаях может работать непосредственно с <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="98813-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="98813-109">Работа непосредственно с <xref:System.Xml.Linq.XElement>реализует простую модель программирования.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="98813-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="98813-110"><xref:System.Xml.Linq.XDocument>является производным от <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="98813-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="98813-111">Поэтому он может содержать дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="98813-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="98813-112">Тем не менее <xref:System.Xml.Linq.XDocument>объекты могут иметь только один дочерний <xref:System.Xml.Linq.XElement>узла.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="98813-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="98813-113">Это обстоятельство отражает стандарт XML, согласно которому в XML-документе может содержаться лишь один корневой элемент.</span><span class="sxs-lookup"><span data-stu-id="98813-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="98813-114">Компоненты XDocument</span><span class="sxs-lookup"><span data-stu-id="98813-114">Components of XDocument</span></span>  
 <span data-ttu-id="98813-115"><xref:System.Xml.Linq.XDocument>Может содержать следующие элементы:</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="98813-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
-   <span data-ttu-id="98813-116">Один <xref:System.Xml.Linq.XDeclaration>объекта.</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="98813-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="98813-117"><xref:System.Xml.Linq.XDeclaration>позволяет указать соответствующие части XML-декларации: версию XML, кодировку документа, а ли XML-документ изолированным.</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="98813-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
-   <span data-ttu-id="98813-118">Один <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="98813-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="98813-119">Это корневой узел XML-документа.</span><span class="sxs-lookup"><span data-stu-id="98813-119">This is the root node of the XML document.</span></span>  
  
-   <span data-ttu-id="98813-120">Любое количество <xref:System.Xml.Linq.XProcessingInstruction>объектов.</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="98813-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="98813-121">Инструкция по обработке передает сведения в приложение, обрабатывающее XML-код.</span><span class="sxs-lookup"><span data-stu-id="98813-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
-   <span data-ttu-id="98813-122">Любое количество <xref:System.Xml.Linq.XComment>объектов.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="98813-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="98813-123">Комментарии и корневой элемент находятся на одном уровне.</span><span class="sxs-lookup"><span data-stu-id="98813-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="98813-124"><xref:System.Xml.Linq.XComment>Объект не может быть первый аргумент в списке, так как оно является недопустимым для документа XML, начинаться с комментария.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="98813-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
-   <span data-ttu-id="98813-125">Один <xref:System.Xml.Linq.XDocumentType>для DTD.</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="98813-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="98813-126">При сериализации <xref:System.Xml.Linq.XDocument>, даже если `XDocument.Declaration` — `null`, выходные данные будут иметь XML-декларацию, если модуль записи имеет `Writer.Settings.OmitXmlDeclaration` значение `false` (по умолчанию).</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="98813-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="98813-127">По умолчанию [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] указывает для версии значение «1.0», а для кодировки значение «utf-8».</span><span class="sxs-lookup"><span data-stu-id="98813-127">By default, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="98813-128">Использование XElement без XDocument</span><span class="sxs-lookup"><span data-stu-id="98813-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="98813-129">Как упоминалось ранее, <xref:System.Xml.Linq.XElement>– это основной класс в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] интерфейс программирования.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="98813-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] programming interface.</span></span> <span data-ttu-id="98813-130">Во многих случаях приложение не требует создания документа.</span><span class="sxs-lookup"><span data-stu-id="98813-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="98813-131">С помощью <xref:System.Xml.Linq.XElement>класс, создание XML-дерева, добавьте к нему другие XML-деревья, изменять XML-дерево и сохранить его</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="98813-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="98813-132">Использование XDocument</span><span class="sxs-lookup"><span data-stu-id="98813-132">Using XDocument</span></span>  
 <span data-ttu-id="98813-133">Для создания <xref:System.Xml.Linq.XDocument>, используется функциональное построение, так же, как и для создания <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="98813-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="98813-134">Следующий код создает <xref:System.Xml.Linq.XDocument>и связанный с ним вложенные объекты.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="98813-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```vb  
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>  
                       <!--This is a comment.-->  
                       <?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
                       <Pubs>  
                           <Book>  
                               <Title>Artifacts of Roman Civilization</Title>  
                               <Author>Moreno, Jordao</Author>  
                           </Book>  
                           <Book>  
                               <Title>Midieval Tools and Implements</Title>  
                               <Author>Gazit, Inbar</Author>  
                           </Book>  
                       </Pubs>  
                       <!--This is another comment.-->  
doc.Save("test.xml")  
```  
  
 <span data-ttu-id="98813-135">В результате анализа файла test.xml получается следующий выход:</span><span class="sxs-lookup"><span data-stu-id="98813-135">When you examine the file test.xml, you get the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a><span data-ttu-id="98813-136">См. также</span><span class="sxs-lookup"><span data-stu-id="98813-136">See Also</span></span>  
 [<span data-ttu-id="98813-137">LINQ to XML обзор программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98813-137">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
