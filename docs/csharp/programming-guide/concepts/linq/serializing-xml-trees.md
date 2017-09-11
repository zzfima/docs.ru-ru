---
title: "Сериализация деревьев XML (C#)"
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
ms.assetid: b3937e54-4ce9-4236-ac96-14e7972aa594
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
ms.openlocfilehash: f3b8ee68065a056cccbf02d96bf5f21e7ccea16b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-xml-trees-c"></a><span data-ttu-id="71a77-102">Сериализация деревьев XML (C#)</span><span class="sxs-lookup"><span data-stu-id="71a77-102">Serializing XML Trees (C#)</span></span>
<span data-ttu-id="71a77-103">Сериализация XML-дерева означает создание XML из XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="71a77-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="71a77-104">Можно сериализовать в файл, в конкретный экземпляр класса <xref:System.IO.TextWriter> или в конкретный экземпляр класса <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="71a77-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="71a77-105">Можно управлять различными аспектами сериализации.</span><span class="sxs-lookup"><span data-stu-id="71a77-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="71a77-106">Например, можно выбрать либо расстановку отступов в сериализованном XML, либо написать XML-декларацию.</span><span class="sxs-lookup"><span data-stu-id="71a77-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="71a77-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="71a77-107">In This Section</span></span>  
  
|<span data-ttu-id="71a77-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="71a77-108">Topic</span></span>|<span data-ttu-id="71a77-109">Описание</span><span class="sxs-lookup"><span data-stu-id="71a77-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="71a77-110">Сохранение пробелов при сериализации</span><span class="sxs-lookup"><span data-stu-id="71a77-110">Preserving White Space While Serializing</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="71a77-111">Описание управления пробелами при сериализации XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="71a77-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="71a77-112">Сериализация с помощью объявления XML (C#)</span><span class="sxs-lookup"><span data-stu-id="71a77-112">Serializing with an XML Declaration (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="71a77-113">Описание сериализации XML-дерева, включающего XML-декларации.</span><span class="sxs-lookup"><span data-stu-id="71a77-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="71a77-114">Сериализация в файлы и объекты TextWriter и XmlWriter</span><span class="sxs-lookup"><span data-stu-id="71a77-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="71a77-115">Описание сериализации документа в файл <xref:System.IO.File>, объект <xref:System.IO.TextWriter> или объект <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="71a77-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="71a77-116">Сериализация в XmlReader (вызов XSLT) (C#)</span><span class="sxs-lookup"><span data-stu-id="71a77-116">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="71a77-117">Описание создания объекта <xref:System.Xml.XmlReader>, который позволяет другому модулю считывать содержимое XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="71a77-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71a77-118">См. также</span><span class="sxs-lookup"><span data-stu-id="71a77-118">See Also</span></span>  
 [<span data-ttu-id="71a77-119">Руководство по программированию (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="71a77-119">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

