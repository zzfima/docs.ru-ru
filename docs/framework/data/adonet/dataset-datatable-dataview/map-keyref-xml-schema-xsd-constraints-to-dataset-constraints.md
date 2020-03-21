---
title: Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 902b79b73f494ced0f54b29babff1b2e767bd47a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150887"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Сопоставление ограничений XML-схемы (XSD) keyref с ограничениями набора данных
Элемент **keyref** позволяет установить связи между элементами в документе. Это похоже на связь по внешнему ключу в реляционной базе данных. Если схема определяет элемент **keyref,** элемент преобразуется в процессе отображения схемы в соответствующее иностранное ограничение клавиш на <xref:System.Data.DataSet>столбцах в таблицах . По умолчанию элемент **keyref** также генерирует отношение с **родительскими**свойствами, **ChildTable,** **ParentColumn**и **ChildColumn** свойствами, указанными в отношении.  
  
 В следующей таблице излагаются атрибуты **msdata,** которые можно указать в элементе **keyref.**  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|Если **на** элементе keyref в схеме указан элемент **keyref,** создается ограничение, но никакое отношение не создается. Если этот атрибут не указан (или установлен **на ложное),** как ограничение, так и отношение создаются в **DataSet.**|  
|**msdata:ConstraintName**|Если атрибут **ConstraintName** указан, его значение используется в качестве имени ограничения. В противном случае атрибут **имени** элемента **keyref** в схеме предоставляет имя ограничения в **DataSet.**|  
|**msdata:UpdateRule**|Если атрибут **UpdateRule** указан в элементе **keyref** в схеме, его значение присваивается свойству ограничения **UpdateRule** в **DataSet.** В противном случае свойство **UpdateRule** настроено на **Каскад.**|  
|**msdata:DeleteRule**|Если атрибут **DeleteRule** указан в элементе **keyref** в схеме, его значение присваивается свойству ограничения **DeleteRule** в **DataSet.** В противном случае свойство **DeleteRule** настроено на **Каскад.**|  
|**msdata:AcceptRejectRule**|Если атрибут **AcceptRejectRule** указан в элементе **keyref** в схеме, его значение присваивается свойству ограничения **AcceptRejectRule** в **DataSet.** В противном случае свойство **AcceptRejectRule** устанавливается **в Нет**.|  
  
 Следующий пример содержит схему, которая определяет **ключевые** и **ключевые** отношения между элементом **ребенка OrderNumber** элемента **Порядка** и элементом **Ребенка OrderNo** элемента **Order** Of.  
  
 В примере элемент **«ПорядокНомер»** элемента **OrderDetail** относится к элементу **OrderNo** ключевого элемента ребенка **элемента Заказа.**  
  
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
  
 Процесс определения схемы XML Schema (XSD) создает следующий **DataSet** с двумя таблицами:  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Кроме того, **DataSet** определяет следующие ограничения:  
  
- Уникальное ограничение на столе **Заказа.**  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- Взаимосвязь между таблицами **Order** и **OrderDetail.** **Свойство Nested настроено** на **ложное,** поскольку два элемента не вложены в схему.  
  
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
  
- Иностранное ограничение ключа на таблице **OrderDetail.**  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Создание отношений наборов данных из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
