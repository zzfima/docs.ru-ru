---
title: "Создание XML-документа"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a0806e34cfbf7c8e0b5ba995ca4876b8d10405e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-creation"></a><span data-ttu-id="365a4-102">Создание XML-документа</span><span class="sxs-lookup"><span data-stu-id="365a4-102">XML Document Creation</span></span>
<span data-ttu-id="365a4-103">XML-документ можно создать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="365a4-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="365a4-104">Один способ — создать **XmlDocument** без параметров.</span><span class="sxs-lookup"><span data-stu-id="365a4-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="365a4-105">Другим способом является создание **XmlDocument** и его передача классу XmlNameTable в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="365a4-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="365a4-106">В следующем примере показано, как создать новый, пустой **XmlDocument** без параметров.</span><span class="sxs-lookup"><span data-stu-id="365a4-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="365a4-107">После создания документа, можно загрузить его с данными из строки, потока, URL-адрес, средства чтения текста, или **XmlReader** производного класса с помощью **загрузить** метод.</span><span class="sxs-lookup"><span data-stu-id="365a4-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="365a4-108">Имеется также другой метод загрузки, **LoadXML** метод, который считывает XML из строки.</span><span class="sxs-lookup"><span data-stu-id="365a4-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="365a4-109">Дополнительные сведения о различных **нагрузки** методов, см. [считывание XML-документа в DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="365a4-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="365a4-110">Отсутствует класс с именем **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="365a4-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="365a4-111">Он является таблицей атомарных объектов строки.</span><span class="sxs-lookup"><span data-stu-id="365a4-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="365a4-112">Эта таблица предоставляет средству синтаксического анализа XML эффективный способ использовать один и тот же строковый объект для всех повторяющихся имен элементов и атрибутов в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="365a4-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="365a4-113">**XmlNameTable** создается автоматически, когда документ создается, как показано выше, а загружается с именами элементов и атрибутов при загрузке документа.</span><span class="sxs-lookup"><span data-stu-id="365a4-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="365a4-114">Если уже есть документ с именем таблицы, и эти имена могут быть полезны в другом документе, можно создать новый документ с помощью **нагрузки** метода, принимающего **XmlNameTable** как параметр.</span><span class="sxs-lookup"><span data-stu-id="365a4-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="365a4-115">При создании документа с помощью этого метода, он использует существующую **XmlNameTable** со всеми атрибутами и элементами, уже загруженными из другого документа.</span><span class="sxs-lookup"><span data-stu-id="365a4-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="365a4-116">Это можно использовать для эффективного сравнения имен элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="365a4-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="365a4-117">Дополнительные сведения о **XmlNameTable**, в разделе [сравнение объекта с помощью класса XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span><span class="sxs-lookup"><span data-stu-id="365a4-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="365a4-118">Справочную информацию см. в разделе <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="365a4-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="365a4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="365a4-119">See Also</span></span>  
 [<span data-ttu-id="365a4-120">Модель объектов XML-документов (DOM)</span><span class="sxs-lookup"><span data-stu-id="365a4-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
