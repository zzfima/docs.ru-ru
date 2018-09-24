---
title: Изменение XML-данных с помощью XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b1f91616-3115-4264-9821-c66589d11d11
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5361ef036d91435b674a1637ac8c2a9a757bf8ab
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46492552"
---
# <a name="editing-xml-data-using-xpathnavigator"></a><span data-ttu-id="cfab6-102">Изменение XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="cfab6-102">Editing XML Data using XPathNavigator</span></span>
<span data-ttu-id="cfab6-103">Класс <xref:System.Xml.XPath.XPathNavigator> предоставляет методы для вставки, изменения и удаления узлов и значений из XML-документа, содержащегося в объекте <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="cfab6-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to insert, modify and remove nodes and values from an XML document contained in an <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="cfab6-104">Чтобы использовать любой из этих методов для вставки, изменения или удаления узлов и значений, объект <xref:System.Xml.XPath.XPathNavigator> должен быть доступен для изменения, то есть, его свойство <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> должно иметь значение true.</span><span class="sxs-lookup"><span data-stu-id="cfab6-104">In order to use any of these methods to insert, modify, and remove nodes and values, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be true.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cfab6-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="cfab6-105">In This Section</span></span>  
 [<span data-ttu-id="cfab6-106">Вставка XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="cfab6-106">Insert XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="cfab6-107">Описывает, как вставлять одноуровневые элементы, дочерние элементы, узлы атрибутов и значения в объект <xref:System.Xml.XmlDocument> с помощью класса <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="cfab6-107">Describes how to insert sibling, child, attribute nodes and values in to an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="cfab6-108">Изменение XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="cfab6-108">Modify XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="cfab6-109">Описывает, как изменять узлы и значения в объекте <xref:System.Xml.XmlDocument> с помощью класса <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="cfab6-109">Describes how to modify nodes and values in an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="cfab6-110">Удаление XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="cfab6-110">Remove XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="cfab6-111">Описывает, как удалять узлы и значения из объекта <xref:System.Xml.XmlDocument> с помощью класса <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="cfab6-111">Describes how to remove nodes and values from an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfab6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="cfab6-112">See also</span></span>

- <xref:System.Xml.XmlDocument>  
- <xref:System.Xml.XPath.XPathDocument>  
- <xref:System.Xml.XPath.XPathNavigator>  
- [<span data-ttu-id="cfab6-113">Обработка XML-данных с использованием модели данных XPath</span><span class="sxs-lookup"><span data-stu-id="cfab6-113">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
- [<span data-ttu-id="cfab6-114">Чтение XML-данных с помощью XPathDocument и XmlDocument</span><span class="sxs-lookup"><span data-stu-id="cfab6-114">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
- [<span data-ttu-id="cfab6-115">Выбор, вычисление и отбор XML-данных с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="cfab6-115">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
- [<span data-ttu-id="cfab6-116">Доступ к XML-данным с помощью класса XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="cfab6-116">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
- [<span data-ttu-id="cfab6-117">Проверка по схеме с помощью XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="cfab6-117">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
