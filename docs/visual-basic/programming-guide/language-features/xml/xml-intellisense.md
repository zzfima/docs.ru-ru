---
title: "XML IntelliSense в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "IntelliSense [Visual Basic], XML"
  - "код Visual Basic, XML"
  - "XML [Visual Basic], IntelliSense"
  - "XML IntelliSense [Visual Basic]"
ms.assetid: 59506ce9-d64e-417e-90fc-e9fe19f0a8fa
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# XML IntelliSense в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Редактор кода Visual Basic включает возможности IntelliSense для XML, обеспечивающие завершение слов для элементов, определенных в схеме XML.  При включении в проект файл схемы определения XML \(XSD\) и импорте пространства имен для схемы с помощью оператора `Imports`, редактор кода будет включать элементы из схемы XSD в списое IntelliSense допустимых переменных члена для объектов <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XDocument>.  Далее показан показан список членов IntelliSense для объекта <xref:System.Xml.Linq.XElement>.  
  
 ![XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/media/xml-intellisense.png "XML\_Intellisense")  
XML IntelliSense  
  
## Включение XML IntelliSense в Visual Basic  
 Чтобы включить XML IntelliSense в Visual Basic, необходимо включить файл XSD\-схемы в проект Visual Basic.  Следует также импортировать целевое пространство имен для схемы XSD в файл кода с помощью оператора `Imports`.  Другим способом является добавление целевого пространства имен в список имен на уровне проекта при помощи страницы **Ссылки** в конструкторе проекта Visual Basic.  Примеры содержатся в разделе [Практическое руководство. Включение XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).  Дополнительные сведения см. в разделах [Оператор Imports \(пространство имен XML\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) и [Страница "Ссылки" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic).  
  
 Обратите внимание, что по умолчанию файлы схемы XSD в проектах Visual Basic не отображаются.  Может потребоваться нажатие кнопки **Показать все файлы**, чтобы выбрать XSD\-файл для включения в проект.  
  
### Создание файла схемы \(получение схемы\)  
 XSD\-схему для существующего XML\-файла с можно создать с помощью средств Visual Studio XML.  
  
-   Начиная с пакета обновления 1, можно использовать XML для мастера схем для создания XML\-схемы, которая является производной от одного или более XML\-документов и включает их в проект.  Можно использовать любые комбинации XML\-документов в форме текстовых файлов, XML из HTTP\-адресов или XML, который объявляется и передается в XML для мастера схем.  Чтобы обратиться к XML для мастера схем, нажмите **Добавить новый элемент** в меню **Проект** и добавьте шаблон **XML для схем** либо из группы шаблонов **Данные**, либо из группы шаблонов **Общие элементы**.  После включения всех источников XML\-документов для определения набора XML\-схем, нажмите **OK** для создания производного набора схем.  Дополнительные сведения см. в разделе [Мастер построения схемы на основе кода XML](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md).  
  
-   Можно также использовать редактор Visual Studio XML для получения XSD\-схемы из XML\-файла.  Чтобы создать XML\-схему при помощи редактора XML, откройте XML\-файл в конструкторе Visual Studio XML и затем нажмите **Создать схему** в меню **XML**.  После создания XSD\-схемы, ее можно сохранить в одном или нескольких XSD\-файлах и включить их в проект.  Дополнительные сведения см. в разделе [Практическое руководство. Включение XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md).  
  
 Обратите внимание, что разные XSD\-схемы могут быть получены из нескольких XML\-документов, для которых предназначено использование одной и той же схемы.  Это может произойти, если определенные элементы и атрибуты находятся в одном файле XML, а не в другом, или элементы включены в другом порядке.  При получении XSD\-схемы ее следует просмотреть на предмет полноты и точности.  
  
## Список членов  
 После ввода точки \(.\) для разделения экземпляра объекта <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XDocument> \(или экземпляра `IEnumerable(Of XElement)` или `IEnumerable(Of XDocument)`\) Visual Basic IntelliSense отображает список возможных членов объектов.  Исходный список содержит три параметра, представляющие свойства XML axis, как описано в следующем списке.  
  
|||  
|-|-|  
|Параметр|Описание|  
|**\< \>**|Выберите этот параметр для отображения списка возможных дочерних элементов.  Дополнительные сведения см. в разделе [Литеральное представление XML\-элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) и <xref:System.Xml.Linq.XContainer.Elements%2A>.|  
|**@**|Выберите этот параметр для отображения списка возможных атрибутов.  Дополнительные сведения содержатся в разделе [Свойства оси XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md). Этот параметр доступен только для объектов типа <xref:System.Xml.Linq.XElement>.|  
|**…\< \>**|Выберите этот параметр для отображения списка возможных элементов\-потомков.  Дополнительные сведения см. в разделе [Практическое руководство. Доступ к элементам\-потомкам XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md) и <xref:System.Xml.Linq.XContainer.Elements%2A>.|  
  
 Выберите или начните ввод любого из параметров XML из списка.  Затем элемент списка отобразит потенциальные члены, относящиеся к выбранному параметру, из XML\-схемы.  Если имеется импортированное пространство имен XML, которое связано с определенным префиксом пространства имен XML, то список потенциальных префиксов пространства имен XML включается в список членов.  
  
 Например, рассмотрим следующую XSD\-схему.  
  
```  
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
  
 Допустимый XML для XSD\-схемы будет выглядеть следующим образом.  
  
```  
<?xml version="1.0"?>  
<PurchaseOrders xmlns="http://SamplePurchaseOrder">  
  <PurchaseOrder PurchaseOrderNumber="12345" OrderDate="2000-1-1">  
    <Address />  
    <Items />  
    <Comment />  
  </PurchaseOrder>  
</PurchaseOrders>  
```  
  
 Если включить файл этой схемы XSD в проект и импортировать пространство имен из XSD\-схемы в файл кода или проекта, Visual Basic IntelliSense отобразит члены из схемы при вводе кода Visual Basic.  Если пространство имен для схемы XSD импортировано как пространство имен по умолчанию и вводятся следующие данные, IntelliSense отобразит список возможных дочерних элементов для элемента XML `PurchaseOrder`.  
  
```  
Dim po = <PurchaseOrder />  
po.<  
```  
  
 Список состоит из элементов Address, Comment и Items.  
  
### Уровни точности для элементов списка IntelliSense  
 Определение XSD\-типа при использовании технологии IntelliSense неточно.  В результате XML IntelliSense часто показывает развернутый список возможных членов.  Для облегчения выбора элемента из списка членов IntelliSense, они отображаются с указанием уровня точности, который IntelliSense XML имеет для определенного члена.  
  
 Иногда XML IntelliSense может идентифицировать определенный тип из XSD\-схемы.  В этих случаях возможные дочерние элементы, атрибуты или элементы, являющиеся потомками для этого типа XSD, будут отображаться с высокой степенью точности.  Эти элементы имеют соответствующую отметку.  
  
 Однако иногда XML IntelliSense не может идентифицировать определенные типы из XSD\-схемы.  В этих случаях возможные дочерние элементы, атрибуты или элементы, являющиеся потомками элементов из этой XSD\-схемы, будут отображаться с низкой степенью точности.  Эти элементы помечены знаком вопроса.  
  
## См. также  
 [Практическое руководство. Включение XML IntelliSense в Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/how-to-enable-xml-intellisense.md)   
 [Мастер построения схемы на основе кода XML](../../../../visual-basic/programming-guide/language-features/xml/xml-to-schema-wizard.md)   
 [Оператор Imports \(пространство имен XML\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Литеральное представление XML\-элемента](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [Свойство оси атрибута XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)   
 [Свойство дочерней оси XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [Страница "Ссылки" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)