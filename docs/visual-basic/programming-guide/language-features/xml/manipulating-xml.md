---
title: Обработка XML в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
ms.openlocfilehash: 4be24afe17e60c6c849530f1b892651a1f78399c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650417"
---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="14188-102">Обработка XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14188-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="14188-103">Можно использовать *XML-литералы* для загрузки XML из внешнего источника, таких как строка, файл или поток.</span><span class="sxs-lookup"><span data-stu-id="14188-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="14188-104">Затем можно использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] для управления XML и использования [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] для составления запросов XML.</span><span class="sxs-lookup"><span data-stu-id="14188-104">You can then use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14188-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="14188-105">In This Section</span></span>  
 [<span data-ttu-id="14188-106">Практическое руководство. Загрузка XML-кода из файла, строки или потока</span><span class="sxs-lookup"><span data-stu-id="14188-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="14188-107">Показан способ загрузки XML-документ в <xref:System.Xml.Linq.XDocument> или <xref:System.Xml.Linq.XElement> объект из текстового файла, строки или потока.</span><span class="sxs-lookup"><span data-stu-id="14188-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="14188-108">Практическое руководство. Преобразование XML с помощью LINQ</span><span class="sxs-lookup"><span data-stu-id="14188-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="14188-109">Показано, как преобразовать содержимое <xref:System.Xml.Linq.XDocument> объекта в новый XML-документ.</span><span class="sxs-lookup"><span data-stu-id="14188-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="14188-110">Практическое руководство. Изменение XML-литералов</span><span class="sxs-lookup"><span data-stu-id="14188-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="14188-111">Показано, как изменять элементы, атрибуты и значения в XML-литерал.</span><span class="sxs-lookup"><span data-stu-id="14188-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="14188-112">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="14188-112">Related Sections</span></span>  
 [<span data-ttu-id="14188-113">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="14188-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="14188-114">Ссылки на разделы, описывающие различные свойства XML доступа.</span><span class="sxs-lookup"><span data-stu-id="14188-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="14188-115">Общие сведения о LINQ to XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14188-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="14188-116">Предоставляет сведения об использовании [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="14188-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="14188-117">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14188-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="14188-118">Предоставляет сведения об использовании XML-литералов в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="14188-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="14188-119">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14188-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="14188-120">Показано, как получить доступ к частям элемента или документа XML в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="14188-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="14188-121">XML</span><span class="sxs-lookup"><span data-stu-id="14188-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="14188-122">Содержит ссылки на разделы, описывающие, как использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="14188-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14188-123">См. также</span><span class="sxs-lookup"><span data-stu-id="14188-123">See Also</span></span>  
 [<span data-ttu-id="14188-124">XML</span><span class="sxs-lookup"><span data-stu-id="14188-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="14188-125">LINQ</span><span class="sxs-lookup"><span data-stu-id="14188-125">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="14188-126">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14188-126">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
