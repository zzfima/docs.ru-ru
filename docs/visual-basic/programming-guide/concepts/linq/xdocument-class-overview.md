---
title: Общие сведения о классах XDocument
ms.date: 07/20/2015
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
ms.openlocfilehash: cbc1ccca53978da07f31c0ba7e54eca9f06b0e72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349291"
---
# <a name="xdocument-class-overview-visual-basic"></a><span data-ttu-id="7aad6-102">XDocument Class Overview (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7aad6-102">XDocument Class Overview (Visual Basic)</span></span>
<span data-ttu-id="7aad6-103">В этом разделе представлен класс <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="7aad6-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="7aad6-104">Общие сведения о классе XDocument</span><span class="sxs-lookup"><span data-stu-id="7aad6-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="7aad6-105">Класс <xref:System.Xml.Linq.XDocument> содержит сведения, необходимые для допустимого XML-документа.</span><span class="sxs-lookup"><span data-stu-id="7aad6-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="7aad6-106">К ним относятся XML-декларация, инструкции по обработке и комментарии.</span><span class="sxs-lookup"><span data-stu-id="7aad6-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="7aad6-107">Отметим, что, если требуются только конкретные функции, обеспечиваемые классом <xref:System.Xml.Linq.XDocument>, необходимо создавать только объекты <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="7aad6-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="7aad6-108">Во многих случаях пользователь может работать непосредственно с <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="7aad6-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="7aad6-109">Непосредственная работа с <xref:System.Xml.Linq.XElement> реализует более простую модель программирования.</span><span class="sxs-lookup"><span data-stu-id="7aad6-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="7aad6-110">Интерфейс <xref:System.Xml.Linq.XDocument> является производным от интерфейса <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="7aad6-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="7aad6-111">Поэтому он может содержать дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="7aad6-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="7aad6-112">Однако объекты <xref:System.Xml.Linq.XDocument> могут иметь только по одному дочернему узлу <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="7aad6-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="7aad6-113">Это обстоятельство отражает стандарт XML, согласно которому в XML-документе может содержаться лишь один корневой элемент.</span><span class="sxs-lookup"><span data-stu-id="7aad6-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="7aad6-114">Компоненты XDocument</span><span class="sxs-lookup"><span data-stu-id="7aad6-114">Components of XDocument</span></span>  
 <span data-ttu-id="7aad6-115">Документ <xref:System.Xml.Linq.XDocument> может включать в себя следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="7aad6-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
- <span data-ttu-id="7aad6-116">Один объект <xref:System.Xml.Linq.XDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="7aad6-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="7aad6-117"><xref:System.Xml.Linq.XDeclaration> позволяет указать соответствующие части XML-объявления: версию XML, кодировку документа, а также то, является ли этот XML-документ изолированным.</span><span class="sxs-lookup"><span data-stu-id="7aad6-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
- <span data-ttu-id="7aad6-118">Один объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="7aad6-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="7aad6-119">Это корневой узел XML-документа.</span><span class="sxs-lookup"><span data-stu-id="7aad6-119">This is the root node of the XML document.</span></span>  
  
- <span data-ttu-id="7aad6-120">Любое количество объектов <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="7aad6-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="7aad6-121">Инструкция по обработке передает сведения в приложение, обрабатывающее XML-код.</span><span class="sxs-lookup"><span data-stu-id="7aad6-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
- <span data-ttu-id="7aad6-122">Любое количество объектов <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="7aad6-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="7aad6-123">Комментарии и корневой элемент находятся на одном уровне.</span><span class="sxs-lookup"><span data-stu-id="7aad6-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="7aad6-124">Объект <xref:System.Xml.Linq.XComment> не может быть первым аргументом в списке, так как XML-документ не может начинаться с комментария.</span><span class="sxs-lookup"><span data-stu-id="7aad6-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
- <span data-ttu-id="7aad6-125">Один тип документа <xref:System.Xml.Linq.XDocumentType> для DTD.</span><span class="sxs-lookup"><span data-stu-id="7aad6-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="7aad6-126">При сериализации документа <xref:System.Xml.Linq.XDocument>, даже если значением декларации `XDocument.Declaration` является `null`, выходные данные будут иметь XML-декларацию, если для свойства `Writer.Settings.OmitXmlDeclaration` автор указал значение `false` (применяется по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7aad6-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="7aad6-127">По умолчанию [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] указывает для версии значение «1.0», а для кодировки значение «utf-8».</span><span class="sxs-lookup"><span data-stu-id="7aad6-127">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="7aad6-128">Использование XElement без XDocument</span><span class="sxs-lookup"><span data-stu-id="7aad6-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="7aad6-129">Как уже отмечалось, класс <xref:System.Xml.Linq.XElement> является основным классом интерфейса программирования [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7aad6-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface.</span></span> <span data-ttu-id="7aad6-130">Во многих случаях приложение не требует создания документа.</span><span class="sxs-lookup"><span data-stu-id="7aad6-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="7aad6-131">Класс <xref:System.Xml.Linq.XElement> позволяет создавать XML-дерево, добавлять к нему другие XML-деревья, изменять XML-дерево и сохранять его.</span><span class="sxs-lookup"><span data-stu-id="7aad6-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="7aad6-132">Использование XDocument</span><span class="sxs-lookup"><span data-stu-id="7aad6-132">Using XDocument</span></span>  
 <span data-ttu-id="7aad6-133">При создании объектов <xref:System.Xml.Linq.XDocument> используется функциональное построение, так же как и при создании объектов <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="7aad6-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="7aad6-134">Следующий фрагмент кода создает объект <xref:System.Xml.Linq.XDocument> и ассоциированные с ним вложенные объекты.</span><span class="sxs-lookup"><span data-stu-id="7aad6-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
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
  
 <span data-ttu-id="7aad6-135">В результате анализа файла test.xml получается следующий выход:</span><span class="sxs-lookup"><span data-stu-id="7aad6-135">When you examine the file test.xml, you get the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7aad6-136">См. также</span><span class="sxs-lookup"><span data-stu-id="7aad6-136">See also</span></span>

- [<span data-ttu-id="7aad6-137">LINQ to XML Programming Overview (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7aad6-137">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
