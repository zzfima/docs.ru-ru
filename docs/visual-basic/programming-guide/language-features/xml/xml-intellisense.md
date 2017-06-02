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
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8c43db3d2010e4fa92eebeec8a973c50052b1340
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="xml-intellisense-in-visual-basic"></a>XML IntelliSense в Visual Basic
Редактор кода Visual Basic включает функции IntelliSense для XML, обеспечивают завершение слов для элементов, определенных в схеме XML. Если включить в проект файл определения схемы XML (XSD) и импортировать целевое пространство имен схемы с помощью `Imports` инструкцию, редактор кода будет включать элементы из схемы XSD в списке IntelliSense допустимых переменных члена для <xref:System.Xml.Linq.XElement>и <xref:System.Xml.Linq.XDocument>объекты.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> На следующем рисунке показан список членов IntelliSense для <xref:System.Xml.Linq.XElement>объекта.</xref:System.Xml.Linq.XElement>  
  
 ![XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml_intellisense.png "XML_Intellisense")  
XML IntelliSense  
  
## <a name="enabling-xml-intellisense-in-visual-basic"></a>Включение XML IntelliSense в Visual Basic  
 Включение XML IntelliSense в Visual Basic, необходимо включить файла XSD-схемы в проекте Visual Basic. Необходимо также импортировать целевое пространство имен для схемы XSD в файл кода с помощью `Imports` инструкции. Кроме того, можно добавить целевое пространство имен в список имен уровня проекта с помощью **ссылки** страницы в конструкторе проектов Visual Basic. Примеры см. в разделе [Практическое руководство: Включение XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md). Дополнительные сведения см. в разделе [оператор Imports (пространство имен XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) и [страница "ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Обратите внимание, что по умолчанию не могут видеть файлы схемы XSD в проектах Visual Basic. Нужно щелкнуть **Показать все файлы** кнопку, чтобы выбрать XSD-файл для включения в проект.  
  
### <a name="generating-a-schema-file-schema-inference"></a>Создание файла схемы (получение схемы)  
 Выводя XSD-схемы с помощью средств Visual Studio XML можно создать схему XSD для существующего файла XML.  
  
-   Начиная с пакета обновления&1;, можно использовать XML для мастера схем для создания набор XML-схем, которая является производной от одного или нескольких XML-документов и включает их в проект. Можно использовать любую комбинацию XML-документов в виде текстовых файлов, XML из HTTP-адресов или XML, который объявляется и передается в XML для мастера схем. Для доступа к XML для мастера схем, нажмите кнопку **Добавление нового элемента** на **проекта** меню и добавьте **XML to Schema** шаблон либо из **данные** или **Общие элементы** группа шаблонов. После включения всех источников XML-документов, чтобы получить набор схем XML из щелкните **ОК** Создание схему набора. Дополнительные сведения см. в разделе [XML для мастера схем](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).  
  
-   Также можно использовать XML-редакторе Visual Studio для выведения схемы XSD из XML-файла. Чтобы создать XML-схему с помощью редактора XML, откройте XML-файл в конструкторе Visual Studio XML и затем нажмите кнопку **Create Schema** на **XML** меню. После создания набора схем XSD, можно сохранить созданную схему набора для одного или нескольких файлов XSD и включить их в проект. Дополнительные сведения см. в разделе[Практическое руководство: Включение XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).  
  
 Обратите внимание, что разные наборы XSD-схемы могут быть получены из нескольких XML-документов, которые предназначены для одной и той же схемы. Это может произойти, когда определенные элементы и атрибуты находятся в одном XML-файле, а не в другом, или элементы включены в другом порядке. Если вы следует просмотреть выводимых наборов схем XSD для полноты и точности.  
  
## <a name="member-list"></a>Список членов  
 После ввода точки (.) для разделения экземпляра объекта <xref:System.Xml.Linq.XElement>или <xref:System.Xml.Linq.XDocument>объекта (или экземпляр `IEnumerable(Of XElement)` или `IEnumerable(Of XDocument)`), Visual Basic IntelliSense отображает список возможных членов объектов.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Исходный список содержит три параметра, представляющие свойства оси XML, как описано в следующем списке.  
  
|Параметр|Описание|  
|---|---|  
|**\< >**|Выберите этот параметр для отображения списка возможных дочерних элементов. Дополнительные сведения см. в разделе [литерала XML элемент](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и <xref:System.Xml.Linq.XContainer.Elements%2A>метод.</xref:System.Xml.Linq.XContainer.Elements%2A>|  
|**@**|Выберите этот параметр для отображения списка возможных атрибутов. Дополнительные сведения см. в разделе [свойства оси XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md). Этот параметр доступен только для объектов типа <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>|  
|**…\< >**|Выберите этот параметр для отображения списка возможных элементов-потомков. Дополнительные сведения см. в разделе [как: элементы-потомки XML доступа](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) и <xref:System.Xml.Linq.XContainer.Elements%2A>метод.</xref:System.Xml.Linq.XContainer.Elements%2A>|  
  
 Выберите или Начните ввод любого из параметров XML из списка. Список членов отобразит потенциальные члены из схемы XML, характерные для выбранного параметра. Если имеется импортированное пространство имен XML, которые связаны с определенным префиксом пространства имен XML, список потенциальных префиксов пространства имен XML включается в список членов.  
  
 Например рассмотрим следующую схему XSD.  
  
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
  
 Допустимый XML для XSD-схемы будет выглядеть следующим образом.  
  
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
  
 Если включить этот файл XSD схемы в проект и импортировать целевое пространство имен из схемы XSD в файл кода или проект Visual Basic IntelliSense отображает элементы из схемы, при вводе кода Visual Basic. Если целевое пространство имен для схемы XSD импортируется как пространство имен по умолчанию, и введите следующую команду, IntelliSense отображает список возможных дочерних элементов для `PurchaseOrder` XML-элемента.  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 Список состоит из адреса, комментарий и элементы элементы.  
  
### <a name="certainty-levels-for-intellisense-list-items"></a>Уровень достоверности для элементов списка IntelliSense  
 Определение типа XSD, предназначенные для IntelliSense не точно. В результате XML IntelliSense часто показывает развернутый список возможных членов. Для облегчения выбора элемента из списка членов IntelliSense, элементы отображаются с указанием уровня точности, который XML IntelliSense имеет для определенного члена.  
  
 Иногда XML IntelliSense можно определить определенного типа из схемы XSD. В этих случаях будут отображаться возможные дочерние элементы, атрибуты или дочерние элементы для этого типа XSD с высокой степенью точности. Эти элементы определяются с флажком.  
  
 Однако иногда XML IntelliSense не может определить определенного типа из схемы XSD. В этих случаях будут отображаться с низкой степенью точности раскрывшегося списка возможные дочерние элементы, атрибуты или дочерние элементы из схемы XSD для проекта. Эти элементы помечены знаком вопроса.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство: Включение XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)   
 [XML для мастера схем](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)   
 [Оператор Imports (пространство имен XML)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Литеральное представление XML элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Свойство оси атрибута XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)   
 [Свойство дочерней оси XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [Страница "Ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)
