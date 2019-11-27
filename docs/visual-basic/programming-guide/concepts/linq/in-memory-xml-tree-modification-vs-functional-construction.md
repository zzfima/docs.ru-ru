---
title: Изменение дерева XML в памяти и функциональное сборка (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: d91c4ebf-6549-43cc-9961-26d4a82f722b
ms.openlocfilehash: 15c38cdf7ce860b34d8d3e9d59b8f06d80f6edd8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344442"
---
# <a name="in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml-visual-basic"></a><span data-ttu-id="a9252-102">Сравнение изменений XML-дерева в памяти и функциональное построение (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9252-102">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="a9252-103">Изменение XML-дерева на месте является традиционным подходом к изменению формы XML-документа.</span><span class="sxs-lookup"><span data-stu-id="a9252-103">Modifying an XML tree in place is a traditional approach to changing the shape of an XML document.</span></span> <span data-ttu-id="a9252-104">Стандартное приложение загружает документ в источник данных, например DOM или [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], при помощи интерфейса программирования вставляет, удаляет узлы или изменяет их содержимое, а затем сохраняет XML в файл или передает по сети.</span><span class="sxs-lookup"><span data-stu-id="a9252-104">A typical application loads a document into a data store such as DOM or [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]; uses a programming interface to insert nodes, delete nodes, or change the content of nodes; and then saves the XML to a file or transmits it over a network.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="a9252-105">поддерживает другой подход, который во многих случаях может оказаться удобным, — *функциональное построение*.</span><span class="sxs-lookup"><span data-stu-id="a9252-105">enables another approach that is useful in many scenarios *: functional construction*.</span></span> <span data-ttu-id="a9252-106">При функциональном построении изменение данных рассматривается как задача преобразования, а не как детализированное управление хранилищем данных.</span><span class="sxs-lookup"><span data-stu-id="a9252-106">Functional construction treats modifying data as a problem of transformation, rather than as detailed manipulation of a data store.</span></span> <span data-ttu-id="a9252-107">Если можно взять представление данных и эффективно преобразовать его из одной формы в другую, то результат будет таким же, как если бы в одном хранилище данных были произведены некоторые изменения, направленные на то, чтобы оно приняло другую форму.</span><span class="sxs-lookup"><span data-stu-id="a9252-107">If you can take a representation of data and transform it efficiently from one form to another, the result is the same as if you took one data store and manipulated it in some way to take another shape.</span></span> <span data-ttu-id="a9252-108">Основным элементом функционального построения является передача результатов запросов конструкторам <xref:System.Xml.Linq.XDocument> и <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a9252-108">A key to the functional construction approach is to pass the results of queries to <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement> constructors.</span></span>  
  
 <span data-ttu-id="a9252-109">Во многих случаях можно написать код для преобразования, затратив лишь часть того времени, которое ушло бы на внесение изменений в хранилище данных, причем этот код надежнее и его проще сопровождать.</span><span class="sxs-lookup"><span data-stu-id="a9252-109">In many cases you can write the transformational code in a fraction of the time that it would take to manipulate the data store, and that code is more robust and easier to maintain.</span></span> <span data-ttu-id="a9252-110">В таких случаях это более эффективный способ изменения данных, несмотря на то что для его реализации может потребоваться больше вычислительной мощности.</span><span class="sxs-lookup"><span data-stu-id="a9252-110">In these cases, even though the transformational approach can take more processing power, it is a more effective way to modify data.</span></span> <span data-ttu-id="a9252-111">Если разработчик знаком с функциональным подходом, то во многих случаях итоговый код получается проще для понимания.</span><span class="sxs-lookup"><span data-stu-id="a9252-111">If a developer is familiar with the functional approach, the resulting code in many cases is easier to understand.</span></span> <span data-ttu-id="a9252-112">Проще найти код, который изменяет каждую часть дерева.</span><span class="sxs-lookup"><span data-stu-id="a9252-112">It is easy to find the code that modifies each part of the tree.</span></span>  
  
 <span data-ttu-id="a9252-113">Вариант, когда XML-дерево изменяется на месте, в большей степени известен многим программистам DOM, а код, написанный при помощи функционального подхода, может показаться программисту, который еще не разобрался в этом методе, незнакомым.</span><span class="sxs-lookup"><span data-stu-id="a9252-113">The approach where you modify an XML tree in-place is more familiar to many DOM programmers, whereas code written using the functional approach might look unfamiliar to a developer who doesn't yet understand that approach.</span></span> <span data-ttu-id="a9252-114">Если требуется внести лишь небольшое изменение в большое XML-дерево, то при изменении дерева на месте во многих случаях требуется меньше времени ЦП.</span><span class="sxs-lookup"><span data-stu-id="a9252-114">If you have to only make a small modification to a large XML tree, the approach where you modify a tree in place in many cases will take less CPU time.</span></span>  
  
 <span data-ttu-id="a9252-115">В этом разделе приведен пример, реализованный обоими методами.</span><span class="sxs-lookup"><span data-stu-id="a9252-115">This topic provides an example that is implemented with both approaches.</span></span>  
  
## <a name="transforming-attributes-into-elements"></a><span data-ttu-id="a9252-116">Преобразование атрибутов в элементы</span><span class="sxs-lookup"><span data-stu-id="a9252-116">Transforming Attributes into Elements</span></span>  
 <span data-ttu-id="a9252-117">Для этого примера предположим, что требуется изменить следующий образец XML-документа, чтобы атрибуты стали элементами.</span><span class="sxs-lookup"><span data-stu-id="a9252-117">For this example, suppose you want to modify the following simple XML document so that the attributes become elements.</span></span> <span data-ttu-id="a9252-118">Сначала в этом разделе представлен обычный способ изменения на месте.</span><span class="sxs-lookup"><span data-stu-id="a9252-118">This topic first presents the traditional in-place modification approach.</span></span> <span data-ttu-id="a9252-119">Затем показан способ функционального построения.</span><span class="sxs-lookup"><span data-stu-id="a9252-119">It then shows the functional construction approach.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Root Data1="123" Data2="456">  
  <Child1>Content</Child1>  
</Root>  
```  
  
### <a name="modifying-the-xml-tree"></a><span data-ttu-id="a9252-120">Изменение XML-дерева</span><span class="sxs-lookup"><span data-stu-id="a9252-120">Modifying the XML Tree</span></span>  
 <span data-ttu-id="a9252-121">Можно написать процедурный код, чтобы создать элементы из атрибутов, а затем удалить атрибуты. Вот как это делается:</span><span class="sxs-lookup"><span data-stu-id="a9252-121">You can write some procedural code to create elements from the attributes, and then delete the attributes, as follows:</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
For Each att As XAttribute In root.Attributes()  
    root.Add(New XElement(att.Name, att.Value))  
Next  
root.Attributes().Remove()  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="a9252-122">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="a9252-122">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Content</Child1>  
  <Data1>123</Data1>  
  <Data2>456</Data2>  
</Root>  
```  
  
### <a name="functional-construction-approach"></a><span data-ttu-id="a9252-123">Подход на основе функционального построения</span><span class="sxs-lookup"><span data-stu-id="a9252-123">Functional Construction Approach</span></span>  
 <span data-ttu-id="a9252-124">В отличие от этого, функциональный подход основан на применении кода, предназначенного для формирования нового дерева, выбора и извлечения элементов и атрибутов из исходного дерева и их соответствующего преобразования по мере добавления в новое дерево.</span><span class="sxs-lookup"><span data-stu-id="a9252-124">By contrast, a functional approach consists of code to form a new tree, picking and choosing elements and attributes from the source tree, and transforming them as appropriate as they are added to the new tree.</span></span> <span data-ttu-id="a9252-125">Пример функционального подхода выглядит примерно так:</span><span class="sxs-lookup"><span data-stu-id="a9252-125">The functional approach looks like the following:</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim newTree As XElement = _  
    <Root>  
        <%= root.<Child1> %>  
        <%= From att In root.Attributes() _  
            Select New XElement(att.Name, att.Value) %>  
    </Root>  
Console.WriteLine(newTree)  
```  
  
 <span data-ttu-id="a9252-126">В этом примере формируется такой же итоговый XML-документ, как и в первом примере.</span><span class="sxs-lookup"><span data-stu-id="a9252-126">This example outputs the same XML as the first example.</span></span> <span data-ttu-id="a9252-127">Но обратите внимание, что при функциональном подходе можно видеть итоговую структуру нового XML-документа.</span><span class="sxs-lookup"><span data-stu-id="a9252-127">However, notice that you can actually see the resulting structure of the new XML in the functional approach.</span></span> <span data-ttu-id="a9252-128">Можно видеть создание элемента `Root`, код, который получает по запросу элемент `Child1` из исходного дерева, а также код, который преобразует атрибуты из исходного дерева в элементы в новом дереве.</span><span class="sxs-lookup"><span data-stu-id="a9252-128">You can see the creation of the `Root` element, the code that pulls the `Child1` element from the source tree, and the code that transforms the attributes from the source tree to elements in the new tree.</span></span>  
  
 <span data-ttu-id="a9252-129">В этом случае функциональный код вряд ли будет короче, чем код из первого примера, и совсем не проще.</span><span class="sxs-lookup"><span data-stu-id="a9252-129">The functional example in this case is not any shorter than the first example, and it is not really any simpler.</span></span> <span data-ttu-id="a9252-130">Но если в XML-дерево требуется внести много изменений, то подход, отличный от функционального, может стать довольно сложным и громоздким.</span><span class="sxs-lookup"><span data-stu-id="a9252-130">However, if you have many changes to make to an XML tree, the non functional approach will become quite complex and somewhat obtuse.</span></span> <span data-ttu-id="a9252-131">В отличие от этого, при использовании функционального подхода происходит просто формирование требуемого XML-документа, когда соответствующие запросы и выражения встраиваются, чтобы получать по запросу нужное содержимое.</span><span class="sxs-lookup"><span data-stu-id="a9252-131">In contrast, when using the functional approach, you still just form the desired XML, embedding queries and expressions as appropriate, to pull in the desired content.</span></span> <span data-ttu-id="a9252-132">При функциональном подходе получается код, более простой в сопровождении.</span><span class="sxs-lookup"><span data-stu-id="a9252-132">The functional approach yields code that is easier to maintain.</span></span>  
  
 <span data-ttu-id="a9252-133">Обратите внимание, что в этом случае функциональный подход, вероятно, обеспечит более низкую производительность в сравнении с внесением изменений в дерево.</span><span class="sxs-lookup"><span data-stu-id="a9252-133">Notice that in this case the functional approach probably would not perform quite as well as the tree manipulation approach.</span></span> <span data-ttu-id="a9252-134">Основная проблема заключается в том, что при функциональном подходе создается больше объектов, существующих в течение непродолжительного времени.</span><span class="sxs-lookup"><span data-stu-id="a9252-134">The main issue is that the functional approach creates more short lived objects.</span></span> <span data-ttu-id="a9252-135">Однако этим недостатком можно пренебречь, если использование функционального подхода позволяет повысить производительность работы программиста.</span><span class="sxs-lookup"><span data-stu-id="a9252-135">However, the tradeoff is an effective one if using the functional approach allows for greater programmer productivity.</span></span>  
  
 <span data-ttu-id="a9252-136">Это очень простой пример, однако он хорошо иллюстрирует различие в основах этих двух подходов.</span><span class="sxs-lookup"><span data-stu-id="a9252-136">This is a very simple example, but it serves to show the difference in philosophy between the two approaches.</span></span> <span data-ttu-id="a9252-137">Функциональный подход обеспечивает большую производительность при преобразовании больших XML-документов.</span><span class="sxs-lookup"><span data-stu-id="a9252-137">The functional approach yields greater productivity gains for transforming larger XML documents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9252-138">См. также</span><span class="sxs-lookup"><span data-stu-id="a9252-138">See also</span></span>

- [<span data-ttu-id="a9252-139">Изменение деревьев XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9252-139">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
