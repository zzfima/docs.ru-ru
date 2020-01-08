---
title: Общие сведения о классе XAttribute
ms.date: 07/20/2015
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
ms.openlocfilehash: ceafe5478e41fb4c2038fd9300ef7b1ee6cb8411
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636657"
---
# <a name="xattribute-class-overview-visual-basic"></a><span data-ttu-id="80eda-102">Общие сведения о классе XAttribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80eda-102">XAttribute Class Overview (Visual Basic)</span></span>
<span data-ttu-id="80eda-103">Атрибуты - это пары «имя-значение», ассоциированные с элементом.</span><span class="sxs-lookup"><span data-stu-id="80eda-103">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="80eda-104">Класс <xref:System.Xml.Linq.XAttribute> представляет XML-атрибуты.</span><span class="sxs-lookup"><span data-stu-id="80eda-104">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="80eda-105">Обзор</span><span class="sxs-lookup"><span data-stu-id="80eda-105">Overview</span></span>  
 <span data-ttu-id="80eda-106">Работа с атрибутами [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] аналогична работе с элементами.</span><span class="sxs-lookup"><span data-stu-id="80eda-106">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="80eda-107">Они имеют аналогичные конструкторы.</span><span class="sxs-lookup"><span data-stu-id="80eda-107">Their constructors are similar.</span></span> <span data-ttu-id="80eda-108">Аналогичны и методы, используемые для получения их коллекций.</span><span class="sxs-lookup"><span data-stu-id="80eda-108">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="80eda-109">Выражение запроса LINQ для коллекции атрибутов очень похоже на выражение запроса LINQ для коллекции элементов.</span><span class="sxs-lookup"><span data-stu-id="80eda-109">A LINQ query expression for a collection of attributes looks very similar to a LINQ query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="80eda-110">Порядок, в котором атрибуты добавлялись к элементу, сохраняется.</span><span class="sxs-lookup"><span data-stu-id="80eda-110">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="80eda-111">Иначе говоря, при просмотре атрибутов они отображаются в том же порядке, в каком были добавлены.</span><span class="sxs-lookup"><span data-stu-id="80eda-111">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="80eda-112">Конструктор XAttribute</span><span class="sxs-lookup"><span data-stu-id="80eda-112">The XAttribute Constructor</span></span>  
 <span data-ttu-id="80eda-113">Чаще всего используется следующий конструктор класса <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="80eda-113">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="80eda-114">Конструктор</span><span class="sxs-lookup"><span data-stu-id="80eda-114">Constructor</span></span>|<span data-ttu-id="80eda-115">Описание</span><span class="sxs-lookup"><span data-stu-id="80eda-115">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="80eda-116">Создает объект <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="80eda-116">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="80eda-117">Аргумент `name` указывает имя атрибута; `content` указывает содержимое атрибута.</span><span class="sxs-lookup"><span data-stu-id="80eda-117">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="80eda-118">Создание элемента с атрибутом</span><span class="sxs-lookup"><span data-stu-id="80eda-118">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="80eda-119">В следующем коде показан элемент, содержащий атрибут с использованием литералов XML в Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="80eda-119">The following code shows an element that contains an attribute using XML literals in Visual Basic:</span></span>  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 <span data-ttu-id="80eda-120">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="80eda-120">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="80eda-121">Функциональное построение атрибутов</span><span class="sxs-lookup"><span data-stu-id="80eda-121">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="80eda-122">Объекты <xref:System.Xml.Linq.XAttribute> можно создавать в процессе создания объектов <xref:System.Xml.Linq.XElement> следующим образом:</span><span class="sxs-lookup"><span data-stu-id="80eda-122">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
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
  
 <span data-ttu-id="80eda-123">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="80eda-123">This example produces the following output:</span></span>  
  
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
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="80eda-124">Атрибуты не являются узлами</span><span class="sxs-lookup"><span data-stu-id="80eda-124">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="80eda-125">Между атрибутами и элементами имеются существенные различия.</span><span class="sxs-lookup"><span data-stu-id="80eda-125">There are some differences between attributes and elements.</span></span> <span data-ttu-id="80eda-126">Объекты <xref:System.Xml.Linq.XAttribute> не являются узлами в дереве XML.</span><span class="sxs-lookup"><span data-stu-id="80eda-126"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="80eda-127">Они представляют собой пары «имя-значение», ассоциированные с элементом XML.</span><span class="sxs-lookup"><span data-stu-id="80eda-127">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="80eda-128">В отличие от модели DOM, это более точно отражает структуру XML.</span><span class="sxs-lookup"><span data-stu-id="80eda-128">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="80eda-129">Хотя объекты <xref:System.Xml.Linq.XAttribute> фактически не являются узлами XML-дерева, работа с объектами <xref:System.Xml.Linq.XAttribute> весьма напоминает работу с объектами <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="80eda-129">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="80eda-130">Это различие имеет первостепенную важность только для разработчиков, создающих коды, которые взаимодействуют с XML-деревьями на уровне узлов.</span><span class="sxs-lookup"><span data-stu-id="80eda-130">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="80eda-131">Для многих разработчиков это различие не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="80eda-131">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80eda-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="80eda-132">See also</span></span>

- [<span data-ttu-id="80eda-133">Общие сведения о программировании LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80eda-133">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
