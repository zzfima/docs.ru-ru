---
title: LINQ to XML и DOM
ms.date: 07/20/2015
ms.assetid: 18c36130-d598-40b7-9007-828232252978
ms.openlocfilehash: b25993fba4d878beb881dfdc46effe5a8ab3485b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331706"
---
# <a name="linq-to-xml-vs-dom-visual-basic"></a><span data-ttu-id="1277e-102">LINQ to XML vs. DOM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1277e-102">LINQ to XML vs. DOM (Visual Basic)</span></span>
<span data-ttu-id="1277e-103">В этом разделе описываются некоторые основные различия между [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] и текущим преобладающим программным интерфейсом API XML, а именно моделью DOM консорциума W3C.</span><span class="sxs-lookup"><span data-stu-id="1277e-103">This section describes some key differences between [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] and the current predominant XML programming API, the W3C Document Object Model (DOM).</span></span>  
  
## <a name="new-ways-to-construct-xml-trees"></a><span data-ttu-id="1277e-104">Новые способы построения XML-деревьев</span><span class="sxs-lookup"><span data-stu-id="1277e-104">New Ways to Construct XML Trees</span></span>  
 <span data-ttu-id="1277e-105">В W3C DOM XML-дерево строится снизу вверх, т. е. создается документ, создаются элементы, а затем элементы добавляются в документ.</span><span class="sxs-lookup"><span data-stu-id="1277e-105">In the W3C DOM, you build an XML tree from the bottom up; that is, you create a document, you create elements, and then you add the elements to the document.</span></span>  
  
 <span data-ttu-id="1277e-106">В качестве примера ниже показан типичный способ создания XML-дерева при помощи реализации DOM от Майкрософт, <xref:System.Xml.XmlDocument>:</span><span class="sxs-lookup"><span data-stu-id="1277e-106">For example, the following would be a typical way to create an XML tree using the Microsoft implementation of DOM, <xref:System.Xml.XmlDocument>:</span></span>  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
Dim phone1 As XmlElement = doc.CreateElement("Phone")  
phone1.SetAttribute("Type", "Home")  
phone1.InnerText = "206-555-0144"  
Dim phone2 As XmlElement = doc.CreateElement("Phone")  
phone2.SetAttribute("Type", "Work")  
phone2.InnerText = "425-555-0145"  
Dim street1 As XmlElement = doc.CreateElement("Street1")  
street1.InnerText = "123 Main St"  
Dim city As XmlElement = doc.CreateElement("City")  
city.InnerText = "Mercer Island"  
Dim state As XmlElement = doc.CreateElement("State")  
state.InnerText = "WA"  
Dim postal As XmlElement = doc.CreateElement("Postal")  
postal.InnerText = "68042"  
Dim address As XmlElement = doc.CreateElement("Address")  
address.AppendChild(street1)  
address.AppendChild(city)  
address.AppendChild(state)  
address.AppendChild(postal)  
Dim contact As XmlElement = doc.CreateElement("Contact")  
contact.AppendChild(name)  
contact.AppendChild(phone1)  
contact.AppendChild(phone2)  
contact.AppendChild(address)  
Dim contacts As XmlElement = doc.CreateElement("Contacts")  
contacts.AppendChild(contact)  
doc.AppendChild(contacts)  
Console.WriteLine(doc.OuterXml)  
```  
  
 <span data-ttu-id="1277e-107">Такой стиль программирования не дает визуального представления о деталях структуры XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="1277e-107">This style of coding does not visually provide much information about the structure of the XML tree.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="1277e-108">поддерживает такой подход к построению XML-дерева, но также предлагает и альтернативный способ, *функциональное построение*.</span><span class="sxs-lookup"><span data-stu-id="1277e-108">supports this approach to constructing an XML tree, but also supports an alternative approach, *functional construction*.</span></span> <span data-ttu-id="1277e-109">In Visual Basic, functional construction uses XML literals to build an XML tree.</span><span class="sxs-lookup"><span data-stu-id="1277e-109">In Visual Basic, functional construction uses XML literals to build an XML tree.</span></span>  
  
 <span data-ttu-id="1277e-110">Вот как можно построить такое же XML-дерево с помощью функционального построения [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1277e-110">Here is how you would construct the same XML tree by using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] functional construction:</span></span>  
  
```vb  
Dim contacts = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="Home">206-555-0144</Phone>  
            <Phone Type="Work">425-555-0145</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 <span data-ttu-id="1277e-111">Обратите внимание, что отступы в коде, который строит XML-дерево, показывают структуру базового документа XML.</span><span class="sxs-lookup"><span data-stu-id="1277e-111">Notice that indenting the code to construct the XML tree shows the structure of the underlying XML.</span></span>  
  
 <span data-ttu-id="1277e-112">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="1277e-112">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="working-directly-with-xml-elements"></a><span data-ttu-id="1277e-113">Работа непосредственно с XML-элементами</span><span class="sxs-lookup"><span data-stu-id="1277e-113">Working Directly with XML Elements</span></span>  
 <span data-ttu-id="1277e-114">При программировании на XML основное внимание обычно уделяется XML-элементам и, возможно, атрибутам.</span><span class="sxs-lookup"><span data-stu-id="1277e-114">When you program with XML, your primary focus is usually on XML elements and perhaps on attributes.</span></span> <span data-ttu-id="1277e-115">В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] можно работать с XML-элементами и атрибутами напрямую.</span><span class="sxs-lookup"><span data-stu-id="1277e-115">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can work directly with XML elements and attributes.</span></span> <span data-ttu-id="1277e-116">Например, можно выполнять следующие действия.</span><span class="sxs-lookup"><span data-stu-id="1277e-116">For example, you can do the following:</span></span>  
  
- <span data-ttu-id="1277e-117">Создавать XML-элементы, совсем не используя объект документа.</span><span class="sxs-lookup"><span data-stu-id="1277e-117">Create XML elements without using a document object at all.</span></span> <span data-ttu-id="1277e-118">Это упрощает программирование, когда необходимо работать с фрагментами XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="1277e-118">This simplifies programming when you have to work with fragments of XML trees.</span></span>  
  
- <span data-ttu-id="1277e-119">Загружать объекты `T:System.Xml.Linq.XElement` непосредственно из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="1277e-119">Load `T:System.Xml.Linq.XElement` objects directly from an XML file.</span></span>  
  
- <span data-ttu-id="1277e-120">Сериализовать объекты `T:System.Xml.Linq.XElement` в файл или поток.</span><span class="sxs-lookup"><span data-stu-id="1277e-120">Serialize `T:System.Xml.Linq.XElement` objects to a file or a stream.</span></span>  
  
 <span data-ttu-id="1277e-121">Сравним это с W3C DOM, где XML-документ используется как логический контейнер для XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="1277e-121">Compare this to the W3C DOM, in which the XML document is used as a logical container for the XML tree.</span></span> <span data-ttu-id="1277e-122">В DOM XML-узлы, в том числе элементы и атрибуты, должны создаваться в контексте XML-документа.</span><span class="sxs-lookup"><span data-stu-id="1277e-122">In DOM, XML nodes, including elements and attributes, must be created in the context of an XML document.</span></span> <span data-ttu-id="1277e-123">Вот фрагмент кода, предназначенного для создания элемента имени в DOM:</span><span class="sxs-lookup"><span data-stu-id="1277e-123">Here is a fragment of the code to create a name element in DOM:</span></span>  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
doc.AppendChild(name)  
```  
  
 <span data-ttu-id="1277e-124">Если элемент требуется использовать в нескольких документах, нужно будет импортировать в эти документы узлы.</span><span class="sxs-lookup"><span data-stu-id="1277e-124">If you want to use an element across multiple documents, you must import the nodes across documents.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="1277e-125">позволяет избавиться от этих сложностей.</span><span class="sxs-lookup"><span data-stu-id="1277e-125">avoids this layer of complexity.</span></span>  
  
 <span data-ttu-id="1277e-126">При использовании LINQ to XML класс <xref:System.Xml.Linq.XDocument> применяется только, если требуется добавить комментарий или инструкцию по обработке на корневом уровне документа.</span><span class="sxs-lookup"><span data-stu-id="1277e-126">When using LINQ to XML, you use the <xref:System.Xml.Linq.XDocument> class only if you want to add a comment or processing instruction at the root level of the document.</span></span>  
  
## <a name="simplified-handling-of-names-and-namespaces"></a><span data-ttu-id="1277e-127">Упрощенная обработка имен и пространств имен</span><span class="sxs-lookup"><span data-stu-id="1277e-127">Simplified Handling of Names and Namespaces</span></span>  
 <span data-ttu-id="1277e-128">В общем случае обработка имен, пространств имен и префиксов пространств имен является сложной частью в программировании на XML.</span><span class="sxs-lookup"><span data-stu-id="1277e-128">Handling names, namespaces, and namespace prefixes is generally a complex part of XML programming.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="1277e-129">упрощает работу с ними, исключая необходимость использования полных префиксов пространств имен.</span><span class="sxs-lookup"><span data-stu-id="1277e-129">simplifies names and namespaces by eliminating the requirement to deal with namespace prefixes.</span></span> <span data-ttu-id="1277e-130">Их можно использовать, если требуется управлять префиксами пространств имен.</span><span class="sxs-lookup"><span data-stu-id="1277e-130">If you want to control namespace prefixes, you can.</span></span> <span data-ttu-id="1277e-131">Однако, если принято решение явно не управлять префиксами пространств имен, то при сериализации [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] назначит префиксы пространств имен, если они необходимы, или, в противном случае, произведет сериализацию при помощи пространств имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1277e-131">But if you decide to not explicitly control namespace prefixes, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] will assign namespace prefixes during serialization if they are required, or will serialize using default namespaces if they are not.</span></span> <span data-ttu-id="1277e-132">Если используются пространства имен по умолчанию, то в итоговом документе префиксов пространств имен не будет.</span><span class="sxs-lookup"><span data-stu-id="1277e-132">If default namespaces are used, there will be no namespace prefixes in the resulting document.</span></span> <span data-ttu-id="1277e-133">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1277e-133">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="1277e-134">Еще одним недостатком DOM является то, что отсутствует возможность изменять имена узлов.</span><span class="sxs-lookup"><span data-stu-id="1277e-134">Another problem with the DOM is that it does not let you change the name of a node.</span></span> <span data-ttu-id="1277e-135">Вместо этого необходимо создать новый узел и скопировать в него все дочерние узлы, но при этом идентификатор первоначального узла будет потерян.</span><span class="sxs-lookup"><span data-stu-id="1277e-135">Instead, you have to create a new node and copy all the child nodes to it, losing the original node identity.</span></span> <span data-ttu-id="1277e-136">В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] эта проблема решена за счет возможности установки свойства <xref:System.Xml.Linq.XName> узла.</span><span class="sxs-lookup"><span data-stu-id="1277e-136">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] avoids this problem by enabling you to set the <xref:System.Xml.Linq.XName> property on a node.</span></span>  
  
## <a name="static-method-support-for-loading-xml"></a><span data-ttu-id="1277e-137">Поддержка статических методов для загрузки XML</span><span class="sxs-lookup"><span data-stu-id="1277e-137">Static Method Support for Loading XML</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="1277e-138">позволяет загружать XML при помощи статических методов, а не методов экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1277e-138">lets you load XML by using static methods, instead of instance methods.</span></span> <span data-ttu-id="1277e-139">Это упрощает загрузку и синтаксический анализ.</span><span class="sxs-lookup"><span data-stu-id="1277e-139">This simplifies loading and parsing.</span></span> <span data-ttu-id="1277e-140">For more information, see [How to: Load XML from a File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md).</span><span class="sxs-lookup"><span data-stu-id="1277e-140">For more information, see [How to: Load XML from a File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md).</span></span>  
  
## <a name="removal-of-support-for-dtd-constructs"></a><span data-ttu-id="1277e-141">Удаление поддержки конструкций DTD</span><span class="sxs-lookup"><span data-stu-id="1277e-141">Removal of Support for DTD Constructs</span></span>  
 <span data-ttu-id="1277e-142">За счет удаления поддержки сущностей и ссылок на сущности [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] еще более упрощает программирование на XML.</span><span class="sxs-lookup"><span data-stu-id="1277e-142">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] further simplifies XML programming by removing support for entities and entity references.</span></span> <span data-ttu-id="1277e-143">Управление сущностями является весьма сложным процессом и поэтому редко используется.</span><span class="sxs-lookup"><span data-stu-id="1277e-143">The management of entities is complex, and is rarely used.</span></span> <span data-ttu-id="1277e-144">Удаление поддержки сущностей позволяет повысить производительность и упростить интерфейс программирования.</span><span class="sxs-lookup"><span data-stu-id="1277e-144">Removing their support increases performance and simplifies the programming interface.</span></span> <span data-ttu-id="1277e-145">При заполнении дерева [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] все сущности DTD раскрываются.</span><span class="sxs-lookup"><span data-stu-id="1277e-145">When a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] tree is populated, all DTD entities are expanded.</span></span>  
  
## <a name="support-for-fragments"></a><span data-ttu-id="1277e-146">Поддержка фрагментов</span><span class="sxs-lookup"><span data-stu-id="1277e-146">Support for Fragments</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="1277e-147">не предоставляет эквивалент класса `XmlDocumentFragment`.</span><span class="sxs-lookup"><span data-stu-id="1277e-147">does not provide an equivalent for the `XmlDocumentFragment` class.</span></span> <span data-ttu-id="1277e-148">Однако во многих случаях понятие `XmlDocumentFragment` можно обрабатывать с помощью результата запроса, который типизируется как объект <xref:System.Collections.Generic.IEnumerable%601> объекта <xref:System.Xml.Linq.XNode> или объект <xref:System.Collections.Generic.IEnumerable%601> объекта <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="1277e-148">In many cases, however, the `XmlDocumentFragment` concept can be handled by the result of a query that is typed as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XNode>, or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="support-for-xpathnavigator"></a><span data-ttu-id="1277e-149">Поддержка XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="1277e-149">Support for XPathNavigator</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="1277e-150">обеспечивает поддержку <xref:System.Xml.XPath.XPathNavigator> через методы расширения в пространстве имен <xref:System.Xml.XPath?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1277e-150">provides support for <xref:System.Xml.XPath.XPathNavigator> through extension methods in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="1277e-151">Для получения дополнительной информации см. <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1277e-151">For more information, see <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.</span></span>  
  
## <a name="support-for-white-space-and-indentation"></a><span data-ttu-id="1277e-152">Поддержка пробелов и отступов</span><span class="sxs-lookup"><span data-stu-id="1277e-152">Support for White Space and Indentation</span></span>  
 <span data-ttu-id="1277e-153">Обработка пробелов в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] проще, чем в DOM.</span><span class="sxs-lookup"><span data-stu-id="1277e-153">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] handles white space more simply than the DOM.</span></span>  
  
 <span data-ttu-id="1277e-154">Типичный сценарий состоит в чтении XML с отступами, создании XML-дерева в памяти без текстовых узлов с пробелами (то есть без сохранения пробелов), выполнении определенных операций над XML и сохранении XML с отступами.</span><span class="sxs-lookup"><span data-stu-id="1277e-154">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="1277e-155">При сериализации XML с форматированием сохраняются только значимые пробелы XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="1277e-155">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="1277e-156">Это поведение [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1277e-156">This is the default behavior for [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="1277e-157">Другой типичный сценарий заключается в чтении и изменении XML с уже существующими преднамеренными отступами.</span><span class="sxs-lookup"><span data-stu-id="1277e-157">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="1277e-158">Эти отступы ни в коем случае изменять нельзя.</span><span class="sxs-lookup"><span data-stu-id="1277e-158">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="1277e-159">В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] этого можно достигнуть, если сохранить пробелы при загрузке или синтаксическом анализе XML и отключить форматирование при сериализации XML.</span><span class="sxs-lookup"><span data-stu-id="1277e-159">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can do this by preserving white space when you load or parse the XML and disabling formatting when you serialize the XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="1277e-160">хранит пробелы как узлы <xref:System.Xml.Linq.XText>, а не имеет сериализованный тип узла <xref:System.Xml.XmlNodeType.Whitespace>, который есть в DOM.</span><span class="sxs-lookup"><span data-stu-id="1277e-160">stores white space as an <xref:System.Xml.Linq.XText> node, instead of having a specialized <xref:System.Xml.XmlNodeType.Whitespace> node type, as the DOM does.</span></span>  
  
## <a name="support-for-annotations"></a><span data-ttu-id="1277e-161">Поддержка заметок</span><span class="sxs-lookup"><span data-stu-id="1277e-161">Support for Annotations</span></span>  
 <span data-ttu-id="1277e-162">Элементы [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] поддерживают расширяемый набор заметок.</span><span class="sxs-lookup"><span data-stu-id="1277e-162">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] elements support an extensible set of annotations.</span></span> <span data-ttu-id="1277e-163">Это полезно для отслеживания различной информации об элементе, например сведений о схеме, сведений о привязке элемента к пользовательскому интерфейсу, а также любых других сведений, относящихся к конкретному приложению.</span><span class="sxs-lookup"><span data-stu-id="1277e-163">This is useful for tracking miscellaneous information about an element, such as schema information, information about whether the element is bound to a UI, or any other kind of application-specific information.</span></span> <span data-ttu-id="1277e-164">Дополнительные сведения см. в разделе [Заметки LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-annotations.md).</span><span class="sxs-lookup"><span data-stu-id="1277e-164">For more information, see [LINQ to XML Annotations](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-annotations.md).</span></span>  
  
## <a name="support-for-schema-information"></a><span data-ttu-id="1277e-165">Поддержка сведений схемы</span><span class="sxs-lookup"><span data-stu-id="1277e-165">Support for Schema Information</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="1277e-166">обеспечивает поддержку проверки правильности по схеме XSD через методы расширения в пространстве имен <xref:System.Xml.Schema?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1277e-166">provides support for XSD validation through extension methods in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="1277e-167">Можно проверить XML-дерево на соответствие схеме XSD.</span><span class="sxs-lookup"><span data-stu-id="1277e-167">You can validate that an XML tree complies with an XSD.</span></span> <span data-ttu-id="1277e-168">XML-дерево можно заполнить при помощи модуля проверки после обработки схемы (PSVI).</span><span class="sxs-lookup"><span data-stu-id="1277e-168">You can populate the XML tree with the post-schema-validation infoset (PSVI).</span></span> <span data-ttu-id="1277e-169">Дополнительные сведения см. в разделах [Практическое руководство. Проверка XSD с использованием XSD](../../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) и <xref:System.Xml.Schema.Extensions>.</span><span class="sxs-lookup"><span data-stu-id="1277e-169">For more information, see [How to: Validate Using XSD](../../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) and <xref:System.Xml.Schema.Extensions>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1277e-170">См. также</span><span class="sxs-lookup"><span data-stu-id="1277e-170">See also</span></span>

- [<span data-ttu-id="1277e-171">Начало работы (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1277e-171">Getting Started (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
