---
title: Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: dcb295aef6d93222e682ef7f720c83963036e795
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607505"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных
**Keyref** элемент позволяет устанавливать ссылки между элементами внутри документа. Это похоже на связь по внешнему ключу в реляционной базе данных. Если в схеме **keyref** элемент преобразуется в процессе сопоставления схемы для соответствующего ограничения внешнего ключа на столбцы в таблицах <xref:System.Data.DataSet>. По умолчанию **keyref** элемент также формирует связь с **ParentTable**, **ChildTable**, **ParentColumn**и  **ChildColumn** свойства, указанными в этой связи.  
  
 В следующей таблице описываются **msdata** атрибуты, можно указать в **keyref** элемент.  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|**msdata: constraintonly**|Если **ConstraintOnly = «true»** заметка указывается для **keyref** элемент в схеме, создается ограничение, но не создается связь. Если этот атрибут не указан (или имеет значение **False**), ограничения и отношения создаются в **набора данных**.|  
|**msdata: ConstraintName**|Если **ConstraintName** атрибут указан, его значение используется в качестве имени ограничения. В противном случае **имя** атрибут **keyref** элемент в схеме предоставляет имя ограничения в **набора данных**.|  
|**msdata:UpdateRule**|Если **UpdateRule** атрибут указан в **keyref** элемента в схеме, его значение будет назначено **UpdateRule** свойство ограничения в  **Набор данных**. В противном случае **UpdateRule** свойству **Cascade**.|  
|**msdata:DeleteRule**|Если **DeleteRule** атрибут указан в **keyref** элемента в схеме, его значение будет назначено **DeleteRule** свойство ограничения в  **Набор данных**. В противном случае **DeleteRule** свойству **Cascade**.|  
|**msdata:AcceptRejectRule**|Если **AcceptRejectRule** атрибут указан в **keyref** элемента в схеме, его значение будет назначено **AcceptRejectRule** свойство ограничения в  **Набор данных**. В противном случае **AcceptRejectRule** свойству **None**.|  
  
 В следующем примере содержится схема, которая задает **ключ** и **keyref** связи между **OrderNumber** дочерний элемент элемента **заказа**  элемент и **OrderNo** дочерний элемент элемента **OrderDetail** элемент.  
  
 В примере **OrderNumber** дочерний элемент элемента **OrderDetail** элемент ссылается на **OrderNo** ключа дочерний элемент элемента **порядок**элемент.  
  
```xml  
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
  
 Процесс сопоставления схемы языка XSD определения схемы XML формирует следующие **набора данных** с двумя таблицами:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Кроме того **набора данных** определяет следующие ограничения:  
  
- Ограничение уникальности на **порядок** таблицы.  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- Отношение между **порядок** и **OrderDetail** таблиц. **Nested** свойству **False** так, как два элемента не являются вложенными в схеме.  
  
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
  
- Ограничение внешнего ключа для **OrderDetail** таблицы.  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>См. также

- [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Создание отношений DataSet из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
