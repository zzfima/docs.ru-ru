---
title: Сериализация деревьев XML
ms.date: 07/20/2015
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
ms.openlocfilehash: 6b91078ff7f1b0410f97be9bc9ed3601f3ca0733
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351050"
---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="49ee3-102">Serializing XML Trees (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49ee3-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="49ee3-103">Сериализация XML-дерева означает создание XML из XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="49ee3-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="49ee3-104">Можно сериализовать в файл, в конкретный экземпляр класса <xref:System.IO.TextWriter> или в конкретный экземпляр класса <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="49ee3-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="49ee3-105">Можно управлять различными аспектами сериализации.</span><span class="sxs-lookup"><span data-stu-id="49ee3-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="49ee3-106">Например, можно выбрать либо расстановку отступов в сериализованном XML, либо написать XML-декларацию.</span><span class="sxs-lookup"><span data-stu-id="49ee3-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49ee3-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="49ee3-107">In This Section</span></span>  
  
|<span data-ttu-id="49ee3-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="49ee3-108">Topic</span></span>|<span data-ttu-id="49ee3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="49ee3-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="49ee3-110">Сохранение пробелов при сериализации</span><span class="sxs-lookup"><span data-stu-id="49ee3-110">Preserving White Space While Serializing</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="49ee3-111">Описание управления пробелами при сериализации XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="49ee3-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="49ee3-112">Serializing with an XML Declaration (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49ee3-112">Serializing with an XML Declaration (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="49ee3-113">Описание сериализации XML-дерева, включающего XML-декларации.</span><span class="sxs-lookup"><span data-stu-id="49ee3-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="49ee3-114">Сериализация в файлы и объекты TextWriter и XmlWriter</span><span class="sxs-lookup"><span data-stu-id="49ee3-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="49ee3-115">Описание сериализации документа в файл <xref:System.IO.File>, объект <xref:System.IO.TextWriter> или объект <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="49ee3-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="49ee3-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49ee3-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="49ee3-117">Описание создания объекта <xref:System.Xml.XmlReader>, который позволяет другому модулю считывать содержимое XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="49ee3-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49ee3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="49ee3-118">See also</span></span>

- [<span data-ttu-id="49ee3-119">Programming Guide (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49ee3-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
