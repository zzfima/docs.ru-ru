---
title: Наследование реляционной структуры набора данных от схемы XML (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 7599577c4e0f485e336e7f79a6c3bd17f0f0c316
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Наследование реляционной структуры набора данных от схемы XML (XSD)
В этом разделе приведены общие сведения о построении реляционной схемы `DataSet` на основе документа схемы на языке XSD. Как правило, для каждого `complexType` дочерний элемент элемента схемы, создается таблица, в `DataSet`. Структура таблицы задается определением сложного типа. Таблицы создаются в `DataSet` для элементов верхнего уровня в схеме. Однако таблица создается только для верхнего уровня `complexType` элемент при `complexType` элемент вложен в другой `complexType` случае вложенный элемент, в котором `complexType` элемент сопоставляется `DataTable` в `DataSet`.  
  
 Дополнительные сведения о языке XSD см. в разделе World Wide Web Consortium (W3C) XML Schema Part 0: Primer Recommendation, XML Schema Part 1: структурные рекомендации и XML Schema Part 2: рекомендации по типам данных, расположенном в [ http://www.w3.org/ ](http://www.w3.org/TR/).  
  
 Ниже приведен пример XML-схемы где `customers` является дочерним элементом элемента `MyDataSet` элемент, являющийся **DataSet** элемента.  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 В предыдущем примере элемент `customers` является элементом сложного типа. Поэтому проводится синтаксический анализ определения сложного типа, а процесс сопоставления создает следующую таблицу.  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 Тип данных каждого столбца в таблице получается из типа схемы XML соответствующего элемента или указанного атрибута.  
  
> [!NOTE]
>  Если элемент `customers` — простого типа данных XML-схемы, таких как **целое**, то таблица не создается. Таблицы создаются только для элементов верхнего уровня, которые являются сложными типами.  
  
 В следующей схеме XML **схемы** элемент имеет два дочерних элемента: `InStateCustomers` и `OutOfStateCustomers`.  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 Дочерние элементы `InStateCustomers` и `OutOfStateCustomers` являются элементами сложного типа (`customerType`). Таким образом, процесс сопоставления создает две следующие одинаковые таблицы в `DataSet`.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>В этом разделе  
 [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы схемы XML, используемые для создания ограничений уникального и внешнего ключа в `DataSet`.  
  
 [Создание отношений DataSet из схемы XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Описывает элементы схемы XML, используемых для создания связей между столбцами таблиц в `DataSet`.  
  
 [Ограничения и отношения схемы XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 Описывает, каким образом неявного создания связей при использовании элементов схемы XML для создания ограничений в `DataSet`.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Использование XML в наборах данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Описывает, как для загрузки и сохранения реляционной структуры и данных в `DataSet` как XML-данных.  
  
## <a name="see-also"></a>См. также  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
