---
title: "Сохранение пробелов при Serializing2 | Документы Microsoft"
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
ms.assetid: 2d7abbd4-37f4-422b-89dd-0a694b5edc17
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
ms.openlocfilehash: de06e1a5a217644a2eae99f8c7752ee780594d22
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="preserving-white-space-while-serializing"></a><span data-ttu-id="0d32a-102">Сохранение пробелов при сериализации</span><span class="sxs-lookup"><span data-stu-id="0d32a-102">Preserving White Space While Serializing</span></span>
<span data-ttu-id="0d32a-103">В этом разделе описывается управление пробелами при сериализации XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="0d32a-103">This topic describes how to control white space when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="0d32a-104">Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами.</span><span class="sxs-lookup"><span data-stu-id="0d32a-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="0d32a-105">При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="0d32a-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="0d32a-106">Это поведение [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d32a-106">This is the default behavior for [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="0d32a-107">Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами.</span><span class="sxs-lookup"><span data-stu-id="0d32a-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="0d32a-108">Эти отступы ни в коем случае изменять нельзя.</span><span class="sxs-lookup"><span data-stu-id="0d32a-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="0d32a-109">Для этого в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] можно сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.</span><span class="sxs-lookup"><span data-stu-id="0d32a-109">To do this in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
## <a name="white-space-behavior-of-methods-that-serialize-xml-trees"></a><span data-ttu-id="0d32a-110">Управление пробелами в методах сериализации XML-деревьев</span><span class="sxs-lookup"><span data-stu-id="0d32a-110">White Space Behavior of Methods that Serialize XML Trees</span></span>  
 <span data-ttu-id="0d32a-111">Следующие методы в <xref:System.Xml.Linq.XElement>и <xref:System.Xml.Linq.XDocument>классы сериализации XML-дерева.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0d32a-111">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes serialize an XML tree.</span></span> <span data-ttu-id="0d32a-112">Можно сериализовать XML-дерево в файл <xref:System.IO.TextReader>, или <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> </xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="0d32a-112">You can serialize an XML tree to a file, a <xref:System.IO.TextReader>, or an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="0d32a-113">Метод `ToString` позволяет сериализовать в строку.</span><span class="sxs-lookup"><span data-stu-id="0d32a-113">The `ToString` method serializes to a string.</span></span>  
  
-   <span data-ttu-id="0d32a-114"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0d32a-114"><xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="0d32a-115"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0d32a-115"><xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="0d32a-116"><xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0d32a-116"><xref:System.Xml.Linq.XElement.ToString%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="0d32a-117"><xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0d32a-117"><xref:System.Xml.Linq.XDocument.ToString%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="0d32a-118">Если метод не принимает <xref:System.Xml.Linq.SaveOptions>как аргумент, затем этот метод будет форматировать (расставлять отступы) сериализованный XML.</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="0d32a-118">If the method does not take <xref:System.Xml.Linq.SaveOptions> as an argument, then the method will format (indent) the serialized XML.</span></span> <span data-ttu-id="0d32a-119">В этом случае все незначащие пробелы в XML-дереве удаляются.</span><span class="sxs-lookup"><span data-stu-id="0d32a-119">In this case, all insignificant white space in the XML tree is discarded.</span></span>  
  
 <span data-ttu-id="0d32a-120">Если метод берет <xref:System.Xml.Linq.SaveOptions>как аргумент, затем можно указать что метод не должен форматировать (расставлять отступы) сериализованный XML.</xref:System.Xml.Linq.SaveOptions></span><span class="sxs-lookup"><span data-stu-id="0d32a-120">If the method does take <xref:System.Xml.Linq.SaveOptions> as an argument, then you can specify that the method not format (indent) the serialized XML.</span></span> <span data-ttu-id="0d32a-121">В этом случае все незначащие пробелы в XML-дереве сохраняются.</span><span class="sxs-lookup"><span data-stu-id="0d32a-121">In this case, all white space in the XML tree is preserved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d32a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0d32a-122">See Also</span></span>  
 [<span data-ttu-id="0d32a-123">Сериализация деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d32a-123">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
