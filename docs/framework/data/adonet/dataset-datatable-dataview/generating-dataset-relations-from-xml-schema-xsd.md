---
title: Создание отношений наборов данных из схемы XML (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: feb0be7f66bf0f407e54ef0830c13f0c4a8a6418
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151134"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Создание отношений наборов данных из схемы XML (XSD)
В <xref:System.Data.DataSet> взаимосвязь между двумя или несколькими столбцами формируется путем создания отношения «родитель-потомок». Существует три способа представления отношения **DataSet** в схеме определения XML Schema (XSD):  
  
- Задайте вложенные сложные типы.  
  
- Используйте аннотацию **msdata:Relationship.**  
  
- Укажите **xs:keyref** без **msdata:ConstraintOnly** аннотации.  
  
## <a name="nested-complex-types"></a>Вложенные сложные типы  
 Определения вложенных сложных типов в схеме указывают на связь элементов по модели «родитель-потомок». Следующий фрагмент XML Schema показывает, что **OrderDetail** является элементом детского обеспечения элемента **Заказа.**  
  
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
  
 Процесс картирования XML Schema создает таблицы в **DataSet,** которые соответствуют вложенным типам сложных в схеме. Он также создает дополнительные столбцы, которые используются в качестве родительских**-** столбцов для генерируемых таблиц. Обратите внимание,**-** что в этих родительских столбцах родительского элемента указаны отношения, что не соответствует указанию основных ограничений ключа/иностранных ключей.  
  
## <a name="msdatarelationship-annotation"></a>Заметка msdata:Relationship  
 Аннотация **msdata:Relationship** позволяет явно указать отношения между родительскими и детскими отношениями между элементами в схеме, которые не вложены. В следующем примере показана структура элемента **«Связь».**  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 Атрибуты **аннотации msdata:Relationship** идентифицируют элементы, участвующие в отношениях между родителем и ребенком, а также элементы и атрибуты родительского ключа **и** **детские** элементы, участвующие в отношениях. Процесс картирования использует эту информацию для создания таблиц в **DataSet** и создания основных ключевых /иностранных ключевых отношений между этими таблицами.  
  
 Например, следующий фрагмент схемы определяет элементы **Order** и **OrderDetail** на одном уровне (не вложенные). Схема определяет аннотацию **msdata:Relationship,** которая определяет отношения между родителем и ребенком между этими двумя элементами. В этом случае явное отношение должно быть определено с помощью аннотации **msdata:Relationship.**  
  
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
  
 Процесс отображения использует элемент **«Отношения»** для создания отношений между столбцом **OrderNumber** в таблице **Заказа** и столбцом **OrderNo** в таблице **OrderDetail** в **DataSet.** Процесс сопоставления только указывает связь, он не задает автоматически ограничения значений в этих столбцах подобно ограничениям первичного/внешнего ключа в реляционных базах данных.  
  
### <a name="in-this-section"></a>в этом разделе  
 [Сопоставление неявных отношений между вложенными элементами схемы](map-implicit-relations-between-nested-schema-elements.md)  
 Описывает ограничения и связи, которые неявно создаются в **DataSet,** когда вложенные элементы встречаются в XML Schema.  
  
 [Сопоставление отношений, заданных для вложенных элементов](map-relations-specified-for-nested-elements.md)  
 Описывает, как четко установить отношения в **DataSet** для вложенных элементов в XML Schema.  
  
 [Указание отношений между элементами без вложенности](specify-relations-between-elements-with-no-nesting.md)  
 Описывает, как создать отношения в **DataSet** между элементами XML Schema, которые не вложены.  
  
### <a name="related-sections"></a>См. также  
 [Наследование реляционной структуры набора данных от схемы XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Описывает реляционную структуру, или схему, **DataSet,** которая создается из схемы определения XML Schema (XSD).  
  
 [Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы XML Schema, используемые для создания уникальных и внешних ключевых ограничений в **DataSet.**  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об ADO.NET](../ado-net-overview.md)
