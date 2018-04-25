---
title: Обработка XML-данных с помощью LINQ to XML
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 059d6b9d-63f7-4011-9ba8-8406f0bbae7d
caps.latest.revision: 2
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4b3d9b53992cfa1c638266883f1298954f5a529c
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="process-xml-data-using-linq-to-xml"></a><span data-ttu-id="cc2a1-102">Обработка XML-данных с помощью LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="cc2a1-102">Process XML Data Using LINQ to XML</span></span>
<span data-ttu-id="cc2a1-103">LINQ to XML - новая модель для обработки XML-данных в платформе .NET Framework версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="cc2a1-103">LINQ to XML is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="cc2a1-104">С помощью LINQ to XML разработчик может выполнять над XML-данными любые операции: запросы, изменения, создание, сохранение и сериализацию XML-документов.</span><span class="sxs-lookup"><span data-stu-id="cc2a1-104">LINQ to XML allows developers to do everything they would expect with XML data: querying, modifying, creating, saving, and serializing XML documents.</span></span> <span data-ttu-id="cc2a1-105">Основные преимущества заключаются в возможностях запросов и создания.</span><span class="sxs-lookup"><span data-stu-id="cc2a1-105">The real advantages lie in the query and creation capabilities.</span></span>  
  
 <span data-ttu-id="cc2a1-106">Синтаксис запросов LINQ to XML краток и выразителен, он даже больше похож на SQL, чем на XPath или XQuery.</span><span class="sxs-lookup"><span data-stu-id="cc2a1-106">Queries in LINQ to XML are succinct and expressive, using syntax more similar to SQL than to XPath or XQuery.</span></span> <span data-ttu-id="cc2a1-107">Поскольку результаты запросов могут возвращаться как коллекции элементов или атрибутов, либо использоваться как параметры для объектов XElement, XML-деревья очень просто преобразовывать из одной формы в другую.</span><span class="sxs-lookup"><span data-stu-id="cc2a1-107">Because query results can be returned as collections of elements or attributes and can be used as parameters for XElement objects, XML trees can be easily transformed from one shape to another.</span></span>  
  
 <span data-ttu-id="cc2a1-108">В LINQ to XML используется технология интегрированного в язык запроса (LINQ) на платформе .NET Framework версии 3.5.</span><span class="sxs-lookup"><span data-stu-id="cc2a1-108">LINQ to XML leverages the language-integrated query (LINQ) technology in the .NET Framework version 3.5.</span></span> <span data-ttu-id="cc2a1-109">LINQ расширяет синтаксис C# и Visual Basic, обеспечивая мощные возможности запросов, которые потенциально могут охватить любое хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="cc2a1-109">LINQ extends the language syntax of C# and Visual Basic to provide powerful query capabilities that can be extended to potentially any data store.</span></span>  
  
 <span data-ttu-id="cc2a1-110">См. дополнительные сведения об использовании [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13), а также общие сведения о [платформе LINQ](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span><span class="sxs-lookup"><span data-stu-id="cc2a1-110">See [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) for a detailed discussion of its use, and see [LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) for an overview of the LINQ framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc2a1-111">См. также</span><span class="sxs-lookup"><span data-stu-id="cc2a1-111">See Also</span></span>  
 <xref:System.Xml.Linq>  
 <xref:System.Linq>  
 [<span data-ttu-id="cc2a1-112">Сравнение LINQ to XML с DOM</span><span class="sxs-lookup"><span data-stu-id="cc2a1-112">LINQ to XML vs. DOM</span></span>](https://msdn.microsoft.com/library/19b5ed02-feb2-455a-8897-f7f0fd76aca3)  
 [<span data-ttu-id="cc2a1-113">Сравнение LINQ to XML с другими XML-технологиями</span><span class="sxs-lookup"><span data-stu-id="cc2a1-113">LINQ to XML vs. Other XML Technologies</span></span>](https://msdn.microsoft.com/library/7ba1eecf-f09a-42de-bc80-22ca5b2e42d3)
