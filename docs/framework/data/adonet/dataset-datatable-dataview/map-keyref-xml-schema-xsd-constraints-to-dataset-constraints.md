---
title: Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 93f766003326fd41357581196015fd58c71d7508
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040372"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных
Элемент **keyref** позволяет устанавливать связи между элементами в документе. Это похоже на связь по внешнему ключу в реляционной базе данных. Если схема указывает элемент **keyref** , то элемент преобразуется в процессе сопоставления схемы в соответствующее ограничение внешнего ключа для столбцов в таблицах <xref:System.Data.DataSet>. По умолчанию элемент **keyref** также создает отношение со свойствами **паренттабле**, **ChildTable**, **парентколумн**и **чилдколумн** , указанными для отношения.  
  
 В следующей таблице описаны атрибуты **msdata** , которые можно указать в элементе **keyref** .  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|**msdata: Констраинтонли**|Если для элемента **keyref** схемы задано **значение констраинтонли = "true"** , то создается ограничение, но связь не создается. Если этот атрибут не задан (или имеет значение **false**), в **наборе данных**создается и ограничение, и отношение.|  
|**msdata: ConstraintName**|Если указан атрибут **ConstraintName** , его значение используется в качестве имени ограничения. В противном случае атрибут **Name** элемента **keyref** в схеме предоставляет имя ограничения в **наборе данных**.|  
|**msdata: UpdateRule**|Если атрибут **UpdateRule** указан в элементе **keyref** схемы, его значение присваивается свойству ограничения **UpdateRule** в **наборе данных**. В противном случае свойство **UpdateRule** имеет значение **CASCADE**.|  
|**msdata: DeleteRule**|Если атрибут **DeleteRule** указан в элементе **keyref** схемы, его значение присваивается свойству ограничения **DeleteRule** в **наборе данных**. В противном случае свойство **DeleteRule** имеет значение **CASCADE**.|  
|**msdata: Акцептрежектруле**|Если атрибут **акцептрежектруле** указан в элементе **keyref** схемы, его значение присваивается свойству ограничения **акцептрежектруле** в **наборе данных**. В противном случае свойство **акцептрежектруле** имеет значение **None**.|  
  
 В следующем примере показана схема, указывающая **ключ** и связи **keyref** между дочерним элементом **OrderNumber** элемента **Order** и дочерним элементом **ордерно** элемента **OrderDetail** . дерев.  
  
 В этом примере дочерний элемент **OrderNumber** элемента **OrderDetail** ссылается на дочерний элемент ключа **ордерно** элемента **Order** .  
  
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
  
 Процесс сопоставления схем на языке определения схем XML (XSD) создает следующий **набор данных** с двумя таблицами:  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Кроме того, **набор данных** определяет следующие ограничения.  
  
- Ограничение UNIQUE для таблицы **Order** .  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- Связь между таблицами **Order** и **OrderDetail** . **Вложенное** свойство имеет значение **false** , так как два элемента не вложены в схему.  
  
    ```text
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- Ограничение внешнего ключа для таблицы **OrderDetail** .  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a>См. также

- [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Создание отношений DataSet из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
