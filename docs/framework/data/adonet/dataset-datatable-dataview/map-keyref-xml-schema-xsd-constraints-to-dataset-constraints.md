---
title: "Сопоставление ограничений keyref схемы XML (XSD) с ограничениями DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Сопоставление ограничений keyref схемы XML (XSD) с ограничениями DataSet
Элемент **keyref** позволяет устанавливать ссылки между элементами внутри документа.  Это похоже на связь по внешнему ключу в реляционной базе данных.  Если в схеме задан элемент **keyref**, то он преобразовывается в процессе сопоставления схемы в соответствующее ограничение внешнего ключа, налагаемое на столбцы в таблицах объекта <xref:System.Data.DataSet>.  По умолчанию элемент **keyref** также формирует связь со свойствами **ParentTable**, **ChildTable**, **ParentColumn** и **ChildColumn**, указанными в этой связи.  
  
 В следующей таблице приведено описание атрибутов **msdata**, которые можно задать в элементе **keyref**.  
  
|Имя атрибута|Описание|  
|------------------|--------------|  
|**msdata:ConstraintOnly**|Если для элемента **keyref** в схеме задано **ConstraintOnly\="true"**, создается ограничение, но не создается связь.  Если этот атрибут не задан \(если ему установлено значение **False**\), в объекте **DataSet** создается и ограничение, и связь.|  
|**msdata:ConstraintName**|Если атрибут **ConstraintName** задан, его значение используется в качестве имени ограничения.  В противном случае имя ограничения в объекте **DataSet** берется из атрибута **name** элемента **keyref** в схеме.|  
|**msdata:UpdateRule**|Если атрибут **UpdateRule** задан в элементе **keyref** в схеме, его значение назначается свойству ограничения **UpdateRule** в объекте **DataSet**.  В противном случае свойство **UpdateRule** имеет значение **Cascade**.|  
|**msdata:DeleteRule**|Если атрибут **DeleteRule** задан в элементе **keyref** в схеме, его значение назначается свойству ограничения **DeleteRule** в объекте **DataSet**.  В противном случае свойство **DeleteRule** имеет значение **Cascade**.|  
|**msdata:AcceptRejectRule**|Если атрибут **AcceptRejectRule** задан в элементе **keyref** в схеме, его значение назначается свойству ограничения **AcceptRejectRule** в объекте **DataSet**.  В противном случае свойство **AcceptRejectRule** имеет значение **None**.|  
  
 В следующем примере содержится схема, которая задает связи **key** и **keyref** между дочерним элементом **OrderNumber** элемента **Order** и дочерним элементом **OrderNo** элемента **OrderDetail**.  
  
 В этом примере дочерний элемент **OrderNumber** элемента **OrderDetail** ссылается на ключевой дочерний элемент **OrderNo** элемента **Order**.  
  
```  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 Процесс сопоставления схемы на языке XSD создает следующий объект **DataSet** с двумя таблицами:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Кроме того, этот объект **DataSet** определяет следующие ограничения:  
  
-   Ограничение уникальности на таблицу **Order**.  
  
    ```  
  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   Связь между таблицами **Order** и **OrderDetail**.  Свойство **Nested** имеет значение **False**, так как два этих элемента не являются вложенными в схеме.  
  
    ```  
  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
-   Ограничение внешнего ключа на таблицу **OrderDetail**.  
  
    ```  
  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## См. также  
 [Сопоставление ограничений схемы XML \(XSD\) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Формирование связей DataSet на основе схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)