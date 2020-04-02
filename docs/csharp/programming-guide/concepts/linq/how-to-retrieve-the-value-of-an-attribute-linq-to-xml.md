---
title: Как получить значение атрибута (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: 212ad3bb3097e7e2c76da8f165011b181f329d4c
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249198"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="6d599-102">Как получить значение атрибута (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6d599-102">How to retrieve the value of an attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="6d599-103">В этом разделе показано получение значений атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6d599-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="6d599-104">Существует два основных способа. Можно привести <xref:System.Xml.Linq.XAttribute> к требуемому типу, после этого оператор явного преобразования преобразует содержимое элемента или атрибута в указанный тип.</span><span class="sxs-lookup"><span data-stu-id="6d599-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="6d599-105">Иначе можно использовать свойство <xref:System.Xml.Linq.XAttribute.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="6d599-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="6d599-106">Однако приведение, как правило, является лучшим подходом.</span><span class="sxs-lookup"><span data-stu-id="6d599-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="6d599-107">В частности, упрощается написание кода, обеспечивающего получение значения атрибута, который может существовать или не существовать, после приведения атрибута к типу значения, допускающему значение NULL.</span><span class="sxs-lookup"><span data-stu-id="6d599-107">If you cast the attribute to a nullable value type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="6d599-108">Примеры использования этой технологии см. в руководстве по [извлечению значений элемента (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6d599-108">For examples of this technique, see [How to retrieve the value of an element (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d599-109">Пример</span><span class="sxs-lookup"><span data-stu-id="6d599-109">Example</span></span>  
 <span data-ttu-id="6d599-110">Для получения значения атрибута нужно просто привести объект <xref:System.Xml.Linq.XAttribute> к желаемому типу.</span><span class="sxs-lookup"><span data-stu-id="6d599-110">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="6d599-111">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6d599-111">This example produces the following output:</span></span>  
  
```output  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="6d599-112">Пример</span><span class="sxs-lookup"><span data-stu-id="6d599-112">Example</span></span>  
 <span data-ttu-id="6d599-113">В следующем примере показано, как получить значение атрибута, если атрибут находится в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="6d599-113">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="6d599-114">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6d599-114">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="6d599-115">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6d599-115">This example produces the following output:</span></span>  
  
```output  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d599-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6d599-116">See also</span></span>

- [<span data-ttu-id="6d599-117">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="6d599-117">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
