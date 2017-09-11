---
title: "Сериализация графов объектов, содержащих объекты XElement (C#)"
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
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
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
ms.openlocfilehash: 4e7b1d6365eb27596477de39577caa4144aa3501
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="5271b-102">Сериализация графов объектов, содержащих объекты XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="5271b-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="5271b-103">В этом разделе описаны возможности сериализации графов объектов, содержащих ссылки на объекты с типом <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="5271b-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="5271b-104">Для обеспечения сериализации этого типа класс <xref:System.Xml.Linq.XElement> реализует интерфейс <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="5271b-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="5271b-105">Обратите внимание, что сериализацию реализует только класс <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="5271b-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5271b-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="5271b-106">In This Section</span></span>  
  
|<span data-ttu-id="5271b-107">Раздел</span><span class="sxs-lookup"><span data-stu-id="5271b-107">Topic</span></span>|<span data-ttu-id="5271b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5271b-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5271b-109">Практическое руководство. Сериализация с использованием XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="5271b-109">How to: Serialize Using XmlSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="5271b-110">Демонстрирует, как выполнять сериализацию с помощью <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5271b-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="5271b-111">Практическое руководство. Сериализация с использованием DataContractSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="5271b-111">How to: Serialize Using DataContractSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="5271b-112">Демонстрирует, как выполнять сериализацию с помощью <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5271b-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5271b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5271b-113">See Also</span></span>  
 [<span data-ttu-id="5271b-114">Расширенные методы программирования LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5271b-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

