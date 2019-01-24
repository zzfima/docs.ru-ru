---
title: Сериализация деревьев XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
ms.openlocfilehash: 54591438b49005f9016560fcc2f314d6a947d485
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616762"
---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="69fca-102">Сериализация деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69fca-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="69fca-103">Сериализация XML-дерева означает создание XML из XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="69fca-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="69fca-104">Можно сериализовать в файл, в конкретный экземпляр класса <xref:System.IO.TextWriter> или в конкретный экземпляр класса <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="69fca-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="69fca-105">Можно управлять различными аспектами сериализации.</span><span class="sxs-lookup"><span data-stu-id="69fca-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="69fca-106">Например, можно выбрать либо расстановку отступов в сериализованном XML, либо написать XML-декларацию.</span><span class="sxs-lookup"><span data-stu-id="69fca-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69fca-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="69fca-107">In This Section</span></span>  
  
|<span data-ttu-id="69fca-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="69fca-108">Topic</span></span>|<span data-ttu-id="69fca-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="69fca-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="69fca-110">Сохранение пробелов при сериализации</span><span class="sxs-lookup"><span data-stu-id="69fca-110">Preserving White Space While Serializing</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="69fca-111">Описание управления пробелами при сериализации XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="69fca-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="69fca-112">Сериализация с использованием декларации XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69fca-112">Serializing with an XML Declaration (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="69fca-113">Описание сериализации XML-дерева, включающего XML-декларации.</span><span class="sxs-lookup"><span data-stu-id="69fca-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="69fca-114">Сериализация в файлы и объекты TextWriter и XmlWriter</span><span class="sxs-lookup"><span data-stu-id="69fca-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="69fca-115">Описание сериализации документа в файл <xref:System.IO.File>, объект <xref:System.IO.TextWriter> или объект <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="69fca-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="69fca-116">Сериализация в XmlReader (вызов XSLT) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69fca-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="69fca-117">Описание создания объекта <xref:System.Xml.XmlReader>, который позволяет другому модулю считывать содержимое XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="69fca-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69fca-118">См. также</span><span class="sxs-lookup"><span data-stu-id="69fca-118">See also</span></span>
- [<span data-ttu-id="69fca-119">Руководство по программированию (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69fca-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
