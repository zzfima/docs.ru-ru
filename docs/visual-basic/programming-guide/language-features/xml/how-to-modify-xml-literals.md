---
title: "Практическое руководство: изменение XML-литералов (Visual Basic) | Документы Microsoft"
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
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9c21ded9fdd8f49b469b9a712be304c0d4cabb8c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="0eebc-102">Практическое руководство. Изменение XML-литералов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0eebc-102">How to: Modify XML Literals (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="0eebc-103">предоставляет удобный способ изменения XML-литералов.</span><span class="sxs-lookup"><span data-stu-id="0eebc-103"> provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="0eebc-104">Можно добавить или удалить элементы и атрибуты, а также можно заменить существующий элемент новым элементом XML.</span><span class="sxs-lookup"><span data-stu-id="0eebc-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="0eebc-105">В этом разделе приведены несколько примеров того, как изменить существующий XML-литерал.</span><span class="sxs-lookup"><span data-stu-id="0eebc-105">This topic provides several examples of how to modify an existing XML literal.</span></span>  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="0eebc-106">Чтобы изменить значение XML-литерал</span><span class="sxs-lookup"><span data-stu-id="0eebc-106">To modify the value of an XML literal</span></span>  
  
1.  <span data-ttu-id="0eebc-107">Чтобы изменить значение XML-литерала, получите ссылку на XML-литерал и задайте `Value` нужное значение свойства.</span><span class="sxs-lookup"><span data-stu-id="0eebc-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>  
  
     <span data-ttu-id="0eebc-108">В следующем примере кода обновляется значение всех \<цена настроек элементов в XML-документ.</span><span class="sxs-lookup"><span data-stu-id="0eebc-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>  
  
     <span data-ttu-id="0eebc-109">[!code-vb[VbXmlSamples&#2;4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0eebc-109">[!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="0eebc-110">Ниже показан образец XML-источника и изменение XML из кода этого примера.</span><span class="sxs-lookup"><span data-stu-id="0eebc-110">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
    >  <span data-ttu-id="0eebc-111">`Value` Свойство ссылается на первый XML-элемент в коллекции.</span><span class="sxs-lookup"><span data-stu-id="0eebc-111">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="0eebc-112">Если имеется более одного элемента с тем же именем в коллекции, задание `Value` свойство влияет только на первый элемент в коллекции.</span><span class="sxs-lookup"><span data-stu-id="0eebc-112">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="0eebc-113">Чтобы добавить атрибут в XML-литерал</span><span class="sxs-lookup"><span data-stu-id="0eebc-113">To add an attribute to an XML literal</span></span>  
  
1.  <span data-ttu-id="0eebc-114">Чтобы добавить атрибут XML-литерал, сначала получите ссылку на XML-литерал.</span><span class="sxs-lookup"><span data-stu-id="0eebc-114">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="0eebc-115">Затем можно добавить атрибут, добавив новое свойство оси атрибута XML.</span><span class="sxs-lookup"><span data-stu-id="0eebc-115">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="0eebc-116">Можно также добавить новый <xref:System.Xml.Linq.XAttribute>объекта на XML-литерал с помощью <xref:System.Xml.Linq.XContainer.Add%2A>метод.</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="0eebc-116">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="0eebc-117">В следующем примере показано, как параметры.</span><span class="sxs-lookup"><span data-stu-id="0eebc-117">The following example shows both options.</span></span>  
  
     <span data-ttu-id="0eebc-118">[!code-vb[VbXmlSamples&#2;5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="0eebc-118">[!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="0eebc-119">Ниже показан образец XML-источника и изменение XML из кода этого примера.</span><span class="sxs-lookup"><span data-stu-id="0eebc-119">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
     <span data-ttu-id="0eebc-120">Дополнительные сведения о свойствах атрибутов оси XML см. в разделе [свойство оси атрибута XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="0eebc-120">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>  
  
### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="0eebc-121">Чтобы добавить элемент в XML-литерал</span><span class="sxs-lookup"><span data-stu-id="0eebc-121">To add an element to an XML literal</span></span>  
  
1.  <span data-ttu-id="0eebc-122">Чтобы добавить элемент в XML-литерал, сначала получите ссылку на XML-литерал.</span><span class="sxs-lookup"><span data-stu-id="0eebc-122">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="0eebc-123">Затем можно добавить новый <xref:System.Xml.Linq.XElement>объект как последний вложенный элемент элемента с помощью <xref:System.Xml.Linq.XContainer.Add%2A>метод.</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0eebc-123">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="0eebc-124">Можно добавить новый <xref:System.Xml.Linq.XElement>объект как первый дочерний элемент с помощью <xref:System.Xml.Linq.XContainer.AddFirst%2A>метод.</xref:System.Xml.Linq.XContainer.AddFirst%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0eebc-124">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>  
  
     <span data-ttu-id="0eebc-125">Чтобы добавить новый элемент в определенное место относительно других вложенных элементов, сначала получите ссылку на смежные вложенный элемент.</span><span class="sxs-lookup"><span data-stu-id="0eebc-125">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="0eebc-126">Затем можно добавить новую <xref:System.Xml.Linq.XElement>объекта перед соседними вложенными элементами с помощью <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>метод.</xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0eebc-126">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="0eebc-127">Можно также добавить новый <xref:System.Xml.Linq.XElement>объекта после соседними вложенными элементами с помощью <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>метод.</xref:System.Xml.Linq.XNode.AddAfterSelf%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0eebc-127">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>  
  
     <span data-ttu-id="0eebc-128">В следующем примере показано примеры всех этих методов.</span><span class="sxs-lookup"><span data-stu-id="0eebc-128">The following example shows examples of each of these techniques.</span></span>  
  
     <span data-ttu-id="0eebc-129">[!code-vb[VbXmlSamples2 №&6;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="0eebc-129">[!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]</span></span>  
  
     <span data-ttu-id="0eebc-130">Ниже показан образец XML-источника и изменение XML из кода этого примера.</span><span class="sxs-lookup"><span data-stu-id="0eebc-130">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="0eebc-131">Чтобы удалить элемент или атрибут из XML-литерал</span><span class="sxs-lookup"><span data-stu-id="0eebc-131">To remove an element or attribute from an XML literal</span></span>  
  
1.  <span data-ttu-id="0eebc-132">Чтобы удалить элемент или атрибут из XML-литерала, получите ссылку на элемент или атрибут и вызовите `Remove` метода, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="0eebc-132">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>  
  
     <span data-ttu-id="0eebc-133">[!code-vb[VbXmlSamples&#2;7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="0eebc-133">[!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]</span></span>  
  
     <span data-ttu-id="0eebc-134">Ниже показан образец XML-источника и изменение XML из кода этого примера.</span><span class="sxs-lookup"><span data-stu-id="0eebc-134">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
     <span data-ttu-id="0eebc-135">Чтобы удалить все элементы или атрибуты из XML-литерала, получите ссылку на XML-литерал и вызовите <xref:System.Xml.Linq.XElement.RemoveAll%2A>метод.</xref:System.Xml.Linq.XElement.RemoveAll%2A></span><span class="sxs-lookup"><span data-stu-id="0eebc-135">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>  
  
### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="0eebc-136">Изменение XML-литерал</span><span class="sxs-lookup"><span data-stu-id="0eebc-136">To modify an XML literal</span></span>  
  
1.  <span data-ttu-id="0eebc-137">Чтобы изменить имя XML-элемента, сначала получите ссылку на элемент.</span><span class="sxs-lookup"><span data-stu-id="0eebc-137">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="0eebc-138">Затем можно создать новый <xref:System.Xml.Linq.XElement>объект, имеющий новое имя и передать этот <xref:System.Xml.Linq.XElement>объект <xref:System.Xml.Linq.XNode.ReplaceWith%2A>существующий метод <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode.ReplaceWith%2A> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0eebc-138">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="0eebc-139">Если элемент, который вы заменяете имеет вложенные элементы, которые должны быть сохранены, задайте значение нового <xref:System.Xml.Linq.XElement>объекта <xref:System.Xml.Linq.XContainer.Nodes%2A>свойства существующего элемента.</xref:System.Xml.Linq.XContainer.Nodes%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0eebc-139">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="0eebc-140">Это установит значение нового элемента внутренний XML существующего элемента.</span><span class="sxs-lookup"><span data-stu-id="0eebc-140">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="0eebc-141">В противном случае, можно задать значение в новом элементе `Value` свойства существующего элемента.</span><span class="sxs-lookup"><span data-stu-id="0eebc-141">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>  
  
     <span data-ttu-id="0eebc-142">В следующем примере кода заменяет все \<описание настроек элементы с \<абстрактный настроек элемента.</span><span class="sxs-lookup"><span data-stu-id="0eebc-142">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="0eebc-143">Содержимое \<описание настроек элемент сохраняется в новом \<абстрактный настроек с помощью <xref:System.Xml.Linq.XContainer.Nodes%2A>свойство \<описание настроек <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Nodes%2A></span><span class="sxs-lookup"><span data-stu-id="0eebc-143">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="0eebc-144">[!code-vb[VbXmlSamples2 №&8;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="0eebc-144">[!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]</span></span>  
  
     <span data-ttu-id="0eebc-145">Ниже показан образец XML-источника и изменение XML из кода этого примера.</span><span class="sxs-lookup"><span data-stu-id="0eebc-145">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0eebc-146">См. также</span><span class="sxs-lookup"><span data-stu-id="0eebc-146">See Also</span></span>  
 <span data-ttu-id="0eebc-147">[Обработка XML в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="0eebc-147">[Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span></span>  
<span data-ttu-id="0eebc-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="0eebc-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="0eebc-149"> [Практическое руководство: загрузка XML из файла, строки или потока](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span><span class="sxs-lookup"><span data-stu-id="0eebc-149"> [How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span></span>  
<span data-ttu-id="0eebc-150"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="0eebc-150"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="0eebc-151"> [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="0eebc-151"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
