---
title: "Сериализация деревьев XML (Visual Basic) | Документы Microsoft"
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
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
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
ms.openlocfilehash: a63e875b1c1391ec1bb2b0ae64be9f9cff28d87d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="9e599-102">Сериализация деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e599-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="9e599-103">Сериализация XML-дерева означает создание XML из XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="9e599-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="9e599-104">Можно сериализовать в файл, чтобы конкретная реализация <xref:System.IO.TextWriter>класс, или на конкретную реализацию <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter></span><span class="sxs-lookup"><span data-stu-id="9e599-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="9e599-105">Можно управлять различными аспектами сериализации.</span><span class="sxs-lookup"><span data-stu-id="9e599-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="9e599-106">Например, можно выбрать либо расстановку отступов в сериализованном XML, либо написать XML-декларацию.</span><span class="sxs-lookup"><span data-stu-id="9e599-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e599-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="9e599-107">In This Section</span></span>  
  
|<span data-ttu-id="9e599-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="9e599-108">Topic</span></span>|<span data-ttu-id="9e599-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9e599-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9e599-110">Сохранение пробелов при сериализации</span><span class="sxs-lookup"><span data-stu-id="9e599-110">Preserving White Space While Serializing</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="9e599-111">Описание управления пробелами при сериализации XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="9e599-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="9e599-112">Сериализация с использованием декларации XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e599-112">Serializing with an XML Declaration (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="9e599-113">Описание сериализации XML-дерева, включающего XML-декларации.</span><span class="sxs-lookup"><span data-stu-id="9e599-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="9e599-114">Сериализация в файлы и объекты TextWriter и XmlWriter</span><span class="sxs-lookup"><span data-stu-id="9e599-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="9e599-115">Описание сериализации документа в <xref:System.IO.File>, <xref:System.IO.TextWriter>, или <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="9e599-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="9e599-116">Сериализация в XmlReader (вызов XSLT) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e599-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="9e599-117">Описывает создание <xref:System.Xml.XmlReader>, позволяет другому модулю считывать содержимое XML-дерева.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="9e599-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e599-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9e599-118">See Also</span></span>  
 [<span data-ttu-id="9e599-119">Руководство по программированию (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e599-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
