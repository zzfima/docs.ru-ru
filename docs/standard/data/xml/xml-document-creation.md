---
title: Создание XML-документа
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
ms.openlocfilehash: a12555a02b45a964ff7efcbe00e0d2cb8637474a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709989"
---
# <a name="xml-document-creation"></a><span data-ttu-id="ccf75-102">Создание XML-документа</span><span class="sxs-lookup"><span data-stu-id="ccf75-102">XML Document Creation</span></span>
<span data-ttu-id="ccf75-103">XML-документ можно создать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="ccf75-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="ccf75-104">Один из них заключается в создании объекта **XmlDocument** без параметров.</span><span class="sxs-lookup"><span data-stu-id="ccf75-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="ccf75-105">Второй включает создание объекта **XmlDocument**, которому нужно в качестве параметра передать XmlNameTable.</span><span class="sxs-lookup"><span data-stu-id="ccf75-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="ccf75-106">В следующем примере показано создание пустого объекта **XmlDocument** без параметров.</span><span class="sxs-lookup"><span data-stu-id="ccf75-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="ccf75-107">После создания документа в него можно с помощью метода **Load** загрузить данные из строки, потока, URL-адреса, текстового модуля чтения или класса, производного от **XmlReader**.</span><span class="sxs-lookup"><span data-stu-id="ccf75-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="ccf75-108">Есть еще один метод загрузки: **LoadXML**, который считывает XML из строки.</span><span class="sxs-lookup"><span data-stu-id="ccf75-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="ccf75-109">Дополнительные сведения о различных методах **Load** см. в статье [Считывание XML-документа в DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="ccf75-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="ccf75-110">Существует класс с именем **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="ccf75-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="ccf75-111">Он является таблицей атомарных объектов строки.</span><span class="sxs-lookup"><span data-stu-id="ccf75-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="ccf75-112">Эта таблица предоставляет средству синтаксического анализа XML эффективный способ использовать один и тот же строковый объект для всех повторяющихся имен элементов и атрибутов в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="ccf75-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="ccf75-113">Класс **XmlNameTable** автоматически создается при создании документа, как показано выше, и заполняется именами элементов и атрибутов при загрузке этого документа.</span><span class="sxs-lookup"><span data-stu-id="ccf75-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="ccf75-114">Если у вас уже есть документ с таблицей имен и эти имена можно применить в другом документе, создайте новый документ с помощью метода **Load**, передав ему в качестве параметра таблицу **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="ccf75-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="ccf75-115">Когда документ создается с помощью этого метода, он использует существующую таблицу **XmlNameTable** со всеми атрибутами и элементами, ранее загруженными в нее из другого документа.</span><span class="sxs-lookup"><span data-stu-id="ccf75-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="ccf75-116">Это можно использовать для эффективного сравнения имен элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="ccf75-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="ccf75-117">Дополнительные сведения о классе **XmlNameTable** см. в таблице [Сравнение объектов с помощью XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span><span class="sxs-lookup"><span data-stu-id="ccf75-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="ccf75-118">Справочную информацию см. в статье <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="ccf75-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf75-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="ccf75-119">See also</span></span>

- [<span data-ttu-id="ccf75-120">Модель объектов документов XML (DOM)</span><span class="sxs-lookup"><span data-stu-id="ccf75-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
