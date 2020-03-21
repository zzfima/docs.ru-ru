---
title: Наследование реляционной структуры набора данных от схемы XML (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d32b5cb86bc5a138f9a5f438629d8e231be4ba94
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151173"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Наследование реляционной структуры набора данных от схемы XML (XSD)
В этом разделе приведены общие сведения о построении реляционной схемы `DataSet` на основе документа схемы на языке XSD. Как правило, `complexType` для каждого элемента элемента схемы создается `DataSet`таблица в . Структура таблицы задается определением сложного типа. Таблицы создаются `DataSet` в элементах верхнего уровня в схеме. Однако таблица создается только для `complexType` элемента `complexType` верхнего уровня, `complexType` когда элемент вложен внутри `complexType` другого элемента, `DataSet`и в этом случае вложенный элемент отображается в элементе `DataTable` .  
  
 Для получения дополнительной информации о XSD, см. World Wide Web консорциум (W3C) [XML Схема Часть 0: Праймер Рекомендация](https://www.w3.org/TR/xmlschema-0/), [XML Схема Часть 1: Структуры Рекомендации](https://www.w3.org/TR/xmlschema-1/), и [XML Схема Часть 2: Рекомендация по типам данных](https://www.w3.org/TR/xmlschema-2/).  
  
 Следующий пример демонстрирует XML Schema, где `customers` находится `MyDataSet` элемент ребенка элемента, который является элементом **DataSet.**  
  
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
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Тип данных каждого столбца в таблице получается из типа схемы XML соответствующего элемента или указанного атрибута.  
  
> [!NOTE]
> Если элемент `customers` имеет простой тип данных XML Schema, такой как **целый ряд,** таблица не генерируется. Таблицы создаются только для элементов верхнего уровня, которые являются сложными типами.  
  
 В следующей схеме XML элемент Schema имеет `InStateCustomers` два `OutOfStateCustomers` **элемента,** и .  
  
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
  
 Дочерние элементы `InStateCustomers` и `OutOfStateCustomers` являются элементами сложного типа (`customerType`). Таким образом, процесс отображения генерирует `DataSet`следующие две одинаковые таблицы в .  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>в этом разделе  
 [Сопоставление ограничений XML-схемы (XSD) с ограничениями набора данных](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы XML Schema, используемые для `DataSet`создания уникальных и внешних ключевых ограничений в .  
  
 [Создание отношений наборов данных из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Описывает элементы XML Schema, используемые для `DataSet`создания связей между столбиками таблицы в .  
  
 [Ограничения и отношения схемы XML](xml-schema-constraints-and-relationships.md)  
 Описывает, как неявно создаются отношения при использовании элементов `DataSet`XML Schema для создания ограничений в .  
  
## <a name="related-sections"></a>См. также  
 [Использование XML в наборах данных](using-xml-in-a-dataset.md)  
 Описывает, как загружать и сохранять реляционную структуру и данные в `DataSet` данных XML.  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об ADO.NET](../ado-net-overview.md)
