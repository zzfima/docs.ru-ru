---
title: "Общие сведения о классе XDocument (C#)"
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
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2e8513c8c969f7522866454838c6c08da528c1b6
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="xdocument-class-overview-c"></a><span data-ttu-id="11815-102">Общие сведения о классе XDocument (C#)</span><span class="sxs-lookup"><span data-stu-id="11815-102">XDocument Class Overview (C#)</span></span>
<span data-ttu-id="11815-103">В этом разделе представлен класс <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="11815-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="11815-104">Общие сведения о классе XDocument</span><span class="sxs-lookup"><span data-stu-id="11815-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="11815-105">Класс <xref:System.Xml.Linq.XDocument> содержит сведения, необходимые для допустимого XML-документа.</span><span class="sxs-lookup"><span data-stu-id="11815-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="11815-106">К ним относятся XML-декларация, инструкции по обработке и комментарии.</span><span class="sxs-lookup"><span data-stu-id="11815-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="11815-107">Отметим, что, если требуются только конкретные функции, обеспечиваемые классом <xref:System.Xml.Linq.XDocument>, необходимо создавать только объекты <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="11815-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="11815-108">Во многих случаях пользователь может работать непосредственно с <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="11815-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="11815-109">Непосредственная работа с <xref:System.Xml.Linq.XElement> реализует более простую модель программирования.</span><span class="sxs-lookup"><span data-stu-id="11815-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="11815-110">Интерфейс <xref:System.Xml.Linq.XDocument> является производным от интерфейса <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="11815-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="11815-111">Поэтому он может содержать дочерние узлы.</span><span class="sxs-lookup"><span data-stu-id="11815-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="11815-112">Однако объекты <xref:System.Xml.Linq.XDocument> могут иметь только по одному дочернему узлу <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="11815-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="11815-113">Это обстоятельство отражает стандарт XML, согласно которому в XML-документе может содержаться лишь один корневой элемент.</span><span class="sxs-lookup"><span data-stu-id="11815-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="11815-114">Компоненты XDocument</span><span class="sxs-lookup"><span data-stu-id="11815-114">Components of XDocument</span></span>  
 <span data-ttu-id="11815-115">Документ <xref:System.Xml.Linq.XDocument> может включать в себя следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="11815-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
-   <span data-ttu-id="11815-116">Один объект <xref:System.Xml.Linq.XDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="11815-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="11815-117"><xref:System.Xml.Linq.XDeclaration> позволяет указать соответствующие части XML-объявления: версию XML, кодировку документа, а также то, является ли этот XML-документ изолированным.</span><span class="sxs-lookup"><span data-stu-id="11815-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
-   <span data-ttu-id="11815-118">Один объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="11815-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="11815-119">Это корневой узел XML-документа.</span><span class="sxs-lookup"><span data-stu-id="11815-119">This is the root node of the XML document.</span></span>  
  
-   <span data-ttu-id="11815-120">Любое количество объектов <xref:System.Xml.Linq.XProcessingInstruction>.</span><span class="sxs-lookup"><span data-stu-id="11815-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="11815-121">Инструкция по обработке передает сведения в приложение, обрабатывающее XML-код.</span><span class="sxs-lookup"><span data-stu-id="11815-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
-   <span data-ttu-id="11815-122">Любое количество объектов <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="11815-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="11815-123">Комментарии и корневой элемент находятся на одном уровне.</span><span class="sxs-lookup"><span data-stu-id="11815-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="11815-124">Объект <xref:System.Xml.Linq.XComment> не может быть первым аргументом в списке, так как XML-документ не может начинаться с комментария.</span><span class="sxs-lookup"><span data-stu-id="11815-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
-   <span data-ttu-id="11815-125">Один тип документа <xref:System.Xml.Linq.XDocumentType> для DTD.</span><span class="sxs-lookup"><span data-stu-id="11815-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="11815-126">При сериализации документа <xref:System.Xml.Linq.XDocument>, даже если значением декларации `XDocument.Declaration` является `null`, выходные данные будут иметь XML-декларацию, если для свойства `Writer.Settings.OmitXmlDeclaration` автор указал значение `false` (применяется по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="11815-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="11815-127">По умолчанию [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] указывает для версии значение «1.0», а для кодировки значение «utf-8».</span><span class="sxs-lookup"><span data-stu-id="11815-127">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="11815-128">Использование XElement без XDocument</span><span class="sxs-lookup"><span data-stu-id="11815-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="11815-129">Как уже отмечалось, класс <xref:System.Xml.Linq.XElement> является основным классом интерфейса программирования [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11815-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface.</span></span> <span data-ttu-id="11815-130">Во многих случаях приложение не требует создания документа.</span><span class="sxs-lookup"><span data-stu-id="11815-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="11815-131">Класс <xref:System.Xml.Linq.XElement> позволяет создавать XML-дерево, добавлять к нему другие XML-деревья, изменять XML-дерево и сохранять его.</span><span class="sxs-lookup"><span data-stu-id="11815-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="11815-132">Использование XDocument</span><span class="sxs-lookup"><span data-stu-id="11815-132">Using XDocument</span></span>  
 <span data-ttu-id="11815-133">При создании объектов <xref:System.Xml.Linq.XDocument> используется функциональное построение, так же как и при создании объектов <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="11815-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="11815-134">Следующий фрагмент кода создает объект <xref:System.Xml.Linq.XDocument> и ассоциированные с ним вложенные объекты.</span><span class="sxs-lookup"><span data-stu-id="11815-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```csharp  
XDocument d = new XDocument(  
    new XComment("This is a comment."),  
    new XProcessingInstruction("xml-stylesheet",  
        "href='mystyle.css' title='Compact' type='text/css'"),  
    new XElement("Pubs",  
        new XElement("Book",  
            new XElement("Title", "Artifacts of Roman Civilization"),  
            new XElement("Author", "Moreno, Jordao")  
        ),  
        new XElement("Book",  
            new XElement("Title", "Midieval Tools and Implements"),  
            new XElement("Author", "Gazit, Inbar")  
        )  
    ),  
    new XComment("This is another comment.")  
);  
d.Declaration = new XDeclaration("1.0", "utf-8", "true");  
Console.WriteLine(d);  
  
d.Save("test.xml");  
```  
  
 <span data-ttu-id="11815-135">В результате анализа файла test.xml получается следующий выход:</span><span class="sxs-lookup"><span data-stu-id="11815-135">When you examine the file test.xml, you get the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="11815-136">См. также</span><span class="sxs-lookup"><span data-stu-id="11815-136">See Also</span></span>  
 [<span data-ttu-id="11815-137">Общие сведения о программировании LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="11815-137">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)

