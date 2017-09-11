---
title: "LINQ to XML Annotations2 | Документы Microsoft"
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
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 97f5386630ba687e4401ee0cfb70f7170e273a53
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="11524-102">Примечания LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="11524-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="11524-103">Заметки в [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] позволяют ассоциировать любой произвольный объект любого произвольного типа с любой компонент XML в XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="11524-103">Annotations in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="11524-104">Чтобы добавить заметку к компоненту XML, такие как <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XAttribute>, можно вызвать <xref:System.Xml.Linq.XObject.AddAnnotation%2A>метод.</xref:System.Xml.Linq.XObject.AddAnnotation%2A> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="11524-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="11524-105">Заметки получаются по типу.</span><span class="sxs-lookup"><span data-stu-id="11524-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="11524-106">Обратите внимание, что заметки не являются частью набора сведений XML, они не могут быть сериализованы или десериализованы.</span><span class="sxs-lookup"><span data-stu-id="11524-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="11524-107">Методы</span><span class="sxs-lookup"><span data-stu-id="11524-107">Methods</span></span>  
 <span data-ttu-id="11524-108">При работе с заметками можно использовать следующие методы.</span><span class="sxs-lookup"><span data-stu-id="11524-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="11524-109">Метод</span><span class="sxs-lookup"><span data-stu-id="11524-109">Method</span></span>|<span data-ttu-id="11524-110">Описание</span><span class="sxs-lookup"><span data-stu-id="11524-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="11524-111"><xref:System.Xml.Linq.XObject.AddAnnotation%2A></xref:System.Xml.Linq.XObject.AddAnnotation%2A></span><span class="sxs-lookup"><span data-stu-id="11524-111"><xref:System.Xml.Linq.XObject.AddAnnotation%2A></span></span>|<span data-ttu-id="11524-112">Добавляет объект к списку заметок <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="11524-112">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="11524-113"><xref:System.Xml.Linq.XObject.Annotation%2A></xref:System.Xml.Linq.XObject.Annotation%2A></span><span class="sxs-lookup"><span data-stu-id="11524-113"><xref:System.Xml.Linq.XObject.Annotation%2A></span></span>|<span data-ttu-id="11524-114">Возвращает первый объект заметки указанного типа из <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="11524-114">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="11524-115"><xref:System.Xml.Linq.XObject.Annotations%2A></xref:System.Xml.Linq.XObject.Annotations%2A></span><span class="sxs-lookup"><span data-stu-id="11524-115"><xref:System.Xml.Linq.XObject.Annotations%2A></span></span>|<span data-ttu-id="11524-116">Получает коллекцию заметок указанного типа для <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="11524-116">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="11524-117"><xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></span><span class="sxs-lookup"><span data-stu-id="11524-117"><xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></span></span>|<span data-ttu-id="11524-118">Удаляет заметки указанного типа из <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="11524-118">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11524-119">См. также</span><span class="sxs-lookup"><span data-stu-id="11524-119">See Also</span></span>  
 [<span data-ttu-id="11524-120">Дополнительно программированию LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11524-120">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
