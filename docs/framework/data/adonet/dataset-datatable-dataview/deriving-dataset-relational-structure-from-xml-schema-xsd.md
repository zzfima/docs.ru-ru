---
title: Наследование реляционной структуры набора данных от схемы XML (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: ef77030b4e847f91fea074b68e223ac622539048
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040105"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Наследование реляционной структуры набора данных от схемы XML (XSD)
В этом разделе приведены общие сведения о построении реляционной схемы `DataSet` на основе документа схемы на языке XSD. Как правило, для каждого `complexType` дочернего элемента в элементе Schema создается таблица в `DataSet`. Структура таблицы задается определением сложного типа. Таблицы создаются в `DataSet` для элементов верхнего уровня в схеме. Однако таблица создается только для элемента `complexType` верхнего уровня, если элемент `complexType` вложен в другой элемент `complexType`. в этом случае вложенный элемент `complexType` сопоставляется с `DataTable` в `DataSet`.  
  
 Дополнительные сведения о XSD см. в разделе консорциум W3C (W3C) [XML-схема, часть 0: рекомендации по основам](https://www.w3.org/TR/xmlschema-0/), [рекомендации по схеме XML Part 1:](https://www.w3.org/TR/xmlschema-1/)Structures и [XML Schema, часть 2: рекомендации по типам](https://www.w3.org/TR/xmlschema-2/)данных.  
  
 В следующем примере показана схема XML, где `customers` является дочерним элементом элемента `MyDataSet`, который является элементом **DataSet** .  
  
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
> Если элемент `customers` имеет простой тип данных схемы XML, такой как **Integer**, таблица не создается. Таблицы создаются только для элементов верхнего уровня, которые являются сложными типами.  
  
 В следующей схеме XML элемент **Schema** имеет два дочерних элемента, `InStateCustomers` и `OutOfStateCustomers`.  
  
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
  
 Дочерние элементы `InStateCustomers` и `OutOfStateCustomers` являются элементами сложного типа (`customerType`). Таким образом, процесс сопоставления создает следующие две идентичные таблицы в `DataSet`.  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>Содержание  
 [Сопоставление ограничений схемы XML (XSD) с ограничениями DataSet](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описывает элементы XML-схемы, используемые для создания ограничений UNIQUE и FOREIGN KEY в `DataSet`.  
  
 [Создание отношений DataSet из схемы XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Описывает элементы XML-схемы, используемые для создания связей между столбцами таблицы в `DataSet`.  
  
 [Ограничения и отношения схемы XML](xml-schema-constraints-and-relationships.md)  
 Описывает, как неявным образом создаются связи при использовании элементов схемы XML для создания ограничений в `DataSet`.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Использование XML в наборах данных](using-xml-in-a-dataset.md)  
 Описывает, как загружать и сохранять реляционную структуру и данные в `DataSet` в виде XML-данных.  
  
## <a name="see-also"></a>См. также

- [Общие сведения об ADO.NET](../ado-net-overview.md)
