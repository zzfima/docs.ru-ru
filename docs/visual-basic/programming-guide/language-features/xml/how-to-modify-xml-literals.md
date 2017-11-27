---
title: "Практическое руководство. Изменение XML-литералов (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdc60542477d15f4fe9dd85dae4c9a918e695740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="20fcb-102">Практическое руководство. Изменение XML-литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20fcb-102">How to: Modify XML Literals (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="20fcb-103">предоставляет удобный способ изменения XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="20fcb-103"> provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="20fcb-104">Можно добавить или удалить элементы и атрибуты, и также можно заменить существующий элемент новым элементом XML.</span><span class="sxs-lookup"><span data-stu-id="20fcb-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="20fcb-105">Здесь приведены несколько примеров того, как изменить существующий XML-литерала.</span><span class="sxs-lookup"><span data-stu-id="20fcb-105">This topic provides several examples of how to modify an existing XML literal.</span></span>  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="20fcb-106">Чтобы изменить значение XML-литерала</span><span class="sxs-lookup"><span data-stu-id="20fcb-106">To modify the value of an XML literal</span></span>  
  
1.  <span data-ttu-id="20fcb-107">Чтобы изменить значение XML-литерала, получите ссылку на XML-литерал и задайте `Value` свойство нужное значение.</span><span class="sxs-lookup"><span data-stu-id="20fcb-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>  
  
     <span data-ttu-id="20fcb-108">В следующем примере кода показано, как значение всех \<цена > элементов в XML-документа.</span><span class="sxs-lookup"><span data-stu-id="20fcb-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>  
  
     [!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]  
  
     <span data-ttu-id="20fcb-109">Ниже показан образец XML-источника и изменение XML из этого примера кода.</span><span class="sxs-lookup"><span data-stu-id="20fcb-109">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
    >  <span data-ttu-id="20fcb-110">`Value` Свойство ссылается на первый XML-элемент в коллекции.</span><span class="sxs-lookup"><span data-stu-id="20fcb-110">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="20fcb-111">Если имеется более одного элемента с тем же именем в коллекцию, задание `Value` свойство влияет только на первый элемент в коллекции.</span><span class="sxs-lookup"><span data-stu-id="20fcb-111">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="20fcb-112">Чтобы добавить атрибут в XML-литерала</span><span class="sxs-lookup"><span data-stu-id="20fcb-112">To add an attribute to an XML literal</span></span>  
  
1.  <span data-ttu-id="20fcb-113">Чтобы добавить атрибут в XML-литерал, сначала получите ссылку на XML-литерал.</span><span class="sxs-lookup"><span data-stu-id="20fcb-113">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="20fcb-114">Затем можно добавить атрибут, добавив новое свойство оси атрибута XML.</span><span class="sxs-lookup"><span data-stu-id="20fcb-114">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="20fcb-115">Также можно добавить новый <xref:System.Xml.Linq.XAttribute> объекта для XML-литерала с помощью <xref:System.Xml.Linq.XContainer.Add%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="20fcb-115">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="20fcb-116">В следующем примере показано, как параметры.</span><span class="sxs-lookup"><span data-stu-id="20fcb-116">The following example shows both options.</span></span>  
  
     [!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]  
  
     <span data-ttu-id="20fcb-117">Ниже показан образец XML-источника и изменение XML из этого примера кода.</span><span class="sxs-lookup"><span data-stu-id="20fcb-117">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
  
     <span data-ttu-id="20fcb-118">Дополнительные сведения о свойствах атрибутов оси XML см. в разделе [свойство оси атрибута XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="20fcb-118">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>  
  
### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="20fcb-119">Чтобы добавить элемент в XML-литерала</span><span class="sxs-lookup"><span data-stu-id="20fcb-119">To add an element to an XML literal</span></span>  
  
1.  <span data-ttu-id="20fcb-120">Чтобы добавить элемент в XML-литерал, сначала получите ссылку на XML-литерал.</span><span class="sxs-lookup"><span data-stu-id="20fcb-120">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="20fcb-121">Затем можно добавить новый <xref:System.Xml.Linq.XElement> объектов как последний дочерний элемент элемента с помощью <xref:System.Xml.Linq.XContainer.Add%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="20fcb-121">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="20fcb-122">Можно добавить новый <xref:System.Xml.Linq.XElement> объект как первый дочерний элемент с помощью <xref:System.Xml.Linq.XContainer.AddFirst%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="20fcb-122">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>  
  
     <span data-ttu-id="20fcb-123">Чтобы добавить новый элемент в определенное место относительно других вложенных элементов, сначала получите ссылку на смежные вложенный элемент.</span><span class="sxs-lookup"><span data-stu-id="20fcb-123">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="20fcb-124">Затем можно добавить новый <xref:System.Xml.Linq.XElement> объекта перед соседними вложенными элементами с помощью <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="20fcb-124">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="20fcb-125">Также можно добавить новый <xref:System.Xml.Linq.XElement> объекта после соседними вложенными элементами с помощью <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="20fcb-125">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>  
  
     <span data-ttu-id="20fcb-126">В следующем примере показано примеры каждого из этих методов.</span><span class="sxs-lookup"><span data-stu-id="20fcb-126">The following example shows examples of each of these techniques.</span></span>  
  
     [!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]  
  
     <span data-ttu-id="20fcb-127">Ниже показан образец XML-источника и изменение XML из этого примера кода.</span><span class="sxs-lookup"><span data-stu-id="20fcb-127">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="20fcb-128">Чтобы удалить элемент или атрибут из XML-литерала</span><span class="sxs-lookup"><span data-stu-id="20fcb-128">To remove an element or attribute from an XML literal</span></span>  
  
1.  <span data-ttu-id="20fcb-129">Чтобы удалить элемент или атрибут из XML-литерала, получите ссылку на элемент или атрибут и вызовите `Remove` метода, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="20fcb-129">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>  
  
     [!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]  
  
     <span data-ttu-id="20fcb-130">Ниже показан образец XML-источника и изменение XML из этого примера кода.</span><span class="sxs-lookup"><span data-stu-id="20fcb-130">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
  
     <span data-ttu-id="20fcb-131">Чтобы удалить все элементы или атрибуты из XML-литерала, получите ссылку на XML-литерал и вызовите <xref:System.Xml.Linq.XElement.RemoveAll%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="20fcb-131">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>  
  
### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="20fcb-132">Для изменения XML-литерала</span><span class="sxs-lookup"><span data-stu-id="20fcb-132">To modify an XML literal</span></span>  
  
1.  <span data-ttu-id="20fcb-133">Чтобы изменить имя элемента XML, необходимо сначала получите ссылку на элемент.</span><span class="sxs-lookup"><span data-stu-id="20fcb-133">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="20fcb-134">Затем можно создать новый <xref:System.Xml.Linq.XElement> объект, имеющий новое имя и передать этот <xref:System.Xml.Linq.XElement> объект <xref:System.Xml.Linq.XNode.ReplaceWith%2A> метод существующего <xref:System.Xml.Linq.XElement> объекта.</span><span class="sxs-lookup"><span data-stu-id="20fcb-134">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="20fcb-135">Если элемент, который вы заменяете имеет вложенные элементы, которые должны быть сохранены, задайте значение нового <xref:System.Xml.Linq.XElement> объект <xref:System.Xml.Linq.XContainer.Nodes%2A> свойства существующего элемента.</span><span class="sxs-lookup"><span data-stu-id="20fcb-135">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="20fcb-136">Это будет присвоено значение нового элемента внутренний XML существующего элемента.</span><span class="sxs-lookup"><span data-stu-id="20fcb-136">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="20fcb-137">В противном случае можно задать значение в новом элементе `Value` свойства существующего элемента.</span><span class="sxs-lookup"><span data-stu-id="20fcb-137">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>  
  
     <span data-ttu-id="20fcb-138">В следующем примере кода заменяет все \<описание > элементы с \<абстрактный > элемент.</span><span class="sxs-lookup"><span data-stu-id="20fcb-138">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="20fcb-139">Содержимое \<описание > элемент сохраняется в новом \<абстрактный > элемента с помощью <xref:System.Xml.Linq.XContainer.Nodes%2A> свойство \<описание > <xref:System.Xml.Linq.XElement> объекта.</span><span class="sxs-lookup"><span data-stu-id="20fcb-139">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     [!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]  
  
     <span data-ttu-id="20fcb-140">Ниже показан образец XML-источника и изменение XML из этого примера кода.</span><span class="sxs-lookup"><span data-stu-id="20fcb-140">The following shows sample source XML and modified XML from this code example.</span></span>  
  
    ```  
    Source XML:  
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
  
    Modified XML:  
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
  
## <a name="see-also"></a><span data-ttu-id="20fcb-141">См. также</span><span class="sxs-lookup"><span data-stu-id="20fcb-141">See Also</span></span>  
 [<span data-ttu-id="20fcb-142">Работа с XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20fcb-142">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 [<span data-ttu-id="20fcb-143">XML</span><span class="sxs-lookup"><span data-stu-id="20fcb-143">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="20fcb-144">Практическое руководство. Загрузка XML-кода из файла, строки или потока</span><span class="sxs-lookup"><span data-stu-id="20fcb-144">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 [<span data-ttu-id="20fcb-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="20fcb-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="20fcb-146">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20fcb-146">[Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
