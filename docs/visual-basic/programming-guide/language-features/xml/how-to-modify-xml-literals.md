---
title: Практическое руководство. Изменение XML-литералов
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 99ec35addcb9fc8d886c9151cde87227b5113eb9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330859"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="e3306-102">Практическое руководство. Изменение XML-литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3306-102">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="e3306-103">Visual Basic предоставляет удобные способы изменения XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="e3306-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="e3306-104">Можно добавлять или удалять элементы и атрибуты. Кроме того, можно заменить существующий элемент новым XML-элементом.</span><span class="sxs-lookup"><span data-stu-id="e3306-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="e3306-105">В этом разделе приводится несколько примеров изменения существующего XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="e3306-105">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="e3306-106">Изменение значения XML-литерала</span><span class="sxs-lookup"><span data-stu-id="e3306-106">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="e3306-107">Чтобы изменить значение XML-литерала, получите ссылку на XML-литерал и задайте для свойства `Value` нужное значение.</span><span class="sxs-lookup"><span data-stu-id="e3306-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="e3306-108">В следующем примере кода обновляется значение всех элементов \<Price > в XML-документе.</span><span class="sxs-lookup"><span data-stu-id="e3306-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="e3306-109">Ниже приведен пример исходного XML и измененный XML-код из этого примера кода.</span><span class="sxs-lookup"><span data-stu-id="e3306-109">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="e3306-110">Исходный XML-код:</span><span class="sxs-lookup"><span data-stu-id="e3306-110">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="e3306-111">Измененный XML:</span><span class="sxs-lookup"><span data-stu-id="e3306-111">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>47.20</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>48.25</Price>
      </Book>
    </Catalog>
    ```

    > [!NOTE]
    > <span data-ttu-id="e3306-112">Свойство `Value` ссылается на первый элемент XML в коллекции.</span><span class="sxs-lookup"><span data-stu-id="e3306-112">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="e3306-113">Если в коллекции имеется несколько элементов с одинаковым именем, установка свойства `Value` влияет только на первый элемент в коллекции.</span><span class="sxs-lookup"><span data-stu-id="e3306-113">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="e3306-114">Добавление атрибута к XML-литералу</span><span class="sxs-lookup"><span data-stu-id="e3306-114">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="e3306-115">Чтобы добавить атрибут к XML-литералу, сначала получите ссылку на XML-литерал.</span><span class="sxs-lookup"><span data-stu-id="e3306-115">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="e3306-116">Затем можно добавить атрибут, добавив новое свойство оси атрибутов XML.</span><span class="sxs-lookup"><span data-stu-id="e3306-116">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="e3306-117">Можно также добавить новый объект <xref:System.Xml.Linq.XAttribute> в XML-литерал с помощью метода <xref:System.Xml.Linq.XContainer.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3306-117">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="e3306-118">В следующем примере показаны оба варианта.</span><span class="sxs-lookup"><span data-stu-id="e3306-118">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="e3306-119">Ниже приведен пример исходного XML и измененный XML-код из этого примера кода.</span><span class="sxs-lookup"><span data-stu-id="e3306-119">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="e3306-120">Исходный XML-код:</span><span class="sxs-lookup"><span data-stu-id="e3306-120">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="e3306-121">Измененный XML:</span><span class="sxs-lookup"><span data-stu-id="e3306-121">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="e3306-122">Дополнительные сведения о свойствах осей атрибутов XML см. в разделе [свойство оси атрибутов XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="e3306-122">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="e3306-123">Добавление элемента в XML-литерал</span><span class="sxs-lookup"><span data-stu-id="e3306-123">To add an element to an XML literal</span></span>

1. <span data-ttu-id="e3306-124">Чтобы добавить элемент в XML-литерал, сначала получите ссылку на XML-литерал.</span><span class="sxs-lookup"><span data-stu-id="e3306-124">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="e3306-125">Затем можно добавить новый объект <xref:System.Xml.Linq.XElement> как последний вложенный элемент элемента с помощью метода <xref:System.Xml.Linq.XContainer.Add%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3306-125">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="e3306-126">Новый объект <xref:System.Xml.Linq.XElement> можно добавить в качестве первого вложенного элемента с помощью метода <xref:System.Xml.Linq.XContainer.AddFirst%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3306-126">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="e3306-127">Чтобы добавить новый элемент в определенном месте относительно других вложенных элементов, сначала получите ссылку на смежный вложенный элемент.</span><span class="sxs-lookup"><span data-stu-id="e3306-127">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="e3306-128">Затем можно добавить новый объект <xref:System.Xml.Linq.XElement> перед соседним вложенным элементом с помощью метода <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3306-128">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="e3306-129">Можно также добавить новый объект <xref:System.Xml.Linq.XElement> после соседнего вложенного элемента с помощью метода <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3306-129">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="e3306-130">В следующем примере показаны примеры каждого из этих методов.</span><span class="sxs-lookup"><span data-stu-id="e3306-130">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="e3306-131">Ниже приведен пример исходного XML и измененный XML-код из этого примера кода.</span><span class="sxs-lookup"><span data-stu-id="e3306-131">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="e3306-132">Исходный XML-код:</span><span class="sxs-lookup"><span data-stu-id="e3306-132">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="e3306-133">Измененный XML:</span><span class="sxs-lookup"><span data-stu-id="e3306-133">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" >
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331">
        <Publisher>Microsoft Press</Publisher>
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <PublishDate>2005-2-14</PublishDate>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="e3306-134">Удаление элемента или атрибута из XML-литерала</span><span class="sxs-lookup"><span data-stu-id="e3306-134">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="e3306-135">Чтобы удалить элемент или атрибут из XML-литерала, получите ссылку на элемент или атрибут и вызовите метод `Remove`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e3306-135">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="e3306-136">Ниже приведен пример исходного XML и измененный XML-код из этого примера кода.</span><span class="sxs-lookup"><span data-stu-id="e3306-136">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="e3306-137">Исходный XML-код:</span><span class="sxs-lookup"><span data-stu-id="e3306-137">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book>
      <Book id="bk999"></Book>
    </Catalog>
    ```

    <span data-ttu-id="e3306-138">Измененный XML:</span><span class="sxs-lookup"><span data-stu-id="e3306-138">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101" editorEmail="someone@example.com">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
      </Book>
      <Book id="bk000"></Book>
      <Book id="bk331" editorEmail="someone@example.com">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
      </Book></Catalog>
    ```

    <span data-ttu-id="e3306-139">Чтобы удалить все элементы или атрибуты из XML-литерала, получите ссылку на XML-литерал и вызовите метод <xref:System.Xml.Linq.XElement.RemoveAll%2A>.</span><span class="sxs-lookup"><span data-stu-id="e3306-139">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="e3306-140">Изменение XML-литерала</span><span class="sxs-lookup"><span data-stu-id="e3306-140">To modify an XML literal</span></span>

1. <span data-ttu-id="e3306-141">Чтобы изменить имя XML-элемента, сначала получите ссылку на элемент.</span><span class="sxs-lookup"><span data-stu-id="e3306-141">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="e3306-142">Затем можно создать новый объект <xref:System.Xml.Linq.XElement> с новым именем и передать новый объект <xref:System.Xml.Linq.XElement> методу <xref:System.Xml.Linq.XNode.ReplaceWith%2A> существующего объекта <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="e3306-142">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="e3306-143">Если заменяемый элемент содержит вложенные элементы, которые должны быть сохранены, установите значение нового объекта <xref:System.Xml.Linq.XElement> в свойство <xref:System.Xml.Linq.XContainer.Nodes%2A> существующего элемента.</span><span class="sxs-lookup"><span data-stu-id="e3306-143">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="e3306-144">При этом значение нового элемента будет присвоено внутреннему XML существующего элемента.</span><span class="sxs-lookup"><span data-stu-id="e3306-144">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="e3306-145">В противном случае можно присвоить значение нового элемента свойству `Value` существующего элемента.</span><span class="sxs-lookup"><span data-stu-id="e3306-145">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="e3306-146">Следующий пример кода заменяет все \<Description > элементами \<абстрактный элемент >.</span><span class="sxs-lookup"><span data-stu-id="e3306-146">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="e3306-147">Содержимое элемента \<Description > сохраняется в новом \<абстрактном элементе > с помощью свойства <xref:System.Xml.Linq.XContainer.Nodes%2A> объекта \<Description > <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="e3306-147">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="e3306-148">Ниже приведен пример исходного XML и измененный XML-код из этого примера кода.</span><span class="sxs-lookup"><span data-stu-id="e3306-148">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="e3306-149">Исходный XML-код:</span><span class="sxs-lookup"><span data-stu-id="e3306-149">Source XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <Price>44.95</Price>
        <Description>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Description>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <Price>45.95</Price>
        <Description>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Description>
      </Book>
    </Catalog>
    ```

    <span data-ttu-id="e3306-150">Измененный XML:</span><span class="sxs-lookup"><span data-stu-id="e3306-150">Modified XML:</span></span>

    ```xml
    <?xml version="1.0"?>
    <Catalog>
      <Book id="bk101">
        <Author>Garghentini, Davide</Author>
        <Title>XML Developer's Guide</Title>
        <MSRP>44.95</MSRP>    <Abstract>
          An in-depth look at creating applications
          with <technology>XML</technology>. For
          <audience>beginners</audience> or
          <audience>advanced</audience> developers.
        </Abstract>
      </Book>
      <Book id="bk331">
        <Author>Spencer, Phil</Author>
        <Title>Developing Applications with Visual Basic .NET</Title>
        <MSRP>45.95</MSRP>    <Abstract>
          Get the expert insights, practical code samples, and best
          practices you need to advance your expertise with
          <technology>Visual Basic .NET</technology>.
          Learn how to create faster, more reliable applications
          based on professional, pragmatic guidance by today's top
          <audience>developers</audience>.
        </Abstract>
      </Book>
    </Catalog>
    ```

## <a name="see-also"></a><span data-ttu-id="e3306-151">См. также</span><span class="sxs-lookup"><span data-stu-id="e3306-151">See also</span></span>

- [<span data-ttu-id="e3306-152">Работа с XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e3306-152">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="e3306-153">XML</span><span class="sxs-lookup"><span data-stu-id="e3306-153">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="e3306-154">Практическое руководство. Загрузка XML-кода из файла, строки или потока</span><span class="sxs-lookup"><span data-stu-id="e3306-154">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="e3306-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="e3306-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- <span data-ttu-id="e3306-156">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3306-156">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
