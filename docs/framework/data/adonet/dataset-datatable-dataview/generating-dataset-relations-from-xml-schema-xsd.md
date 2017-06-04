---
title: "Формирование связей DataSet на основе схемы XML (XSD) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Формирование связей DataSet на основе схемы XML (XSD)
В <xref:System.Data.DataSet> взаимосвязь между двумя или несколькими столбцами формируется путем создания отношения «родитель\-потомок».  Существует три способа представить связь элементов **DataSet** внутри схемы XSD.  
  
-   Задайте вложенные сложные типы.  
  
-   Используйте заметку **msdata:Relationship**.  
  
-   Задайте **xs:keyref** без заметки **msdata:ConstraintOnly**.  
  
## Вложенные сложные типы  
 Определения вложенных сложных типов в схеме указывают на связь элементов по модели «родитель\-потомок».  В следующем фрагменте схемы XML показано, что элемент **OrderDetail** является дочерним по отношению к элементу **Order**.  
  
```  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>          
       <xs:element name="OrderDetail" />  
           <xs:complexType>               
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Процесс сопоставления схем XML создает таблицы в наборе данных **DataSet**, соответствующие вложенным сложным типам в схеме.  Он также создает дополнительные столбцы, которые используются как столбцы типа «родитель**\-**потомок» в созданных таблицах.  Обратите внимание, что эти столбцы «родитель**\-**потомок» задают связи, которые отличаются от ограничений первичного\/внешнего ключа.  
  
## Заметка msdata:Relationship  
 Заметка **msdata:Relationship** позволяет явно задать связь «родитель\-потомок» между невложенными элементами схемы.  В следующем примере показана структура элемента **Relationship**.  
  
```  
  
  <msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Атрибуты заметки **msdata:Relationship** определяют элементы связи «родитель\-потомок», элементы **parentkey** и **childkey**, а также атрибуты этой связи.  Процесс сопоставления использует эти данные для создания таблиц в **DataSet** и связи «первичный\/внешний ключ» между этими таблицами.  
  
 Например, следующий фрагмент схемы задает одноуровневые \(не вложенные\) элементы **Order** и **OrderDetail**.  В схеме содержится заметка **msdata:Relationship**, которая указывает связь «родитель\-потомок» между этими элементами.  В этом случае необходимо явно задать связь с помощью заметки **msdata:Relationship**.  
  
```  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"   
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
  
```  
  
 Процесс сопоставления использует элемент **Relationship** для создания связи «родитель\-потомок» между столбцом **OrderNumber** в таблице **Order** и столбцом **OrderNo** в таблице **OrderDetail** в **DataSet**.  Процесс сопоставления только указывает связь, он не задает автоматически ограничения значений в этих столбцах подобно ограничениям первичного\/внешнего ключа в реляционных базах данных.  
  
### Содержание  
 [Сопоставление неявных связей между вложенными элементами схемы](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 Описание ограничений и связей, неявно создаваемых в **DataSet**, если в схеме XML встречаются вложенные элементы.  
  
 [Сопоставление связей, указанных для вложенных элементов](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 Описание способов явной установки связей в **DataSet** для вложенных элементов схемы XML.  
  
 [Определение связей между невложенными элементами](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 Описание способов создания связей в **DataSet** между невложенными элементами схемы XML.  
  
### Связанные разделы  
 [Выведение реляционной структуры DataSet из схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Описание реляционной структуры \(или схемы\) **DataSet**, созданной из схемы XSD.  
  
 [Сопоставление ограничений схемы XML \(XSD\) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описание элементов схемы XML, используемых для создания ограничений уникального и внешнего ключа в **DataSet**.  
  
## См. также  
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)