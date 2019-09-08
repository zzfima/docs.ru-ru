---
title: Создание отношений наборов данных из схемы XML (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: d00f07ee3338941b7de1bb890f71cd3c2d120246
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784648"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Создание отношений наборов данных из схемы XML (XSD)
В <xref:System.Data.DataSet> взаимосвязь между двумя или несколькими столбцами формируется путем создания отношения «родитель-потомок». Существует три способа представления связи **набора данных** в схеме языка определения схемы XML (XSD).  
  
- Задайте вложенные сложные типы.  
  
- Используйте аннотацию **msdata: relationship** .  
  
- Укажите **xs: keyref** без аннотации **msdata: констраинтонли** .  
  
## <a name="nested-complex-types"></a>Вложенные сложные типы  
 Определения вложенных сложных типов в схеме указывают на связь элементов по модели «родитель-потомок». Следующий фрагмент схемы XML показывает, что элемент **OrderDetail** является дочерним элементом элемента **Order** .  
  
```xml  
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
  
 Процесс сопоставления схем XML создает таблицы в **наборе данных** , соответствующие вложенным сложным типам в схеме. Он также создает дополнительные столбцы, которые используются в качестве **-** родительских дочерних столбцов для создаваемых таблиц. Обратите внимание, **-** что эти родительские дочерние столбцы задают связи, которые не совпадают с указанием ограничений первичного и внешнего ключей.  
  
## <a name="msdatarelationship-annotation"></a>Заметка msdata:Relationship  
 Аннотация **msdata: relationship** позволяет явно указать связи типа «родители-потомки» между элементами схемы, которые не являются вложенными. В следующем примере показана структура элемента **Relationship** .  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Атрибуты заметки **msdata: relationship** указывают элементы, участвующие в связи типа «родители-потомки», а также элементы и атрибуты **родительскими** и **чилдкэй** , участвующие в связи. Процесс сопоставления использует эти сведения для создания таблиц в **наборе данных** и для создания связи первичного и внешнего ключей между этими таблицами.  
  
 Например, в следующем фрагменте схемы элементы **Order** и **OrderDetail** указываются на одном и том же уровне (не вложенном). Схема задает аннотацию **msdata: relationship** , которая указывает связь типа «родители-потомки» между этими двумя элементами. В этом случае необходимо указать явную связь с помощью аннотации **msdata: relationship** .  
  
```xml  
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
  
 В процессе сопоставления используется элемент **Relationship** для создания связи типа «родители-потомки» между столбцом **OrderNumber** в таблице **Order** и столбцом **Ордерно** в таблице **OrderDetail** в **наборе данных**. Процесс сопоставления только указывает связь, он не задает автоматически ограничения значений в этих столбцах подобно ограничениям первичного/внешнего ключа в реляционных базах данных.  
  
### <a name="in-this-section"></a>В этом разделе  
 [Сопоставление неявных отношений между вложенными элементами схемы](map-implicit-relations-between-nested-schema-elements.md)  
 Описывает ограничения и связи, которые неявно создаются в **наборе данных** при обнаружении вложенных элементов в схеме XML.  
  
 [Сопоставление отношений, заданных для вложенных элементов](map-relations-specified-for-nested-elements.md)  
 Описывает, как явно задать связи в **наборе данных** для вложенных элементов в схеме XML.  
  
 [Указание отношений между элементами без вложенности](specify-relations-between-elements-with-no-nesting.md)  
 Описывает создание связей в **наборе данных** между невложенными ЭЛЕМЕНТАМИ XML-схемы.  
  
### <a name="related-sections"></a>Связанные разделы  
 [Наследование реляционной структуры DataSet от схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Описывает реляционную структуру или схему **набора данных** , созданного из схемы языка определения схемы XML (XSD).  
  
 [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы XML-схемы, используемые для создания ограничений UNIQUE и FOREIGN KEY в **наборе данных**.  
  
## <a name="see-also"></a>См. также

- [Общие сведения об ADO.NET](../ado-net-overview.md)
