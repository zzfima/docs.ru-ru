---
title: "LINQ to XML Обзор (Visual Basic) | Документы Microsoft"
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
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
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
ms.openlocfilehash: 4732aaa64119ba98ab11205e8c93dd8d3eb62d4b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-overview-visual-basic"></a><span data-ttu-id="b2def-102">LINQ to XML Обзор (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2def-102">LINQ to XML Overview (Visual Basic)</span></span>
<span data-ttu-id="b2def-103">XML широко используется для форматирования данных в целом ряде контекстов.</span><span class="sxs-lookup"><span data-stu-id="b2def-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="b2def-104">Примеры XML можно обнаружить в веб-среде, в файлах конфигурации, в файлах Microsoft Office Word и в базах данных.</span><span class="sxs-lookup"><span data-stu-id="b2def-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 <span data-ttu-id="b2def-105">В [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] реализован современный пересмотренный подход к программированию средствами XML.</span><span class="sxs-lookup"><span data-stu-id="b2def-105">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="b2def-106">Кроме того, реализованы встроенные в память возможности модификации документов модели DOM, поддерживаются выражения запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2def-106">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query expressions.</span></span> <span data-ttu-id="b2def-107">Хотя в синтаксическом отношении эти выражения запросов отличаются от XPath, они предоставляют аналогичные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="b2def-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="b2def-108">Разработчики, использующие LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="b2def-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b2def-109"> предназначен для различных категорий разработчиков.</span><span class="sxs-lookup"><span data-stu-id="b2def-109"> targets a variety of developers.</span></span> <span data-ttu-id="b2def-110">С точки зрения среднестатистического разработчика, заинтересованного в решении той или иной задачи, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] облегчает обработку XML, поскольку дает возможность получить опыт работы с запросами, аналогичный опыту работы с языком SQL.</span><span class="sxs-lookup"><span data-stu-id="b2def-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="b2def-111">Посвятив совсем немного времени изучению предмета, программисты могут научиться составлять сжатые и мощные запросы на предпочитаемом ими языке программирования.</span><span class="sxs-lookup"><span data-stu-id="b2def-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="b2def-112">Профессиональные разработчики могут с помощью [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] существенно повысить производительность своего труда.</span><span class="sxs-lookup"><span data-stu-id="b2def-112">Professional developers can use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="b2def-113">Используя [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], они могут сократить объемы необходимого кода и сделать его более выразительным, более компактным и более мощным.</span><span class="sxs-lookup"><span data-stu-id="b2def-113">With [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="b2def-114">Они могут одновременно использовать выражения запросов из нескольких доменов данных.</span><span class="sxs-lookup"><span data-stu-id="b2def-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="b2def-115">Что такое LINQ to XML?</span><span class="sxs-lookup"><span data-stu-id="b2def-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b2def-116"> - это оснащенный средствами LINQ и встроенный в память программный интерфейс XML, позволяющий работать с XML-файлами внутри языков программирования [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2def-116"> is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b2def-117">действует как объектной модели документов (DOM), что загружает XML-документа в памяти.</span><span class="sxs-lookup"><span data-stu-id="b2def-117"> is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="b2def-118">К такому документу можно направить запрос, его можно изменить, а после изменения его можно сохранить в файле или сериализовать и передать через Интернет.</span><span class="sxs-lookup"><span data-stu-id="b2def-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="b2def-119">Однако [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] отличается от модели DOM: он предоставляет модель объектов легкую и простую в работе, и в Visual Basic, используются преимущества функций языка.</span><span class="sxs-lookup"><span data-stu-id="b2def-119">However, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in Visual Basic.</span></span>  
  
 <span data-ttu-id="b2def-120">Важнейшее достоинство [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] состоит в его интеграции с [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2def-120">The most important advantage of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is its integration with [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)].</span></span> <span data-ttu-id="b2def-121">Эта интеграция дает возможность создавать запросы к загруженному в память XML-документу с целью получения коллекций элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="b2def-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="b2def-122">По своей функциональности (но не по синтаксису) реализованные в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] возможности формирования запросов сопоставимы с возможностями XPath и XQuery.</span><span class="sxs-lookup"><span data-stu-id="b2def-122">The query capability of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="b2def-123">Интеграция [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] в Visual Basic обеспечивается более строгая типизация, компиляции время проверки и улучшенная поддержка отладчика.</span><span class="sxs-lookup"><span data-stu-id="b2def-123">The integration of [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] in Visual Basic provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="b2def-124">Другим преимуществом [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] является возможность использования результатов запроса в качестве параметров <xref:System.Xml.Linq.XElement>и <xref:System.Xml.Linq.XAttribute>Конструкторы объектов позволяет применять мощный подход к созданию XML-деревьев.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b2def-124">Another advantage of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="b2def-125">Этот подход, именуемый *функциональное построение*, дает разработчикам возможность легко преобразовывать XML-деревья из одной формы в другую.</span><span class="sxs-lookup"><span data-stu-id="b2def-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="b2def-126">Например, может потребоваться типичный XML заказа на покупку, как описано в [пример XML-файла: типичный заказ на покупку (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348).</span><span class="sxs-lookup"><span data-stu-id="b2def-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348).</span></span> <span data-ttu-id="b2def-127">С помощью интерфейса [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] можно выполнить следующий запрос для получения значения атрибута артикула для каждого элемента в заказе на покупку:</span><span class="sxs-lookup"><span data-stu-id="b2def-127">By using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 <span data-ttu-id="b2def-128">Еще один пример. Пусть требуется сформировать отсортированный в соответствии с номерами деталей список продуктов стоимостью выше&100; долл.</span><span class="sxs-lookup"><span data-stu-id="b2def-128">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="b2def-129">Для получения этих сведений можно выполнить следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="b2def-129">To obtain this information, you could run the following query:</span></span>  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 <span data-ttu-id="b2def-130">Помимо этих [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] возможности, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] предоставляет усовершенствованный интерфейс программирования XML.</span><span class="sxs-lookup"><span data-stu-id="b2def-130">In addition to these [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] capabilities, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="b2def-131">Благодаря [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] появляются следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="b2def-131">Using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you can:</span></span>  
  
-   <span data-ttu-id="b2def-132">Загрузка XML из файлов или из потоков.</span><span class="sxs-lookup"><span data-stu-id="b2def-132">Load XML from files or streams.</span></span>  
  
-   <span data-ttu-id="b2def-133">Сериализация XML в файлы или в потоки.</span><span class="sxs-lookup"><span data-stu-id="b2def-133">Serialize XML to files or streams.</span></span>  
  
-   <span data-ttu-id="b2def-134">Создание XML-кодов «с чистого листа» с помощью функционального построения.</span><span class="sxs-lookup"><span data-stu-id="b2def-134">Create XML from scratch by using functional construction.</span></span>  
  
-   <span data-ttu-id="b2def-135">Обращение с запросами к XML с помощью XPath-подобных осей.</span><span class="sxs-lookup"><span data-stu-id="b2def-135">Query XML using XPath-like axes.</span></span>  
  
-   <span data-ttu-id="b2def-136">Управлять XML-дерева в памяти с помощью методов, таких как <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>и <xref:System.Xml.Linq.XElement.SetValue%2A>.</xref:System.Xml.Linq.XElement.SetValue%2A> </xref:System.Xml.Linq.XNode.ReplaceWith%2A> </xref:System.Xml.Linq.XNode.Remove%2A> </xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="b2def-136">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
-   <span data-ttu-id="b2def-137">Проверка XML-деревьев с помощью XSD.</span><span class="sxs-lookup"><span data-stu-id="b2def-137">Validate XML trees using XSD.</span></span>  
  
-   <span data-ttu-id="b2def-138">Использование сочетания этих функций для преобразования XML-деревьев из одной формы в другую.</span><span class="sxs-lookup"><span data-stu-id="b2def-138">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="b2def-139">Создание деревьев XML</span><span class="sxs-lookup"><span data-stu-id="b2def-139">Creating XML Trees</span></span>  
 <span data-ttu-id="b2def-140">Одним из наиболее важных преимуществ программирования с использованием [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] является простота создания XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="b2def-140">IOne of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="b2def-141">Например для создания небольшого XML-дерева, можно написать код следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b2def-141">For example, to create a small XML tree, you can write  code as follows:</span></span>  
  
```vb  
Dim contacts = _  
<Contacts>  
    <Contact>  
        <Name>Patrick Hines</Name>  
        <Phone Type="Home">206-555-0144</Phone>  
        <Phone Type="Work">425-555-0145</Phone>  
        <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
        </Address>  
    </Contact>  
</Contacts>  
```  
  
 <span data-ttu-id="b2def-142">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Компилятор преобразует XML-литералы в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] вызовов методов.</span><span class="sxs-lookup"><span data-stu-id="b2def-142">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler translates XML literals into [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] method calls.</span></span>  
  
 <span data-ttu-id="b2def-143">Дополнительные сведения см. в разделе [Создание XML-деревьев (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="b2def-143">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2def-144">См. также</span><span class="sxs-lookup"><span data-stu-id="b2def-144">See Also</span></span>  
 <span data-ttu-id="b2def-145"><xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="b2def-145"><xref:System.Xml.Linq></span></span>   
<span data-ttu-id="b2def-146"> [Приступая к работе (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="b2def-146"> [Getting Started (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md) </span></span>  
<span data-ttu-id="b2def-147"> [Общие сведения о LINQ to XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="b2def-147"> [Overview of LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md) </span></span>  
<span data-ttu-id="b2def-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span><span class="sxs-lookup"><span data-stu-id="b2def-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span></span>
