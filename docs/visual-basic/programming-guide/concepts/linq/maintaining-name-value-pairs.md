---
title: "Обслуживание пар &quot;имя значение&quot; (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 30e40c73430f385815b7a08a2507343db0fafd4f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="maintaining-namevalue-pairs-visual-basic"></a><span data-ttu-id="47ecd-102">Обслуживание пар имя значение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47ecd-102">Maintaining Name/Value Pairs (Visual Basic)</span></span>
<span data-ttu-id="47ecd-103">Множеству приложений приходится сохранять данные, которые лучше всего хранить в виде пар «имя-значение».</span><span class="sxs-lookup"><span data-stu-id="47ecd-103">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="47ecd-104">Эти данные могут представлять сведения о конфигурации или глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="47ecd-104">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="47ecd-105"> содержит несколько методов, которые облегчают хранение пар «имя-значение».</span><span class="sxs-lookup"><span data-stu-id="47ecd-105"> contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="47ecd-106">Можно либо оставить информацию в виде атрибутов, либо в виде набора дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="47ecd-106">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="47ecd-107">Одно из отличий между хранением информации в виде атрибутов и в виде дочерних элементов состоит в том, что атрибуты имеют ограничение в том, что для элемента может быть только один атрибут с данным именем.</span><span class="sxs-lookup"><span data-stu-id="47ecd-107">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="47ecd-108">Это ограничение не относится к дочерним элементам.</span><span class="sxs-lookup"><span data-stu-id="47ecd-108">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="47ecd-109">Методы SetAttributeValue и SetElementValue</span><span class="sxs-lookup"><span data-stu-id="47ecd-109">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="47ecd-110">Два метода, которые облегчают хранение имя значение пары <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>и <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</xref:System.Xml.Linq.XElement.SetElementValue%2A> </xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-110">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="47ecd-111">Эти два метода имеют похожую семантику.</span><span class="sxs-lookup"><span data-stu-id="47ecd-111">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="47ecd-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A>можно добавить, изменить или удалить атрибуты элемента.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
-   <span data-ttu-id="47ecd-113">При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>с имя атрибута, который не существует, этот метод создаст новый атрибут и добавляет его в указанный элемент.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-113">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
-   <span data-ttu-id="47ecd-114">При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>с именем существующего атрибута и с указанным содержимого, содержимое атрибута замещается указанным содержимым.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
-   <span data-ttu-id="47ecd-115">При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>с существующим именем атрибута и с указанием значения null для содержимого, атрибут удаляется из родительского.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="47ecd-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A>можно добавлять, изменять или удалять дочерние элементы данного элемента.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
-   <span data-ttu-id="47ecd-117">При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A>с именем дочерний элемент, который не существует, этот метод создает новый элемент и добавляет его в указанный элемент.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-117">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
-   <span data-ttu-id="47ecd-118">При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A>с именем существующего элемента и с указанным содержимым, содержимое элемента, заменяются с указанным содержимым.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
-   <span data-ttu-id="47ecd-119">При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A>с именем существующего элемента и задать значение null для содержимого, элемент удаляется из своего родителя.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47ecd-120">Пример</span><span class="sxs-lookup"><span data-stu-id="47ecd-120">Example</span></span>  
 <span data-ttu-id="47ecd-121">Следующий пример показывает, как создать элемент без атрибутов.</span><span class="sxs-lookup"><span data-stu-id="47ecd-121">The following example creates an element with no attributes.</span></span> <span data-ttu-id="47ecd-122">Затем он использует <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>метод для создания и поддержания списка пар имя значение.</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-122">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22)  
root.SetAttributeValue("Left", 20)  
root.SetAttributeValue("Bottom", 122)  
root.SetAttributeValue("Right", 300)  
root.SetAttributeValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
  
' Replace the value of Top.  
root.SetAttributeValue("Top", 10)  
Console.WriteLine(root)  
  
' Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="47ecd-123">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="47ecd-123">This example produces the following output:</span></span>  
  
```  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="47ecd-124">Пример</span><span class="sxs-lookup"><span data-stu-id="47ecd-124">Example</span></span>  
 <span data-ttu-id="47ecd-125">Следующий пример показывает, как создать элемент без дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="47ecd-125">The following example creates an element with no child elements.</span></span> <span data-ttu-id="47ecd-126">Затем он использует <xref:System.Xml.Linq.XElement.SetElementValue%2A>метод для создания и поддержания списка пар имя значение.</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-126">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22)  
root.SetElementValue("Left", 20)  
root.SetElementValue("Bottom", 122)  
root.SetElementValue("Right", 300)  
root.SetElementValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Replace the value of Top.  
root.SetElementValue("Top", 10)  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Remove DefaultColor.  
root.SetElementValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
  
```  
  
 <span data-ttu-id="47ecd-127">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="47ecd-127">This example produces the following output:</span></span>  
  
```  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="47ecd-128">См. также</span><span class="sxs-lookup"><span data-stu-id="47ecd-128">See Also</span></span>  
 <span data-ttu-id="47ecd-129"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A></xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-129"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span></span>   
 <span data-ttu-id="47ecd-130"><xref:System.Xml.Linq.XElement.SetElementValue%2A></xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="47ecd-130"><xref:System.Xml.Linq.XElement.SetElementValue%2A></span></span>   
<span data-ttu-id="47ecd-131"> [Изменение деревьев XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="47ecd-131"> [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)</span></span>
