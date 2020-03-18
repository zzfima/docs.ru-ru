---
title: Практическое руководство. Управление префиксами пространств имен (C#) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: 9f43c0804d8c830fa75f1e1390cb578c5f5d5106
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141381"
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a><span data-ttu-id="aaaef-102">Практическое руководство. Управление префиксами пространств имен (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="aaaef-102">How to control namespace prefixes (C#) (LINQ to XML)</span></span>
<span data-ttu-id="aaaef-103">В этом разделе описывается управление префиксами пространств имен при сериализации дерева XML.</span><span class="sxs-lookup"><span data-stu-id="aaaef-103">This topic describes how you can control namespace prefixes when serializing an XML tree.</span></span>  
  
 <span data-ttu-id="aaaef-104">Во многих ситуациях управлять префиксами пространств имен нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="aaaef-104">In many situations, it is not necessary to control namespace prefixes.</span></span>  
  
 <span data-ttu-id="aaaef-105">Однако некоторые средства программирования XML требуют, чтобы была возможность управления префиксами пространства имен.</span><span class="sxs-lookup"><span data-stu-id="aaaef-105">However, certain XML programming tools require specific control of namespace prefixes.</span></span> <span data-ttu-id="aaaef-106">Например, при выполнении манипуляций с таблицами стилей XSLT или с документами XAML, которые содержат ссылающиеся на те или иные префиксы пространства имен внедренные выражения XPath, важно, чтобы документ сериализовался с этими конкретными префиксами.</span><span class="sxs-lookup"><span data-stu-id="aaaef-106">For example, you might be manipulating an XSLT style sheet or a XAML document that contains embedded XPath expressions that refer to specific namespace prefixes; in this case, it is important that the document be serialized with those specific prefixes.</span></span>  
  
 <span data-ttu-id="aaaef-107">Это основная причина, по которой необходимо управление префиксами пространства имен.</span><span class="sxs-lookup"><span data-stu-id="aaaef-107">This is the most common reason for controlling namespace prefixes.</span></span>  
  
 <span data-ttu-id="aaaef-108">Кроме того, возможность управления префиксами пространства имен требуется в тех случаях, когда необходимо, чтобы пользователи редактировали XML-документы вручную и могли без труда вводить префиксы с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="aaaef-108">Another common reason for controlling namespace prefixes is that you want users to edit the XML document manually, and you want to create namespace prefixes that are convenient for the user to type.</span></span> <span data-ttu-id="aaaef-109">Пусть создается документ XSD.</span><span class="sxs-lookup"><span data-stu-id="aaaef-109">For example, you might be generating an XSD document.</span></span> <span data-ttu-id="aaaef-110">В соответствии с соглашениями по схемам при этом в качестве префиксов пространства имен схемы используются `xs` или `xsd`.</span><span class="sxs-lookup"><span data-stu-id="aaaef-110">Conventions for schemas suggest that you use either `xs` or `xsd` as the prefix for the schema namespace.</span></span>  
  
 <span data-ttu-id="aaaef-111">Для управления префиксами пространства имен нужно вставлять атрибуты, объявляющие пространства имен.</span><span class="sxs-lookup"><span data-stu-id="aaaef-111">To control namespace prefixes, you insert attributes that declare namespaces.</span></span> <span data-ttu-id="aaaef-112">В случае объявления пространств имен с теми или иными префиксами [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] попытается учитывать префиксы пространств имен при сериализации.</span><span class="sxs-lookup"><span data-stu-id="aaaef-112">If you declare the namespaces with specific prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will attempt to honor the namespace prefixes when serializing.</span></span>  
  
 <span data-ttu-id="aaaef-113">Создать атрибут, объявляющий пространство имен с префиксом, можно, указав для имени атрибута пространство имен <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, а само имя атрибута в качестве префикса пространства имен.</span><span class="sxs-lookup"><span data-stu-id="aaaef-113">To create an attribute that declares a namespace with a prefix, you create an attribute where the namespace of the name of the attribute is <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, and the name of the attribute is the namespace prefix.</span></span> <span data-ttu-id="aaaef-114">Значение атрибута представляет собой URI пространства имен.</span><span class="sxs-lookup"><span data-stu-id="aaaef-114">The value of the attribute is the URI of the namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaaef-115">Пример</span><span class="sxs-lookup"><span data-stu-id="aaaef-115">Example</span></span>  
 <span data-ttu-id="aaaef-116">В этом примере объявляются два пространства имен.</span><span class="sxs-lookup"><span data-stu-id="aaaef-116">This example declares two namespaces.</span></span> <span data-ttu-id="aaaef-117">В нем указывается, что пространство имен `http://www.adventure-works.com` имеет префикс `aw`, а пространство имен `www.fourthcoffee.com` — префикс `fc`.</span><span class="sxs-lookup"><span data-stu-id="aaaef-117">It specifies that the `http://www.adventure-works.com` namespace has the prefix of `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="aaaef-118">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="aaaef-118">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aaaef-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aaaef-119">See also</span></span>

- [<span data-ttu-id="aaaef-120">Обзор пространств имен (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="aaaef-120">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
