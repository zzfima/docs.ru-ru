---
title: LINQ to XML Annotations2
ms.date: 07/20/2015
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
ms.openlocfilehash: 891c451bc573e41e26833878187224cf54510435
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566857"
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="da374-102">Примечания LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="da374-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="da374-103">Заметки в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяют ассоциировать любой произвольный объект любого произвольного типа с любым XML-компонентом XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="da374-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="da374-104">Чтобы добавить заметку к компоненту XML, например <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute>, следует вызвать метод <xref:System.Xml.Linq.XObject.AddAnnotation%2A>.</span><span class="sxs-lookup"><span data-stu-id="da374-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="da374-105">Заметки получаются по типу.</span><span class="sxs-lookup"><span data-stu-id="da374-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="da374-106">Обратите внимание, что заметки не являются частью набора сведений XML, они не могут быть сериализованы или десериализованы.</span><span class="sxs-lookup"><span data-stu-id="da374-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="da374-107">Методы</span><span class="sxs-lookup"><span data-stu-id="da374-107">Methods</span></span>  
 <span data-ttu-id="da374-108">При работе с заметками можно использовать следующие методы.</span><span class="sxs-lookup"><span data-stu-id="da374-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="da374-109">Метод</span><span class="sxs-lookup"><span data-stu-id="da374-109">Method</span></span>|<span data-ttu-id="da374-110">Описание</span><span class="sxs-lookup"><span data-stu-id="da374-110">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="da374-111">Добавляет объект к списку заметок <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="da374-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="da374-112">Извлекает первый объект заметки указанного типа из <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="da374-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="da374-113">Извлекает коллекцию заметок указанного типа для <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="da374-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="da374-114">Удаляет заметки указанного типа из <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="da374-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da374-115">См. также</span><span class="sxs-lookup"><span data-stu-id="da374-115">See also</span></span>
- [<span data-ttu-id="da374-116">Расширенные программированию LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da374-116">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
