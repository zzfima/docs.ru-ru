---
title: "Сериализация деревьев XML (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: b3937e54-4ce9-4236-ac96-14e7972aa594
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 27001dbc92afddc35be12b593f5ba082c29af5f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-xml-trees-c"></a><span data-ttu-id="fafbd-102">Сериализация деревьев XML (C#)</span><span class="sxs-lookup"><span data-stu-id="fafbd-102">Serializing XML Trees (C#)</span></span>
<span data-ttu-id="fafbd-103">Сериализация XML-дерева означает создание XML из XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="fafbd-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="fafbd-104">Можно сериализовать в файл, в конкретный экземпляр класса <xref:System.IO.TextWriter> или в конкретный экземпляр класса <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="fafbd-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="fafbd-105">Можно управлять различными аспектами сериализации.</span><span class="sxs-lookup"><span data-stu-id="fafbd-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="fafbd-106">Например, можно выбрать либо расстановку отступов в сериализованном XML, либо написать XML-декларацию.</span><span class="sxs-lookup"><span data-stu-id="fafbd-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fafbd-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="fafbd-107">In This Section</span></span>  
  
|<span data-ttu-id="fafbd-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="fafbd-108">Topic</span></span>|<span data-ttu-id="fafbd-109">Описание</span><span class="sxs-lookup"><span data-stu-id="fafbd-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fafbd-110">Сохранение пробелов при сериализации</span><span class="sxs-lookup"><span data-stu-id="fafbd-110">Preserving White Space While Serializing</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="fafbd-111">Описание управления пробелами при сериализации XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="fafbd-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="fafbd-112">Сериализация с помощью объявления XML (C#)</span><span class="sxs-lookup"><span data-stu-id="fafbd-112">Serializing with an XML Declaration (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="fafbd-113">Описание сериализации XML-дерева, включающего XML-декларации.</span><span class="sxs-lookup"><span data-stu-id="fafbd-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="fafbd-114">Сериализация в файлы и объекты TextWriter и XmlWriter</span><span class="sxs-lookup"><span data-stu-id="fafbd-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="fafbd-115">Описание сериализации документа в файл <xref:System.IO.File>, объект <xref:System.IO.TextWriter> или объект <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="fafbd-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="fafbd-116">Сериализация в XmlReader (вызов XSLT) (C#)</span><span class="sxs-lookup"><span data-stu-id="fafbd-116">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="fafbd-117">Описание создания объекта <xref:System.Xml.XmlReader>, который позволяет другому модулю считывать содержимое XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="fafbd-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fafbd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fafbd-118">See Also</span></span>  
 [<span data-ttu-id="fafbd-119">Руководство по программированию (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fafbd-119">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
