---
title: "Функциональное сборка (LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d5c68fb71fd59d08574cee9eec933cee25e504d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="functional-construction-linq-to-xml-visual-basic"></a><span data-ttu-id="23639-102">Функциональное сборка (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23639-102">Functional Construction (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="23639-103"> предоставляет эффективный способ создания XML-элементов, который называется *функциональным построением*.</span><span class="sxs-lookup"><span data-stu-id="23639-103"> provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="23639-104">Функциональное построение — это возможность создать XML-дерево одной инструкцией.</span><span class="sxs-lookup"><span data-stu-id="23639-104">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="23639-105">Существует несколько основных функций интерфейса программирования [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], обеспечивающих функциональное построение.</span><span class="sxs-lookup"><span data-stu-id="23639-105">There are several key features of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface that enable functional construction:</span></span>  
  
-   <span data-ttu-id="23639-106">Конструктор <xref:System.Xml.Linq.XElement> принимает различные типы аргументов для содержимого.</span><span class="sxs-lookup"><span data-stu-id="23639-106">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="23639-107">Например, можно передать еще один объект <xref:System.Xml.Linq.XElement>, который станет дочерним элементом.</span><span class="sxs-lookup"><span data-stu-id="23639-107">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="23639-108">Можно передать объект <xref:System.Xml.Linq.XAttribute>, который станет атрибутом элемента.</span><span class="sxs-lookup"><span data-stu-id="23639-108">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="23639-109">Можно также передать любой другой тип объекта, который будет преобразован в строку и станет текстовым содержимым элемента.</span><span class="sxs-lookup"><span data-stu-id="23639-109">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
-   <span data-ttu-id="23639-110">Конструктор <xref:System.Xml.Linq.XElement> принимает массив `params` типа <xref:System.Object>, так что этому конструктору можно передать любое количество объектов.</span><span class="sxs-lookup"><span data-stu-id="23639-110">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="23639-111">Это позволяет создавать элементы со сложным содержимым.</span><span class="sxs-lookup"><span data-stu-id="23639-111">This enables you to create an element that has complex content.</span></span>  
  
-   <span data-ttu-id="23639-112">Если объект реализует интерфейс <xref:System.Collections.Generic.IEnumerable%601>, коллекция в этом объекте перечисляется и добавляются все элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="23639-112">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="23639-113">Если коллекция содержит объекты <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute>, каждый ее элемент добавляется отдельно.</span><span class="sxs-lookup"><span data-stu-id="23639-113">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="23639-114">Это важно, так как позволяет передавать результаты запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] конструктору.</span><span class="sxs-lookup"><span data-stu-id="23639-114">This is important because it lets you pass the results of a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query to the constructor.</span></span>  
  
 <span data-ttu-id="23639-115">Ниже представлен пример такого кода.</span><span class="sxs-lookup"><span data-stu-id="23639-115">The following is an example:</span></span>  
  
 <span data-ttu-id="23639-116">Эти функции позволяют создавать код с помощью литералов XML для создания XML-дерева, а также написать код, использующий результаты [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запросов при создании XML-дерева:</span><span class="sxs-lookup"><span data-stu-id="23639-116">These features enable you to write code using XML literals to create an XML tree, and also to write code that uses the results of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries when you create an XML tree:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where CInt(el) > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="23639-117">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="23639-117">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="23639-118">См. также</span><span class="sxs-lookup"><span data-stu-id="23639-118">See Also</span></span>  
 [<span data-ttu-id="23639-119">Создание деревьев XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23639-119">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
