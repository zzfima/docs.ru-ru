---
title: Обработка XML-данных с помощью LINQ to XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 059d6b9d-63f7-4011-9ba8-8406f0bbae7d
ms.openlocfilehash: f45c5c9dccd2c1e8bdd67000a8b2f22425822ac9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710470"
---
# <a name="process-xml-data-using-linq-to-xml"></a><span data-ttu-id="7c64a-102">Обработка XML-данных с помощью LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="7c64a-102">Process XML Data Using LINQ to XML</span></span>
<span data-ttu-id="7c64a-103">LINQ to XML - новая модель для обработки XML-данных в платформе .NET Framework версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="7c64a-103">LINQ to XML is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="7c64a-104">С помощью LINQ to XML разработчик может выполнять над XML-данными любые операции: запросы, изменения, создание, сохранение и сериализацию XML-документов.</span><span class="sxs-lookup"><span data-stu-id="7c64a-104">LINQ to XML allows developers to do everything they would expect with XML data: querying, modifying, creating, saving, and serializing XML documents.</span></span> <span data-ttu-id="7c64a-105">Основные преимущества заключаются в возможностях запросов и создания.</span><span class="sxs-lookup"><span data-stu-id="7c64a-105">The real advantages lie in the query and creation capabilities.</span></span>  
  
 <span data-ttu-id="7c64a-106">Синтаксис запросов LINQ to XML краток и выразителен, он даже больше похож на SQL, чем на XPath или XQuery.</span><span class="sxs-lookup"><span data-stu-id="7c64a-106">Queries in LINQ to XML are succinct and expressive, using syntax more similar to SQL than to XPath or XQuery.</span></span> <span data-ttu-id="7c64a-107">Поскольку результаты запросов могут возвращаться как коллекции элементов или атрибутов, либо использоваться как параметры для объектов XElement, XML-деревья очень просто преобразовывать из одной формы в другую.</span><span class="sxs-lookup"><span data-stu-id="7c64a-107">Because query results can be returned as collections of elements or attributes and can be used as parameters for XElement objects, XML trees can be easily transformed from one shape to another.</span></span>  
  
 <span data-ttu-id="7c64a-108">В LINQ to XML используется технология интегрированного в язык запроса (LINQ) на платформе .NET Framework версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="7c64a-108">LINQ to XML leverages the language-integrated query (LINQ) technology in the .NET Framework version 3.5.</span></span> <span data-ttu-id="7c64a-109">LINQ расширяет синтаксис C# и Visual Basic, обеспечивая мощные возможности запросов, которые потенциально могут охватить любое хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="7c64a-109">LINQ extends the language syntax of C# and Visual Basic to provide powerful query capabilities that can be extended to potentially any data store.</span></span>  
  
 <span data-ttu-id="7c64a-110">Подробное описание использования см. в разделах [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) и [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7c64a-110">For a detailed discussion of its use, see [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) and [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span></span> <span data-ttu-id="7c64a-111">Общие сведения о платформе LINQ см. в разделе [LINQ — C#](../../../csharp/programming-guide/concepts/linq/index.md) или [LINQ — Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="7c64a-111">For an overview of the LINQ framework, see [Language-Integrated Query (LINQ) - C#](../../../csharp/programming-guide/concepts/linq/index.md) or [Language-Integrated Query (LINQ) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c64a-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="7c64a-112">See also</span></span>

- <xref:System.Xml.Linq>
- <xref:System.Linq>
- [<span data-ttu-id="7c64a-113">Сравнение LINQ to XML и DOM (C#)</span><span class="sxs-lookup"><span data-stu-id="7c64a-113">LINQ to XML vs. DOM (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/linq-to-xml-vs-dom.md)
- [<span data-ttu-id="7c64a-114">LINQ to XML и DOM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c64a-114">LINQ to XML vs. DOM (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-dom.md)
- [<span data-ttu-id="7c64a-115">LINQ to XML и другие технологии XML (C#)</span><span class="sxs-lookup"><span data-stu-id="7c64a-115">LINQ to XML vs. Other XML Technologies (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)
- [<span data-ttu-id="7c64a-116">LINQ to XML и другие технологии XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c64a-116">LINQ to XML vs. Other XML Technologies (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)
