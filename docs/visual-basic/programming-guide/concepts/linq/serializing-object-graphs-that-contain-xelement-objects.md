---
title: "Сериализация графов объектов, содержащих объекты XElement (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0cc5c92-5ca3-44b1-98dd-371601df721b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44a30e3c79eb1f68f968e83c50a55f24da9275cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-visual-basic"></a><span data-ttu-id="74667-102">Сериализация графов объектов, содержащих объекты XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74667-102">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>
<span data-ttu-id="74667-103">В этом разделе описаны возможности сериализации графов объектов, содержащих ссылки на объекты с типом <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="74667-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="74667-104">Для обеспечения сериализации этого типа класс <xref:System.Xml.Linq.XElement> реализует интерфейс <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="74667-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="74667-105">Обратите внимание, что сериализацию реализует только класс <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="74667-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74667-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="74667-106">In This Section</span></span>  
  
|<span data-ttu-id="74667-107">Раздел</span><span class="sxs-lookup"><span data-stu-id="74667-107">Topic</span></span>|<span data-ttu-id="74667-108">Описание</span><span class="sxs-lookup"><span data-stu-id="74667-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="74667-109">Как: сериализация с использованием XmlSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74667-109">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="74667-110">Демонстрирует, как выполнять сериализацию с помощью <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="74667-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="74667-111">Как: сериализация с использованием DataContractSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74667-111">How to: Serialize Using DataContractSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="74667-112">Демонстрирует, как выполнять сериализацию с помощью <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="74667-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74667-113">См. также</span><span class="sxs-lookup"><span data-stu-id="74667-113">See Also</span></span>  
 [<span data-ttu-id="74667-114">Дополнительно LINQ to XML, программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74667-114">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
