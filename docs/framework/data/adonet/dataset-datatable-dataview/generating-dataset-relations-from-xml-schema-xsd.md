---
title: Создание отношений наборов данных из схемы XML (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: 7c73dcec3d23b094436791af6649de83b9eacad9
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43880040"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>Создание отношений наборов данных из схемы XML (XSD)
В <xref:System.Data.DataSet> взаимосвязь между двумя или несколькими столбцами формируется путем создания отношения «родитель-потомок». Существует три способа представления **набора данных** отношения в схему языка определения схемы XML:  
  
-   Задайте вложенные сложные типы.  
  
-   Используйте **msdata: Relationship** заметки.  
  
-   Укажите **xs: keyref** без **msdata: constraintonly** заметки.  
  
## <a name="nested-complex-types"></a>Вложенные сложные типы  
 Определения вложенных сложных типов в схеме указывают на связь элементов по модели «родитель-потомок». В следующем фрагменте схемы XML показано, что **OrderDetail** является дочерним элементом элемента **порядок** элемент.  
  
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
  
 Процесс сопоставления схем XML создает таблицы в **набора данных** , соответствующие вложенным сложным типам в схеме. Он также создает дополнительные столбцы, которые используются в качестве родительского**-** дочерних столбцов в созданных таблицах. Обратите внимание, что их родительский**-** дочерние столбцы задают связи, который не так же, как и при указании ограничений primary key/foreign key.  
  
## <a name="msdatarelationship-annotation"></a>Заметка msdata:Relationship  
 **Msdata: Relationship** заметки можно явно указать иерархические отношения между элементами в схеме, которые не являются вложенными. В следующем примере показана структура **связь** элемент.  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Атрибуты **msdata: Relationship** заметки идентификации элементов, входящую в связь родитель потомок, а также как **parentkey** и **childkey** элементы и атрибуты, участвующие в связи. Процесс сопоставления использует эти сведения для создания таблиц в **набора данных** и для создания первичного/внешнего ключа связи между этими таблицами.  
  
 Например, следующий фрагмент схемы задает **порядок** и **OrderDetail** элементов того же уровня (не вложенные). Схема задает **msdata: Relationship** заметки, который указывает связь «родители потомки» между этими элементами. В этом случае явную связь необходимо указать с помощью **msdata: Relationship** заметки.  
  
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
  
 Процесс сопоставления использует **связь** элемент, чтобы создать отношение "родитель потомок" между **OrderNumber** столбца в **порядок** таблицы и **OrderNo** столбца в **OrderDetail** в таблицу **набора данных**. Процесс сопоставления только указывает связь, он не задает автоматически ограничения значений в этих столбцах подобно ограничениям первичного/внешнего ключа в реляционных базах данных.  
  
### <a name="in-this-section"></a>В этом разделе  
 [Сопоставление неявных отношений между вложенными элементами схемы](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 Описание ограничений и связей, неявно создаваемых в **набора данных** при в схеме XML встречаются вложенные элементы.  
  
 [Сопоставление отношений, заданных для вложенных элементов](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 Описание способов явной установки связей в **набора данных** для вложенных элементов в схеме XML.  
  
 [Указание отношений между элементами без вложенности](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 Описывает создание отношений в **набора данных** между элементами схемы XML, которые не являются вложенными.  
  
### <a name="related-sections"></a>Связанные разделы  
 [Наследование реляционной структуры DataSet от схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Описывает реляционную структуру, или схему, **набора данных** , созданную из схемы языка определения схемы XML.  
  
 [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы схемы XML, используемые для создания ограничений уникального и внешнего ключа в **набора данных**.  
  
## <a name="see-also"></a>См. также  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
