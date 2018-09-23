---
title: Обработка XML в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
ms.openlocfilehash: 7fd111f5e885de3389b8f93002db22b48c4edd45
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562233"
---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="f8322-102">Обработка XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8322-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="f8322-103">Можно использовать *XML-литералов* загрузить XML из внешнего источника, например строки, файл или поток.</span><span class="sxs-lookup"><span data-stu-id="f8322-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="f8322-104">Затем можно использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] обработки XML и использовать [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] чтобы запросить XML.</span><span class="sxs-lookup"><span data-stu-id="f8322-104">You can then use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8322-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f8322-105">In This Section</span></span>  
 [<span data-ttu-id="f8322-106">Практическое руководство. Загрузка XML-кода из файла, строки или потока</span><span class="sxs-lookup"><span data-stu-id="f8322-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="f8322-107">Демонстрируется загрузка XML-данных в <xref:System.Xml.Linq.XDocument> или <xref:System.Xml.Linq.XElement> объект из текстового файла, строки или потока.</span><span class="sxs-lookup"><span data-stu-id="f8322-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="f8322-108">Практическое руководство. Преобразование XML с помощью LINQ</span><span class="sxs-lookup"><span data-stu-id="f8322-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="f8322-109">Показано, как преобразовать содержимое <xref:System.Xml.Linq.XDocument> объекта в новый XML-документа.</span><span class="sxs-lookup"><span data-stu-id="f8322-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="f8322-110">Практическое руководство. Изменение XML-литералов</span><span class="sxs-lookup"><span data-stu-id="f8322-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="f8322-111">Описание способа изменения элементов, атрибутов и значений в XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="f8322-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f8322-112">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f8322-112">Related Sections</span></span>  
 [<span data-ttu-id="f8322-113">Свойства оси XML</span><span class="sxs-lookup"><span data-stu-id="f8322-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="f8322-114">Ссылки на разделы, описывающие различные свойства XML доступа.</span><span class="sxs-lookup"><span data-stu-id="f8322-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="f8322-115">Общие сведения о LINQ to XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8322-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="f8322-116">Введение в использование [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f8322-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="f8322-117">Создание XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8322-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="f8322-118">Знакомство с помощью XML-литералов в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f8322-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="f8322-119">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f8322-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="f8322-120">Показано, как получить доступ к частям XML-элемента или документа в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f8322-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="f8322-121">XML</span><span class="sxs-lookup"><span data-stu-id="f8322-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="f8322-122">Содержит ссылки на разделы, описывающие, как использовать [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f8322-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8322-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f8322-123">See Also</span></span>  
 [<span data-ttu-id="f8322-124">XML</span><span class="sxs-lookup"><span data-stu-id="f8322-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="f8322-125">LINQ</span><span class="sxs-lookup"><span data-stu-id="f8322-125">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="f8322-126">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8322-126">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
