---
title: "Обработка XML в Visual Basic | Документы Microsoft"
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
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 62b955d78eb507aab4c786e84f3044ba54a38ebc
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="3c3d7-102">Обработка XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c3d7-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="3c3d7-103">Можно использовать *XML-литералы* для загрузки XML из внешнего источника, таких как строка, файл или поток.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="3c3d7-104">Затем можно использовать [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] управления XML и использовать [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] для составления запросов XML.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-104">You can then use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c3d7-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="3c3d7-105">In This Section</span></span>  
 [<span data-ttu-id="3c3d7-106">Практическое руководство. Загрузка XML-кода из файла, строки или потока</span><span class="sxs-lookup"><span data-stu-id="3c3d7-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="3c3d7-107">Показан способ загрузки XML в <xref:System.Xml.Linq.XDocument>или <xref:System.Xml.Linq.XElement>объекта из текстового файла, строки или потока.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="3c3d7-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="3c3d7-108">Практическое руководство. Преобразование XML с помощью LINQ</span><span class="sxs-lookup"><span data-stu-id="3c3d7-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="3c3d7-109">Показано, как преобразовать содержимое <xref:System.Xml.Linq.XDocument>объект в новый XML-документ.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="3c3d7-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="3c3d7-110">Практическое руководство. Изменение XML-литералов</span><span class="sxs-lookup"><span data-stu-id="3c3d7-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="3c3d7-111">Показано, как изменять элементы, атрибуты и значения в XML-литерале.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3c3d7-112">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3c3d7-112">Related Sections</span></span>  
 [<span data-ttu-id="3c3d7-113">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="3c3d7-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="3c3d7-114">Содержит ссылки на разделы, описывающие различные свойства XML доступа.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="3c3d7-115">Общие сведения о LINQ to XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c3d7-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="3c3d7-116">Введение в использование [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="3c3d7-117">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c3d7-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="3c3d7-118">Введение в использование литералов XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="3c3d7-119">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c3d7-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="3c3d7-120">Показано, как получить доступ к частям элемента или документа XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="3c3d7-121">XML</span><span class="sxs-lookup"><span data-stu-id="3c3d7-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="3c3d7-122">Содержит ссылки на разделы, описывающие, как использовать [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3c3d7-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c3d7-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3c3d7-123">See Also</span></span>  
 <span data-ttu-id="3c3d7-124">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="3c3d7-124">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="3c3d7-125"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="3c3d7-125"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="3c3d7-126"> [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="3c3d7-126"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
