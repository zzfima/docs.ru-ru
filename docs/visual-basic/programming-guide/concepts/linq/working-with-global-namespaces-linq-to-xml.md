---
title: Работа с глобальными пространствами имен (Visual Basic) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
ms.openlocfilehash: d8e74e949815d36f06f522460cc31ca6c3ccabb3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827384"
---
# <a name="working-with-global-namespaces-visual-basic-linq-to-xml"></a><span data-ttu-id="58618-102">Работа с глобальными пространствами имен (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="58618-102">Working with Global Namespaces (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="58618-103">Одним из ключевых особенностей XML-литералов в Visual Basic является возможность объявлять пространства имен XML с помощью `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="58618-103">One of the key features of XML literals in Visual Basic is the capability to declare XML namespaces by using the `Imports` statement.</span></span> <span data-ttu-id="58618-104">Используя эту возможность, можно объявить либо пространство имен XML, использующее префикс, либо пространство имен XML по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58618-104">Using this feature, you can declare an XML namespace that uses a prefix, or you can declare a default XML namespace.</span></span>  
  
 <span data-ttu-id="58618-105">Данная возможность полезна в двух ситуациях.</span><span class="sxs-lookup"><span data-stu-id="58618-105">This capability is useful in two situations.</span></span> <span data-ttu-id="58618-106">Во-первых, пространства имен, объявленные в XML-литералах, не переносятся во внедренные выражения.</span><span class="sxs-lookup"><span data-stu-id="58618-106">First, namespaces declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="58618-107">Применение деклараций глобальных пространств имен способствует снижению объема работы, которую необходимо выполнить в целях использования внедренных выражений с пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="58618-107">Declaring global namespaces reduces the amount of work that you have to do to use embedded expressions with namespaces.</span></span> <span data-ttu-id="58618-108">Во-вторых, необходимо объявить глобальные пространства имен в целях использования пространств имен с XML-свойствами.</span><span class="sxs-lookup"><span data-stu-id="58618-108">Second, you must declare global namespaces in order to use namespaces with XML properties.</span></span>  
  
 <span data-ttu-id="58618-109">Глобальные пространства имен можно объявлять на уровне проекта.</span><span class="sxs-lookup"><span data-stu-id="58618-109">You can declare global namespaces at the project level.</span></span> <span data-ttu-id="58618-110">Глобальные пространства имен можно также объявить на уровне модуля, что приводит к переопределению глобальных пространств имен уровня проекта.</span><span class="sxs-lookup"><span data-stu-id="58618-110">You can also declare global namespaces at the module level, which overrides the project-level global namespaces.</span></span> <span data-ttu-id="58618-111">Наконец, можно переопределить глобальные пространства имен в XML-литерале.</span><span class="sxs-lookup"><span data-stu-id="58618-111">Finally, you can override global namespaces in an XML literal.</span></span>  
  
 <span data-ttu-id="58618-112">При использовании XML-литералов или XML-свойств, находящихся в пространствах имен, объявленных глобально, можно видеть развернутое имя XML-литералов или свойств при наведении на них курсора в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="58618-112">When using XML literals or XML properties that are in globally-declared namespaces, you can see the expanded name of XML literals or properties by hovering over them in Visual Studio.</span></span> <span data-ttu-id="58618-113">Развернутое имя отобразится в подсказке.</span><span class="sxs-lookup"><span data-stu-id="58618-113">You will see the expanded name in a tooltip.</span></span>  
  
 <span data-ttu-id="58618-114">С помощью метода <xref:System.Xml.Linq.XNamespace> можно вызвать объект `GetXmlNamespace`, соответствующий глобальному пространству имен.</span><span class="sxs-lookup"><span data-stu-id="58618-114">You can get an <xref:System.Xml.Linq.XNamespace> object that corresponds to a global namespace using the `GetXmlNamespace` method.</span></span>  
  
## <a name="examples-of-global-namespaces"></a><span data-ttu-id="58618-115">Примеры глобальных пространств имен</span><span class="sxs-lookup"><span data-stu-id="58618-115">Examples of Global Namespaces</span></span>  
 <span data-ttu-id="58618-116">В следующем примере объявляется глобальное пространство имен по умолчанию с помощью инструкции `Imports`, а затем используется XML-литерал для инициализации объекта <xref:System.Xml.Linq.XElement> в данном пространстве имен:</span><span class="sxs-lookup"><span data-stu-id="58618-116">The following example declares a default global namespace by using the `Imports` statement, and then uses an XML literal to initialize an <xref:System.Xml.Linq.XElement> object in that namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="58618-117">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="58618-117">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" />  
```  
  
 <span data-ttu-id="58618-118">В следующем примере объявляется глобальное пространство имен с префиксом, а затем используется XML-литерал для инициализации элемента:</span><span class="sxs-lookup"><span data-stu-id="58618-118">The following example declares a global namespace with a prefix, and then uses an XML literal to initialize an element:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="58618-119">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="58618-119">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" />  
```  
  
## <a name="global-namespaces-and-embedded-expressions"></a><span data-ttu-id="58618-120">Глобальные пространства имен и внедренные выражения</span><span class="sxs-lookup"><span data-stu-id="58618-120">Global Namespaces and Embedded Expressions</span></span>  
 <span data-ttu-id="58618-121">Пространства имен, объявленные в XML-литералах, не переносятся во внедренные выражения.</span><span class="sxs-lookup"><span data-stu-id="58618-121">Namespaces that are declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="58618-122">В следующем примере объявляется пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58618-122">The following example declares a default namespace.</span></span> <span data-ttu-id="58618-123">Затем в нем используется внедренное выражение для элемента `Child`.</span><span class="sxs-lookup"><span data-stu-id="58618-123">It then uses an embedded expression for the `Child` element.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="58618-124">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="58618-124">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="" />  
</Root>  
```  
  
 <span data-ttu-id="58618-125">Очевидно, что результирующий XML включает декларацию пространства имен по умолчанию, так что элемент `Child` находится вне пространства имен.</span><span class="sxs-lookup"><span data-stu-id="58618-125">As you can see, the resulting XML includes a declaration of a default namespace so that the `Child` element is in no namespace.</span></span>  
  
 <span data-ttu-id="58618-126">Можно повторно объявить пространство имен во внедренном выражении следующим образом:</span><span class="sxs-lookup"><span data-stu-id="58618-126">You could re-declare the namespace in the embedded expression, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child xmlns="http://www.adventure-works.com"/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="58618-127">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="58618-127">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="http://www.adventure-works.com" />  
</Root>  
```  
  
 <span data-ttu-id="58618-128">Однако это более сложный и менее выгодный способ по сравнению с использованием глобального пространства имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="58618-128">However, this is more cumbersome to use than the global default namespace, which is a better approach.</span></span> <span data-ttu-id="58618-129">При наличии глобального пространства имен по умолчанию при использовании XML-литералов можно не декларировать пространства имен.</span><span class="sxs-lookup"><span data-stu-id="58618-129">With the global default namespace, you can use XML literals without declaring namespaces.</span></span> <span data-ttu-id="58618-130">Результирующий XML будет находиться в пространстве имен, объявленном глобально.</span><span class="sxs-lookup"><span data-stu-id="58618-130">The resulting XML will be in the globally-declared default namespace.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root>  
                                   <%= <Child/> %>  
                               </Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="58618-131">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="58618-131">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child />  
</Root>  
```  
  
## <a name="using-namespaces-with-xml-properties"></a><span data-ttu-id="58618-132">Использование пространств имен с XML-свойствами</span><span class="sxs-lookup"><span data-stu-id="58618-132">Using Namespaces with XML Properties</span></span>  
 <span data-ttu-id="58618-133">При работе с XML-деревом, находящимся в пространстве имен, и использовании XML-свойств необходимо использовать глобальное пространство имен, чтобы XML-свойства также находились в правильно заданном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="58618-133">If you are working with an XML tree that is in a namespace, and you use XML properties, then you must use a global namespace so that the XML properties will also be in the correct namespace.</span></span> <span data-ttu-id="58618-134">В следующем примере объявляется XML-дерево в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="58618-134">The following example declares an XML tree in a namespace.</span></span> <span data-ttu-id="58618-135">Затем в нем происходит вывод на печать числа элементов `Child`.</span><span class="sxs-lookup"><span data-stu-id="58618-135">It then prints the count of `Child` elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <Child>content</Child>  
    </Root>  
Console.WriteLine(root.<Child>.Count())  
```  
  
 <span data-ttu-id="58618-136">Данный пример указывает на отсутствие элементов `Child`.</span><span class="sxs-lookup"><span data-stu-id="58618-136">This example indicates that there are no `Child` elements.</span></span> <span data-ttu-id="58618-137">Выводятся следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="58618-137">It produces the following output:</span></span>  
  
```  
0  
```  
  
 <span data-ttu-id="58618-138">Однако после объявления глобального пространства имен по умолчанию в нем будут находиться и XML-литерал и XML-свойство.</span><span class="sxs-lookup"><span data-stu-id="58618-138">If, however, you declare a default global namespace, then both the XML literal and the XML property are in the default global namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>content</Child>  
            </Root>  
        Console.WriteLine(root.<Child>.Count())  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="58618-139">Данный пример указывает на отсутствие одного элемента `Child`.</span><span class="sxs-lookup"><span data-stu-id="58618-139">This example indicates that there is one `Child` element.</span></span> <span data-ttu-id="58618-140">Выводятся следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="58618-140">It produces the following output:</span></span>  
  
```  
1  
```  
  
 <span data-ttu-id="58618-141">После объявления глобального пространства имен с префиксом можно использовать префикс как для XML-литералов, так и для XML-свойств.</span><span class="sxs-lookup"><span data-stu-id="58618-141">If you declare a global namespace that has a prefix, you can use the prefix for both XML literals and XML properties:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>content</aw:Child>  
            </aw:Root>  
        Console.WriteLine(root.<aw:Child>.Count())  
    End Sub  
End Module  
```  
  
## <a name="xnamespace-and-global-namespaces"></a><span data-ttu-id="58618-142">XNamespace и глобальные пространства имен</span><span class="sxs-lookup"><span data-stu-id="58618-142">XNamespace and Global Namespaces</span></span>  
 <span data-ttu-id="58618-143">Объект <xref:System.Xml.Linq.XNamespace> можно получить с помощью метода `GetXmlNamespace`:</span><span class="sxs-lookup"><span data-stu-id="58618-143">You can get an <xref:System.Xml.Linq.XNamespace> object by using the `GetXmlNamespace` method:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Dim xn As XNamespace = GetXmlNamespace(aw)  
        Console.WriteLine(xn)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="58618-144">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="58618-144">This example produces the following output:</span></span>  
  
```  
http://www.adventure-works.com  
```  
  
## <a name="see-also"></a><span data-ttu-id="58618-145">См. также</span><span class="sxs-lookup"><span data-stu-id="58618-145">See also</span></span>

- [<span data-ttu-id="58618-146">Работа с пространствами имен XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58618-146">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
