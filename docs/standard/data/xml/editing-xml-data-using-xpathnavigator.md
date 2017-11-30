---
title: "Изменение XML-данных с помощью XPathNavigator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1f91616-3115-4264-9821-c66589d11d11
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 488651181aaec34c52f368d8829b1c556e6e746e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="editing-xml-data-using-xpathnavigator"></a><span data-ttu-id="ad195-102">Изменение XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ad195-102">Editing XML Data using XPathNavigator</span></span>
<span data-ttu-id="ad195-103">Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет методы для вставки, изменения и удаления узлов и значений из XML-документа, содержащегося в объекте <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="ad195-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to insert, modify and remove nodes and values from an XML document contained in an <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="ad195-104">Чтобы использовать любой из этих методов для вставки, изменения или удаления узлов и значений, объект <xref:System.Xml.XPath.XPathNavigator> должен быть доступен для изменения, то есть, его свойство <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> должно иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="ad195-104">In order to use any of these methods to insert, modify, and remove nodes and values, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be true.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad195-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="ad195-105">In This Section</span></span>  
 [<span data-ttu-id="ad195-106">Вставка XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ad195-106">Insert XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="ad195-107">Описывает, как вставлять одноуровневые элементы, дочерние элементы, узлы атрибутов и значения в объект <xref:System.Xml.XmlDocument> с помощью класса <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="ad195-107">Describes how to insert sibling, child, attribute nodes and values in to an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="ad195-108">Изменение XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ad195-108">Modify XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="ad195-109">Описывает, как изменять узлы и значения в объекте <xref:System.Xml.XmlDocument> с помощью класса <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="ad195-109">Describes how to modify nodes and values in an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="ad195-110">Удаление XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ad195-110">Remove XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="ad195-111">Описывает, как удалять узлы и значения из объекта <xref:System.Xml.XmlDocument> с помощью класса <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="ad195-111">Describes how to remove nodes and values from an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad195-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ad195-112">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="ad195-113">Обработка XML-данных с использованием модели данных XPath</span><span class="sxs-lookup"><span data-stu-id="ad195-113">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="ad195-114">Чтение XML-данных с помощью XPathDocument и XmlDocument</span><span class="sxs-lookup"><span data-stu-id="ad195-114">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="ad195-115">Выбор, вычисление и отбор XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ad195-115">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="ad195-116">Доступ к данным XML с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ad195-116">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="ad195-117">Проверка схемы с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ad195-117">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
