---
title: Сериализация графов объектов, содержащих объекты XElement (C#)
ms.date: 07/20/2015
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
ms.openlocfilehash: db7354598fc84c6fa3f8ec4e5b53799030459387
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569145"
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="4bd34-102">Сериализация графов объектов, содержащих объекты XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="4bd34-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="4bd34-103">В этом разделе описаны возможности сериализации графов объектов, содержащих ссылки на объекты с типом <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="4bd34-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="4bd34-104">Для обеспечения сериализации этого типа класс <xref:System.Xml.Linq.XElement> реализует интерфейс <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="4bd34-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="4bd34-105">Обратите внимание, что сериализацию реализует только класс <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="4bd34-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bd34-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4bd34-106">In This Section</span></span>  
  
|<span data-ttu-id="4bd34-107">Раздел</span><span class="sxs-lookup"><span data-stu-id="4bd34-107">Topic</span></span>|<span data-ttu-id="4bd34-108">Описание</span><span class="sxs-lookup"><span data-stu-id="4bd34-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4bd34-109">Практическое руководство. Сериализация с использованием XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="4bd34-109">How to: Serialize Using XmlSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="4bd34-110">Демонстрирует, как выполнять сериализацию с помощью <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="4bd34-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="4bd34-111">Практическое руководство. Сериализация с использованием DataContractSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="4bd34-111">How to: Serialize Using DataContractSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="4bd34-112">Демонстрирует, как выполнять сериализацию с помощью <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="4bd34-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4bd34-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4bd34-113">See also</span></span>

- [<span data-ttu-id="4bd34-114">Расширенные методы программирования LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="4bd34-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
