---
title: "Сохранение пробелов при загрузке или синтаксическом анализе XML2 | Документы Microsoft"
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
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
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
ms.openlocfilehash: a2872c1e2354c0a0bd106f7fb945542ce37e7774
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a><span data-ttu-id="71044-102">Сохранение пробелов при загрузке и анализе XML</span><span class="sxs-lookup"><span data-stu-id="71044-102">Preserving White Space while Loading or Parsing XML</span></span>
<span data-ttu-id="71044-103">В этом разделе показан способ управления тем, как обрабатываются пробелы в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="71044-103">This topic describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="71044-104">Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами.</span><span class="sxs-lookup"><span data-stu-id="71044-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="71044-105">При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="71044-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="71044-106">Это поведение [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71044-106">This is the default behavior for [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="71044-107">Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами.</span><span class="sxs-lookup"><span data-stu-id="71044-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="71044-108">Эти отступы ни в коем случае изменять нельзя.</span><span class="sxs-lookup"><span data-stu-id="71044-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="71044-109">Для этого в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] можно сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.</span><span class="sxs-lookup"><span data-stu-id="71044-109">To do this in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
 <span data-ttu-id="71044-110">В этом разделе описывается, как методы, заполняющие XML-деревья, обрабатывают пробелы.</span><span class="sxs-lookup"><span data-stu-id="71044-110">This topic describes the white space behavior of methods that populate XML trees.</span></span> <span data-ttu-id="71044-111">Сведения об управлении пробелами при сериализации XML-деревьев см. в разделе [Сохранение пробелов при сериализации](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span><span class="sxs-lookup"><span data-stu-id="71044-111">For information about controlling white space when you serialize XML trees, see [Preserving White Space While Serializing](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a><span data-ttu-id="71044-112">Поведение методов, заполняющих XML-деревья</span><span class="sxs-lookup"><span data-stu-id="71044-112">Behavior of Methods that Populate XML Trees</span></span>  
 <span data-ttu-id="71044-113">Следующие методы в <xref:System.Xml.Linq.XElement>и <xref:System.Xml.Linq.XDocument>классы заполнение дерева XML.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="71044-113">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes populate an XML tree.</span></span> <span data-ttu-id="71044-114">Можно заполнить дерево XML из файла, <xref:System.IO.TextReader>, <xref:System.Xml.XmlReader>, или строка:</xref:System.Xml.XmlReader> </xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="71044-114">You can populate an XML tree from a file, a <xref:System.IO.TextReader>, an <xref:System.Xml.XmlReader>, or a string:</span></span>  
  
-   <span data-ttu-id="71044-115"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="71044-115"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="71044-116"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="71044-116"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="71044-117"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="71044-117"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="71044-118"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="71044-118"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="71044-119">Если метод не принимает <xref:System.Xml.Linq.LoadOptions>как аргумент, не будет сохранять незначащие пробелы.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="71044-119">If the method does not take <xref:System.Xml.Linq.LoadOptions> as an argument, the method will not preserve insignificant white space.</span></span>  
  
 <span data-ttu-id="71044-120">В большинстве случаев, если метод принимает <xref:System.Xml.Linq.LoadOptions>как аргумент, позволяет сохранять незначащие пробелы в XML-дереве как текстовые узлы.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="71044-120">In most cases, if the method takes <xref:System.Xml.Linq.LoadOptions> as an argument, you can optionally preserve insignificant white space as text nodes in the XML tree.</span></span> <span data-ttu-id="71044-121">Однако если метод загружает XML из <xref:System.Xml.XmlReader>, то <xref:System.Xml.XmlReader>определяет, будет ли сохраняться пробелы или нет.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="71044-121">However, if the method is loading the XML from an <xref:System.Xml.XmlReader>, then the <xref:System.Xml.XmlReader> determines whether white space will be preserved or not.</span></span> <span data-ttu-id="71044-122">Параметр <xref:System.Xml.Linq.LoadOptions>не повлияет.</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="71044-122">Setting <xref:System.Xml.Linq.LoadOptions> will have no effect.</span></span>  
  
 <span data-ttu-id="71044-123">С помощью этих методов, если пробелы сохраняются незначащие пробелы вставляется в XML-дерево как <xref:System.Xml.Linq.XText>узлов.</xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="71044-123">With these methods, if white space is preserved, insignificant white space is inserted into the XML tree as <xref:System.Xml.Linq.XText> nodes.</span></span> <span data-ttu-id="71044-124">Если же пробелы не сохраняются, то вставка текстовых узлов не происходит.</span><span class="sxs-lookup"><span data-stu-id="71044-124">If white space is not preserved, text nodes are not inserted.</span></span>  
  
 <span data-ttu-id="71044-125">Можно создать XML-дерево с помощью <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="71044-125">You can create an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="71044-126">Узлы, которые записываются в <xref:System.Xml.XmlWriter>вставляются в дерево.</xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="71044-126">Nodes that are written to the <xref:System.Xml.XmlWriter> are populated in the tree.</span></span> <span data-ttu-id="71044-127">Однако при построении XML-дерева при помощи этого метода сохраняются все методы, независимо от того, содержит ли узел пробел или нет, является ли пробел значащим или нет.</span><span class="sxs-lookup"><span data-stu-id="71044-127">However, when you build an XML tree using this method, all nodes are preserved, regardless of whether the node is white space or not, or whether the white space is significant or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71044-128">См. также</span><span class="sxs-lookup"><span data-stu-id="71044-128">See Also</span></span>  
 [<span data-ttu-id="71044-129">Синтаксический анализ XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71044-129">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
