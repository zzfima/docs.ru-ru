---
title: "Общие сведения о классе XAttribute (Visual Basic) | Документы Microsoft"
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
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 741e73987a9339a320114d74187c0056c7150924
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="xattribute-class-overview-visual-basic"></a><span data-ttu-id="52947-102">Общие сведения о классе XAttribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52947-102">XAttribute Class Overview (Visual Basic)</span></span>
<span data-ttu-id="52947-103">Атрибуты - это пары «имя-значение», ассоциированные с элементом.</span><span class="sxs-lookup"><span data-stu-id="52947-103">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="52947-104"><xref:System.Xml.Linq.XAttribute>Класс представляет XML-атрибуты.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="52947-104">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="52947-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="52947-105">Overview</span></span>  
 <span data-ttu-id="52947-106">Работа с атрибутами [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] аналогична работе с элементами.</span><span class="sxs-lookup"><span data-stu-id="52947-106">Working with attributes in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is similar to working with elements.</span></span> <span data-ttu-id="52947-107">Они имеют аналогичные конструкторы.</span><span class="sxs-lookup"><span data-stu-id="52947-107">Their constructors are similar.</span></span> <span data-ttu-id="52947-108">Аналогичны и методы, используемые для получения их коллекций.</span><span class="sxs-lookup"><span data-stu-id="52947-108">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="52947-109">Объект [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] выражение запроса для коллекции атрибутов очень похож на [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] выражение коллекции элементов запроса.</span><span class="sxs-lookup"><span data-stu-id="52947-109">A [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query expression for a collection of attributes looks very similar to a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="52947-110">Порядок, в котором атрибуты добавлялись к элементу, сохраняется.</span><span class="sxs-lookup"><span data-stu-id="52947-110">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="52947-111">Иначе говоря, при просмотре атрибутов они отображаются в том же порядке, в каком были добавлены.</span><span class="sxs-lookup"><span data-stu-id="52947-111">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="52947-112">Конструктор XAttribute</span><span class="sxs-lookup"><span data-stu-id="52947-112">The XAttribute Constructor</span></span>  
 <span data-ttu-id="52947-113">Следующий конструктор класса <xref:System.Xml.Linq.XAttribute>класс является тот, который будет использоваться чаще всего:</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="52947-113">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="52947-114">Конструктор</span><span class="sxs-lookup"><span data-stu-id="52947-114">Constructor</span></span>|<span data-ttu-id="52947-115">Описание</span><span class="sxs-lookup"><span data-stu-id="52947-115">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="52947-116">Создает <xref:System.Xml.Linq.XAttribute>объекта.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="52947-116">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="52947-117">Аргумент `name` указывает имя атрибута; `content` указывает содержимое атрибута.</span><span class="sxs-lookup"><span data-stu-id="52947-117">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="52947-118">Создание элемента с атрибутом</span><span class="sxs-lookup"><span data-stu-id="52947-118">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="52947-119">Следующий код показывает элемент, содержащий атрибут с помощью XML-литералов в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="52947-119">The following code shows an element that contains an attribute using XML literals in Visual Basic:</span></span>  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 <span data-ttu-id="52947-120">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="52947-120">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="52947-121">Функциональное построение атрибутов</span><span class="sxs-lookup"><span data-stu-id="52947-121">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="52947-122">Можно создавать <xref:System.Xml.Linq.XAttribute>объекты в процессе создания <xref:System.Xml.Linq.XElement>объектов следующим образом:</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="52947-122">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
```vb  
Dim c As XElement = _  
    <Customers>  
        <Customer>  
            <Name>John Doe</Name>  
            <PhoneNumbers>  
                <Phone type="home">555-555-5555</Phone>  
                <Phone type="work">666-666-6666</Phone>  
            </PhoneNumbers>  
        </Customer>  
    </Customers>  
Console.WriteLine(c)  
```  
  
 <span data-ttu-id="52947-123">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="52947-123">This example produces the following output:</span></span>  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="52947-124">Атрибуты не являются узлами</span><span class="sxs-lookup"><span data-stu-id="52947-124">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="52947-125">Между атрибутами и элементами имеются существенные различия.</span><span class="sxs-lookup"><span data-stu-id="52947-125">There are some differences between attributes and elements.</span></span> <span data-ttu-id="52947-126"><xref:System.Xml.Linq.XAttribute>объекты не являются узлами XML-дерева.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="52947-126"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="52947-127">Они представляют собой пары «имя-значение», ассоциированные с элементом XML.</span><span class="sxs-lookup"><span data-stu-id="52947-127">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="52947-128">В отличие от модели DOM, это более точно отражает структуру XML.</span><span class="sxs-lookup"><span data-stu-id="52947-128">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="52947-129">Хотя <xref:System.Xml.Linq.XAttribute>объектов фактически не являются узлами XML-дерева, работа с <xref:System.Xml.Linq.XAttribute>объекты очень похожа на работу с <xref:System.Xml.Linq.XElement>объектов.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="52947-129">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="52947-130">Это различие имеет первостепенную важность только для разработчиков, создающих коды, которые взаимодействуют с XML-деревьями на уровне узлов.</span><span class="sxs-lookup"><span data-stu-id="52947-130">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="52947-131">Для многих разработчиков это различие не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="52947-131">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52947-132">См. также</span><span class="sxs-lookup"><span data-stu-id="52947-132">See Also</span></span>  
 [<span data-ttu-id="52947-133">LINQ to XML обзор программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52947-133">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
