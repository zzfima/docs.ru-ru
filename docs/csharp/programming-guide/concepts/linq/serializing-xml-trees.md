---
title: Сериализация деревьев XML (C#)
ms.date: 07/20/2015
ms.assetid: b3937e54-4ce9-4236-ac96-14e7972aa594
ms.openlocfilehash: 8f372a05bd69b801085cba9d9a3b11ae01841a2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="serializing-xml-trees-c"></a><span data-ttu-id="ee473-102">Сериализация деревьев XML (C#)</span><span class="sxs-lookup"><span data-stu-id="ee473-102">Serializing XML Trees (C#)</span></span>
<span data-ttu-id="ee473-103">Сериализация XML-дерева означает создание XML из XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="ee473-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="ee473-104">Можно сериализовать в файл, в конкретный экземпляр класса <xref:System.IO.TextWriter> или в конкретный экземпляр класса <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="ee473-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="ee473-105">Можно управлять различными аспектами сериализации.</span><span class="sxs-lookup"><span data-stu-id="ee473-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="ee473-106">Например, можно выбрать либо расстановку отступов в сериализованном XML, либо написать XML-декларацию.</span><span class="sxs-lookup"><span data-stu-id="ee473-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ee473-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ee473-107">In This Section</span></span>  
  
|<span data-ttu-id="ee473-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="ee473-108">Topic</span></span>|<span data-ttu-id="ee473-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="ee473-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ee473-110">Сохранение пробелов при сериализации</span><span class="sxs-lookup"><span data-stu-id="ee473-110">Preserving White Space While Serializing</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="ee473-111">Описание управления пробелами при сериализации XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="ee473-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="ee473-112">Сериализация с помощью объявления XML (C#)</span><span class="sxs-lookup"><span data-stu-id="ee473-112">Serializing with an XML Declaration (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="ee473-113">Описание сериализации XML-дерева, включающего XML-декларации.</span><span class="sxs-lookup"><span data-stu-id="ee473-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="ee473-114">Сериализация в файлы и объекты TextWriter и XmlWriter</span><span class="sxs-lookup"><span data-stu-id="ee473-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="ee473-115">Описание сериализации документа в файл <xref:System.IO.File>, объект <xref:System.IO.TextWriter> или объект <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="ee473-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="ee473-116">Сериализация в XmlReader (вызов XSLT) (C#)</span><span class="sxs-lookup"><span data-stu-id="ee473-116">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="ee473-117">Описание создания объекта <xref:System.Xml.XmlReader>, который позволяет другому модулю считывать содержимое XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="ee473-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee473-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ee473-118">See Also</span></span>  
 [<span data-ttu-id="ee473-119">Руководство по программированию (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ee473-119">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
