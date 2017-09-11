---
title: "XML IntelliSense в Visual Basic | Документы Microsoft"
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
- Visual Basic code, XML
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: 59506ce9-d64e-417e-90fc-e9fe19f0a8fa
caps.latest.revision: 27
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
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 9a3c6f923bc9458997c388d4cf74ca113265a8cc
ms.contentlocale: ru-ru
ms.lasthandoff: 06/01/2017

---
# <a name="xml-intellisense-in-visual-basic"></a><span data-ttu-id="d262d-102">XML IntelliSense в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d262d-102">XML IntelliSense in Visual Basic</span></span>
<span data-ttu-id="d262d-103">Редактор кода Visual Basic включает функции IntelliSense для XML, обеспечивают завершение слов для элементов, определенных в схеме XML.</span><span class="sxs-lookup"><span data-stu-id="d262d-103">The Visual Basic Code Editor includes IntelliSense features for XML that provide word completion for elements defined in an XML schema.</span></span> <span data-ttu-id="d262d-104">Если включить в проект файл определения схемы XML (XSD) и импортировать целевое пространство имен схемы с помощью `Imports` инструкцию, редактор кода будет включать элементы из схемы XSD в списке IntelliSense допустимых переменных члена для <xref:System.Xml.Linq.XElement>и <xref:System.Xml.Linq.XDocument>объекты.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d262d-104">If you include an XML Schema Definition (XSD) file in your project and import the target namespace of the schema by using the `Imports` statement, the Code Editor will include elements from the XSD schema in the IntelliSense list of valid member variables for <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="d262d-105">На следующем рисунке показан список членов IntelliSense для <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d262d-105">The following illustration shows the IntelliSense members list for an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
 <span data-ttu-id="d262d-106">![XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")</span><span class="sxs-lookup"><span data-stu-id="d262d-106">![XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")</span></span>  
<span data-ttu-id="d262d-107">XML IntelliSense</span><span class="sxs-lookup"><span data-stu-id="d262d-107">XML IntelliSense</span></span>  
  
## <a name="enabling-xml-intellisense-in-visual-basic"></a><span data-ttu-id="d262d-108">Включение XML IntelliSense в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d262d-108">Enabling XML IntelliSense in Visual Basic</span></span>  
 <span data-ttu-id="d262d-109">Включение XML IntelliSense в Visual Basic, необходимо включить файла XSD-схемы в проекте Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d262d-109">To enable XML IntelliSense in Visual Basic, you must include an XSD schema file in your Visual Basic project.</span></span> <span data-ttu-id="d262d-110">Необходимо также импортировать целевое пространство имен для схемы XSD в файл кода с помощью `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="d262d-110">You must also import the target namespace for the XSD schema into your code file by using the `Imports` statement.</span></span> <span data-ttu-id="d262d-111">Кроме того, можно добавить целевое пространство имен в список имен уровня проекта с помощью **ссылки** страницы в конструкторе проектов Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d262d-111">Alternatively, you can add the target namespace to the project-level namespace list by using the **References** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="d262d-112">Примеры см. в разделе [Практическое руководство: Включение XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="d262d-112">For examples, see [How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span></span> <span data-ttu-id="d262d-113">Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) и [страница "ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d262d-113">For more information, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) and [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="d262d-114">Обратите внимание, что по умолчанию не могут видеть файлы схемы XSD в проектах Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d262d-114">Note that by default you cannot see XSD schema files in Visual Basic projects.</span></span> <span data-ttu-id="d262d-115">Нужно щелкнуть **Показать все файлы** кнопку, чтобы выбрать XSD-файл для включения в проект.</span><span class="sxs-lookup"><span data-stu-id="d262d-115">You may have to click the **Show All Files** button to select an XSD file to include in your project.</span></span>  
  
### <a name="generating-a-schema-file-schema-inference"></a><span data-ttu-id="d262d-116">Создание файла схемы (получение схемы)</span><span class="sxs-lookup"><span data-stu-id="d262d-116">Generating a Schema File (Schema Inference)</span></span>  
 <span data-ttu-id="d262d-117">Выводя XSD-схемы с помощью средств Visual Studio XML можно создать схему XSD для существующего файла XML.</span><span class="sxs-lookup"><span data-stu-id="d262d-117">You can create an XSD schema for an existing XML file by inferring the XSD schema by using Visual Studio XML tools.</span></span>  
  
-   <span data-ttu-id="d262d-118">Начиная с пакета обновления&1;, можно использовать XML для мастера схем для создания набор XML-схем, которая является производной от одного или нескольких XML-документов и включает их в проект.</span><span class="sxs-lookup"><span data-stu-id="d262d-118">Starting in SP1, you can use the XML to Schema Wizard to create an XML Schema set that is inferred from one or more XML documents and include it your project.</span></span> <span data-ttu-id="d262d-119">Можно использовать любую комбинацию XML-документов в виде текстовых файлов, XML из HTTP-адресов или XML, который объявляется и передается в XML для мастера схем.</span><span class="sxs-lookup"><span data-stu-id="d262d-119">You can use any combination of XML documents in the form of text files, XML from HTTP Internet addresses, or XML that is typed or pasted into the XML to Schema Wizard.</span></span> <span data-ttu-id="d262d-120">Для доступа к XML для мастера схем, нажмите кнопку **Добавление нового элемента** на **проекта** меню и добавьте **XML to Schema** шаблон либо из **данные** или **Общие элементы** группа шаблонов.</span><span class="sxs-lookup"><span data-stu-id="d262d-120">To access the XML to Schema Wizard, click **Add New Item** on the **Project** menu and add an **XML to Schema** template from either the **Data** or **Common Items** template group.</span></span> <span data-ttu-id="d262d-121">После включения всех источников XML-документов, чтобы получить набор схем XML из щелкните **ОК** Создание схему набора.</span><span class="sxs-lookup"><span data-stu-id="d262d-121">After you have included all the XML document sources to infer the XML Schema set from, click **OK** to create the inferred schema set.</span></span> <span data-ttu-id="d262d-122">Дополнительные сведения см. в разделе [XML для мастера схем](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d262d-122">For more information, see [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).</span></span>  
  
-   <span data-ttu-id="d262d-123">Также можно использовать XML-редакторе Visual Studio для выведения схемы XSD из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="d262d-123">You can also use the Visual Studio XML Editor to infer an XSD schema set from an XML file.</span></span> <span data-ttu-id="d262d-124">Чтобы создать XML-схему с помощью редактора XML, откройте XML-файл в конструкторе Visual Studio XML и затем нажмите кнопку **Create Schema** на **XML** меню.</span><span class="sxs-lookup"><span data-stu-id="d262d-124">To create an XML schema set by using the XML Editor, open an XML file in the Visual Studio XML Designer and then click **Create Schema** on the **XML** menu.</span></span> <span data-ttu-id="d262d-125">После создания набора схем XSD, можно сохранить созданную схему набора для одного или нескольких файлов XSD и включить их в проект.</span><span class="sxs-lookup"><span data-stu-id="d262d-125">After you create the XSD schema set, you can save the created schema set to one or more XSD files and include them in your project.</span></span> <span data-ttu-id="d262d-126">Дополнительные сведения см. в разделе[Практическое руководство: Включение XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span><span class="sxs-lookup"><span data-stu-id="d262d-126">For more information, see[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).</span></span>  
  
 <span data-ttu-id="d262d-127">Обратите внимание, что разные наборы XSD-схемы могут быть получены из нескольких XML-документов, которые предназначены для одной и той же схемы.</span><span class="sxs-lookup"><span data-stu-id="d262d-127">Note that different XSD schema sets might be inferred from multiple XML documents that are intended to have the same schema.</span></span> <span data-ttu-id="d262d-128">Это может произойти, когда определенные элементы и атрибуты находятся в одном XML-файле, а не в другом, или элементы включены в другом порядке.</span><span class="sxs-lookup"><span data-stu-id="d262d-128">This can occur when particular elements and attributes are found in one XML file and not in another, or when elements are included in different order, for example.</span></span> <span data-ttu-id="d262d-129">Если вы следует просмотреть выводимых наборов схем XSD для полноты и точности.</span><span class="sxs-lookup"><span data-stu-id="d262d-129">You should review inferred XSD schema sets for completeness and accuracy when you use XSD schema inference.</span></span>  
  
## <a name="member-list"></a><span data-ttu-id="d262d-130">Список членов</span><span class="sxs-lookup"><span data-stu-id="d262d-130">Member List</span></span>  
 <span data-ttu-id="d262d-131">После ввода точки (.) для разделения экземпляра объекта <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объекта (или экземпляр `IEnumerable(Of XElement)` или `IEnumerable(Of XDocument)`), Visual Basic IntelliSense отображает список возможных членов объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d262d-131">After you type a period (.) to delimit an instance of an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object (or an instance of `IEnumerable(Of XElement)` or `IEnumerable(Of XDocument)`), Visual Basic IntelliSense displays a list of possible object members.</span></span> <span data-ttu-id="d262d-132">Исходный список содержит три параметра, представляющие свойства оси XML, как описано в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="d262d-132">The initial list includes three options that represent XML axis properties, as described in the following list.</span></span>  
  
|<span data-ttu-id="d262d-133">Параметр</span><span class="sxs-lookup"><span data-stu-id="d262d-133">Option</span></span>|<span data-ttu-id="d262d-134">Описание</span><span class="sxs-lookup"><span data-stu-id="d262d-134">Description</span></span>|  
|---|---|  
|**\< >**|<span data-ttu-id="d262d-135">Выберите этот параметр для отображения списка возможных дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="d262d-135">Select this option to show a list of possible child elements.</span></span> <span data-ttu-id="d262d-136">Дополнительные сведения см. в разделе [литерала XML элемент](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и <xref:System.Xml.Linq.XContainer.Elements%2A>метод.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="d262d-136">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>|  
|**@**|<span data-ttu-id="d262d-137">Выберите этот параметр для отображения списка возможных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="d262d-137">Select this option to show a list of possible attributes.</span></span> <span data-ttu-id="d262d-138">Дополнительные сведения см. в разделе [свойства оси XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md). Этот параметр доступен только для объектов типа <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d262d-138">For more information, see [XML Axis Properties](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).This option is available only for objects of type <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="d262d-139">**…\< >**</span><span class="sxs-lookup"><span data-stu-id="d262d-139">**…\< >**</span></span>|<span data-ttu-id="d262d-140">Выберите этот параметр для отображения списка возможных элементов-потомков.</span><span class="sxs-lookup"><span data-stu-id="d262d-140">Select this option to show a list of possible descendant elements.</span></span> <span data-ttu-id="d262d-141">Дополнительные сведения см. в разделе [как: элементы-потомки XML доступа](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) и <xref:System.Xml.Linq.XContainer.Elements%2A>метод.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="d262d-141">For more information, see [How to: Access XML Descendant Elements](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) and the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>|  
  
 <span data-ttu-id="d262d-142">Выберите или Начните ввод любого из параметров XML из списка.</span><span class="sxs-lookup"><span data-stu-id="d262d-142">Select or begin typing any of the XML options from the list.</span></span> <span data-ttu-id="d262d-143">Список членов отобразит потенциальные члены из схемы XML, характерные для выбранного параметра.</span><span class="sxs-lookup"><span data-stu-id="d262d-143">The member list will then display potential members from the XML schema that are specific to the selected option.</span></span> <span data-ttu-id="d262d-144">Если имеется импортированное пространство имен XML, которые связаны с определенным префиксом пространства имен XML, список потенциальных префиксов пространства имен XML включается в список членов.</span><span class="sxs-lookup"><span data-stu-id="d262d-144">If you have XML namespaces imported that are associated with a specific XML namespace prefix, a list of potential XML namespace prefixes is included in the member list.</span></span>  
  
 <span data-ttu-id="d262d-145">Например рассмотрим следующую схему XSD.</span><span class="sxs-lookup"><span data-stu-id="d262d-145">For example, consider the following XSD schema.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema attributeFormDefault="unqualified"   
           elementFormDefault="qualified"   
           targetNamespace="http://SamplePurchaseOrder"   
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="PurchaseOrders">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="PurchaseOrder">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="Address" />  
              <xs:element name="Items" />  
              <xs:element name="Comment" />  
            </xs:sequence>  
            <xs:attribute name="PurchaseOrderNumber" type="xs:unsignedShort" use="required" />  
            <xs:attribute name="OrderDate" type="xs:string" use="required" />  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="d262d-146">Допустимый XML для XSD-схемы будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d262d-146">Valid XML for the XSD schema would resemble the following.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<PurchaseOrders xmlns="http://SamplePurchaseOrder">  
  <PurchaseOrder PurchaseOrderNumber="12345" OrderDate="2000-1-1">  
    <Address />  
    <Items />  
    <Comment />  
  </PurchaseOrder>  
</PurchaseOrders>  
```  
  
 <span data-ttu-id="d262d-147">Если включить этот файл XSD схемы в проект и импортировать целевое пространство имен из схемы XSD в файл кода или проект Visual Basic IntelliSense отображает элементы из схемы, при вводе кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d262d-147">If you include this XSD schema file in a project and import the target namespace from the XSD schema into your code file or project, Visual Basic IntelliSense displays members from the schema as you type your Visual Basic code.</span></span> <span data-ttu-id="d262d-148">Если целевое пространство имен для схемы XSD импортируется как пространство имен по умолчанию, и введите следующую команду, IntelliSense отображает список возможных дочерних элементов для `PurchaseOrder` XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="d262d-148">If the target namespace for the XSD schema is imported as the default namespace and you type the following, IntelliSense displays a list of possible child elements for the `PurchaseOrder` XML element.</span></span>  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 <span data-ttu-id="d262d-149">Список состоит из адреса, комментарий и элементы элементы.</span><span class="sxs-lookup"><span data-stu-id="d262d-149">The list consists of the Address, Comment, and Items elements.</span></span>  
  
### <a name="certainty-levels-for-intellisense-list-items"></a><span data-ttu-id="d262d-150">Уровень достоверности для элементов списка IntelliSense</span><span class="sxs-lookup"><span data-stu-id="d262d-150">Certainty Levels for IntelliSense List Items</span></span>  
 <span data-ttu-id="d262d-151">Определение типа XSD, предназначенные для IntelliSense не точно.</span><span class="sxs-lookup"><span data-stu-id="d262d-151">Determining the XSD type to use for IntelliSense is not exact.</span></span> <span data-ttu-id="d262d-152">В результате XML IntelliSense часто показывает развернутый список возможных членов.</span><span class="sxs-lookup"><span data-stu-id="d262d-152">As a result, XML IntelliSense will often show an expanded list of possible members.</span></span> <span data-ttu-id="d262d-153">Для облегчения выбора элемента из списка членов IntelliSense, элементы отображаются с указанием уровня точности, который XML IntelliSense имеет для определенного члена.</span><span class="sxs-lookup"><span data-stu-id="d262d-153">To aid you in selecting an item from the IntelliSense member list, items are displayed with an indication of the level of certainty that XML IntelliSense has for a particular member.</span></span>  
  
 <span data-ttu-id="d262d-154">Иногда XML IntelliSense можно определить определенного типа из схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="d262d-154">Sometimes XML IntelliSense can identify a specific type from the XSD schema.</span></span> <span data-ttu-id="d262d-155">В этих случаях будут отображаться возможные дочерние элементы, атрибуты или дочерние элементы для этого типа XSD с высокой степенью точности.</span><span class="sxs-lookup"><span data-stu-id="d262d-155">In these cases, it will display possible child elements, attributes, or descendant elements for that XSD type with a high degree of certainty.</span></span> <span data-ttu-id="d262d-156">Эти элементы определяются с флажком.</span><span class="sxs-lookup"><span data-stu-id="d262d-156">These items are identified with a check mark.</span></span>  
  
 <span data-ttu-id="d262d-157">Однако иногда XML IntelliSense не может определить определенного типа из схемы XSD.</span><span class="sxs-lookup"><span data-stu-id="d262d-157">However, sometimes XML IntelliSense is not able to identify a specific type from the XSD schema.</span></span> <span data-ttu-id="d262d-158">В этих случаях будут отображаться с низкой степенью точности раскрывшегося списка возможные дочерние элементы, атрибуты или дочерние элементы из схемы XSD для проекта.</span><span class="sxs-lookup"><span data-stu-id="d262d-158">In these cases, it will display an expanded list of possible child elements, attributes, or descendant elements from the XSD schema for the project with a low degree of certainty.</span></span> <span data-ttu-id="d262d-159">Эти элементы помечены знаком вопроса.</span><span class="sxs-lookup"><span data-stu-id="d262d-159">These items are identified with a question mark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d262d-160">См. также</span><span class="sxs-lookup"><span data-stu-id="d262d-160">See Also</span></span>  
 <span data-ttu-id="d262d-161">[Практическое руководство: Включение XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md) </span><span class="sxs-lookup"><span data-stu-id="d262d-161">[How to: Enable XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md) </span></span>  
<span data-ttu-id="d262d-162"> [XML для мастера схем](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="d262d-162"> [XML to Schema Wizard](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md) </span></span>  
<span data-ttu-id="d262d-163"> [Оператор Imports (пространство имен XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="d262d-163"> [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="d262d-164"> [Литеральное представление XML элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="d262d-164"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="d262d-165"> [Свойство оси атрибута XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="d262d-165"> [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span></span>  
<span data-ttu-id="d262d-166"> [Свойство дочерней оси XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="d262d-166"> [XML Descendant Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md) </span></span>  
<span data-ttu-id="d262d-167"> [Страница "Ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="d262d-167"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span></span>
