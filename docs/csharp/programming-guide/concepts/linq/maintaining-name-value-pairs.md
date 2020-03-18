---
title: Обслуживание пар "имя-значение" (C#)
ms.date: 07/20/2015
ms.assetid: 7b04b0f1-af64-42eb-8737-83f8861b5915
ms.openlocfilehash: 9c42a154a4c3ed1463e428faab4c7d33197ef4a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591698"
---
# <a name="maintaining-namevalue-pairs-c"></a><span data-ttu-id="60ba4-102">Обслуживание пар "имя-значение" (C#)</span><span class="sxs-lookup"><span data-stu-id="60ba4-102">Maintaining Name/Value Pairs (C#)</span></span>
<span data-ttu-id="60ba4-103">Множеству приложений приходится сохранять данные, которые лучше всего хранить в виде пар «имя-значение».</span><span class="sxs-lookup"><span data-stu-id="60ba4-103">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="60ba4-104">Эти данные могут представлять сведения о конфигурации или глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="60ba4-104">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="60ba4-105">содержит несколько методов, которые облегчают хранение пар «имя-значение».</span><span class="sxs-lookup"><span data-stu-id="60ba4-105">contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="60ba4-106">Можно либо оставить информацию в виде атрибутов, либо в виде набора дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="60ba4-106">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="60ba4-107">Одно из отличий между хранением информации в виде атрибутов и в виде дочерних элементов состоит в том, что атрибуты имеют ограничение в том, что для элемента может быть только один атрибут с данным именем.</span><span class="sxs-lookup"><span data-stu-id="60ba4-107">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="60ba4-108">Это ограничение не относится к дочерним элементам.</span><span class="sxs-lookup"><span data-stu-id="60ba4-108">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="60ba4-109">Методы SetAttributeValue и SetElementValue</span><span class="sxs-lookup"><span data-stu-id="60ba4-109">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="60ba4-110">Два метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> и <xref:System.Xml.Linq.XElement.SetElementValue%2A> облегчают хранение в виде пар «имя-значение».</span><span class="sxs-lookup"><span data-stu-id="60ba4-110">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="60ba4-111">Эти два метода имеют похожую семантику.</span><span class="sxs-lookup"><span data-stu-id="60ba4-111">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="60ba4-112">С помощью метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> можно добавлять, изменять и удалять атрибуты данного элемента.</span><span class="sxs-lookup"><span data-stu-id="60ba4-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
- <span data-ttu-id="60ba4-113">При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> с несуществующим именем атрибута этот метод создаст новый атрибут и добавит его в указанный элемент.</span><span class="sxs-lookup"><span data-stu-id="60ba4-113">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="60ba4-114">При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> с существующим именем атрибута и с указанным содержимым содержимое данного атрибута замещается указанным содержимым.</span><span class="sxs-lookup"><span data-stu-id="60ba4-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="60ba4-115">При вызове метода <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> с существующим именем атрибута и с указанием значения NULL в качестве содержимого атрибут удаляется из своего родителя.</span><span class="sxs-lookup"><span data-stu-id="60ba4-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="60ba4-116">С помощью метода <xref:System.Xml.Linq.XElement.SetElementValue%2A> можно добавлять, изменять и удалять дочерние элементы данного элемента.</span><span class="sxs-lookup"><span data-stu-id="60ba4-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
- <span data-ttu-id="60ba4-117">При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A> с несуществующим именем дочернего элемента этот метод создаст новый элемент и добавит его к указанному элементу.</span><span class="sxs-lookup"><span data-stu-id="60ba4-117">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="60ba4-118">При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A> с существующим именем элемента и с указанным содержимым содержимое данного элемента замещается указанным содержимым.</span><span class="sxs-lookup"><span data-stu-id="60ba4-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="60ba4-119">При вызове метода <xref:System.Xml.Linq.XElement.SetElementValue%2A> с существующим именем атрибута и с указанием значения NULL в качестве содержимого атрибут удаляется из своего родителя.</span><span class="sxs-lookup"><span data-stu-id="60ba4-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60ba4-120">Пример</span><span class="sxs-lookup"><span data-stu-id="60ba4-120">Example</span></span>  
 <span data-ttu-id="60ba4-121">Следующий пример показывает, как создать элемент без атрибутов.</span><span class="sxs-lookup"><span data-stu-id="60ba4-121">The following example creates an element with no attributes.</span></span> <span data-ttu-id="60ba4-122">Затем используется метод <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> для создания и поддержания списка пар «имя-значение».</span><span class="sxs-lookup"><span data-stu-id="60ba4-122">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22);  
root.SetAttributeValue("Left", 20);  
root.SetAttributeValue("Bottom", 122);  
root.SetAttributeValue("Right", 300);  
root.SetAttributeValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
  
// Replace the value of Top.  
root.SetAttributeValue("Top", 10);  
Console.WriteLine(root);  
  
// Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="60ba4-123">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="60ba4-123">This example produces the following output:</span></span>  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="60ba4-124">Пример</span><span class="sxs-lookup"><span data-stu-id="60ba4-124">Example</span></span>  
 <span data-ttu-id="60ba4-125">Следующий пример показывает, как создать элемент без дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="60ba4-125">The following example creates an element with no child elements.</span></span> <span data-ttu-id="60ba4-126">Затем используется метод <xref:System.Xml.Linq.XElement.SetElementValue%2A> для создания и поддержания списка пар «имя-значение».</span><span class="sxs-lookup"><span data-stu-id="60ba4-126">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22);  
root.SetElementValue("Left", 20);  
root.SetElementValue("Bottom", 122);  
root.SetElementValue("Right", 300);  
root.SetElementValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Replace the value of Top.  
root.SetElementValue("Top", 10);  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Remove DefaultColor.  
root.SetElementValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="60ba4-127">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="60ba4-127">This example produces the following output:</span></span>  
  
```xml  
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
  
## <a name="see-also"></a><span data-ttu-id="60ba4-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="60ba4-128">See also</span></span>

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>
- [<span data-ttu-id="60ba4-129">Изменение деревьев XML (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="60ba4-129">Modifying XML Trees (LINQ to XML) (C#)</span></span>](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)
