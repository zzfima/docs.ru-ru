---
title: Сравнение функционального Процедурное программирование (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
ms.openlocfilehash: e87114d2edcda4b2df14eb2d84f62ebe9638b5eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69594247"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a><span data-ttu-id="44359-102">Сравнение функционального Процедурное программирование (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="44359-102">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>
<span data-ttu-id="44359-103">XML-приложения имеют самые разнообразные типы.</span><span class="sxs-lookup"><span data-stu-id="44359-103">There are various types of XML applications:</span></span>  
  
- <span data-ttu-id="44359-104">Некоторые приложения принимают исходные XML-документы и представляют новые XML-документы в новой форме, отличной от формы исходных документов.</span><span class="sxs-lookup"><span data-stu-id="44359-104">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
- <span data-ttu-id="44359-105">Некоторые приложения принимают исходные XML-документы и представляют документы совершенно в другом формате, например в виде кода HTML или текстовых файлов CSV.</span><span class="sxs-lookup"><span data-stu-id="44359-105">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
- <span data-ttu-id="44359-106">Некоторые приложения принимают исходные XML-документы и вставляют записи в базу данных.</span><span class="sxs-lookup"><span data-stu-id="44359-106">Some applications take source XML documents, and insert records into a database.</span></span>  
  
- <span data-ttu-id="44359-107">Некоторые приложения принимают данные из другого источника, например из базы данных, и создают из них XML-документы.</span><span class="sxs-lookup"><span data-stu-id="44359-107">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="44359-108">Это не все типы XML-приложений, а лишь представительный набор тех типов, которые приходится создавать программисту, работающему с кодом XML.</span><span class="sxs-lookup"><span data-stu-id="44359-108">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="44359-109">При всем разнообразии типов приложений существуют только два противоположных подхода, которыми может воспользоваться разработчик:</span><span class="sxs-lookup"><span data-stu-id="44359-109">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
- <span data-ttu-id="44359-110">функциональное построение с использованием декларативного стиля;</span><span class="sxs-lookup"><span data-stu-id="44359-110">Functional construction using a declarative approach.</span></span>  
  
- <span data-ttu-id="44359-111">модификация XML-дерева в оперативной памяти с использованием процедурного кода.</span><span class="sxs-lookup"><span data-stu-id="44359-111">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="44359-112">LINQ to XML поддерживает оба подхода.</span><span class="sxs-lookup"><span data-stu-id="44359-112">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="44359-113">При использовании функционального подхода вы должны написать преобразования исходных документов, чтобы получить совершенно новые документы нужного формата.</span><span class="sxs-lookup"><span data-stu-id="44359-113">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="44359-114">При изменении XML-дерева на месте вы должны написать код, который прослеживает узлы находящегося в памяти XML-дерева и переходит по ним, по мере необходимости вставляя, удаляя и изменяя узлы.</span><span class="sxs-lookup"><span data-stu-id="44359-114">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="44359-115">LINQ to XML можно использовать в обоих подходах.</span><span class="sxs-lookup"><span data-stu-id="44359-115">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="44359-116">Используются одни и те же классы, а в некоторых случаях и одинаковые методы.</span><span class="sxs-lookup"><span data-stu-id="44359-116">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="44359-117">Но организация и цели этих двух подходов существенно различаются.</span><span class="sxs-lookup"><span data-stu-id="44359-117">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="44359-118">Например, в разных ситуациях один из них часто оказывается производительнее другого и использует больше или меньше памяти.</span><span class="sxs-lookup"><span data-stu-id="44359-118">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="44359-119">Кроме того, код на основе одного или другого подхода легче писать, а сам код является более простым в обслуживании.</span><span class="sxs-lookup"><span data-stu-id="44359-119">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="44359-120">Сравнение этих двух подходов см. в разделе [Сравнение изменения XML-дерева в памяти с функциональным построением (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="44359-120">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="44359-121">Инструкции по написанию функциональных преобразований см. в разделе [Чистые функциональные преобразования XML (C#)](./introduction-to-pure-functional-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="44359-121">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (C#)](./introduction-to-pure-functional-transformations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44359-122">См. также</span><span class="sxs-lookup"><span data-stu-id="44359-122">See also</span></span>

- [<span data-ttu-id="44359-123">Общие сведения о программировании LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="44359-123">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
