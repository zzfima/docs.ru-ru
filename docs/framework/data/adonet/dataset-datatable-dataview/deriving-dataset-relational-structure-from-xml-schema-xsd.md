---
title: "Выведение реляционной структуры DataSet из схемы XML (XSD) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Выведение реляционной структуры DataSet из схемы XML (XSD)
В этом разделе приведены общие сведения о построении реляционной схемы <xref:System.Data.DataSet> на основе документа схемы на языке XSD.  В общем случае для каждого дочернего элемента **complexType** элемента схемы в наборе **DataSet** создается таблица.  Структура таблицы задается определением сложного типа.  В наборе **DataSet** таблицы создаются для элементов верхнего уровня в схеме.  Однако таблица создается для элемента **complexType** верхнего уровня, только когда элемент **complexType** вложен в другой элемент **complexType**. В этом случае вложенный элемент **complexType** сопоставлен с <xref:System.Data.DataTable> в наборе **DataSet**.  
  
 Дополнительные сведения о языке XSD см. в документах консорциума W3C «XML Schema Part 0: Primer Recommendation», «XML Schema Part 1: Structures Recommendation» и «XML Schema Part 2: Datatypes Recommendation», которые доступны по адресу [http:\/\/www.w3.org\/](http://www.w3.org/TR/).  
  
 В следующем примере показана схема XML, где `customers` является дочерним элементом элемента `MyDataSet`, который является элементом **DataSet**.  
  
```  
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
  
 В предыдущем примере элемент `customers` является элементом сложного типа.  Поэтому проводится синтаксический анализ определения сложного типа, а процесс сопоставления создает следующую таблицу.  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 Тип данных каждого столбца в таблице получается из типа схемы XML соответствующего элемента или указанного атрибута.  
  
> [!NOTE]
>  Если элемент `customers` является элементом простого типа данных схемы XML, например **integer**, то таблица не создается.  Таблицы создаются только для элементов верхнего уровня, которые являются сложными типами.  
  
 В следующей схеме XML элемент **Schema** имеет два дочерних элемента: `InStateCustomers` и `OutOfStateCustomers`.  
  
```  
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
  
 Дочерние элементы `InStateCustomers` и `OutOfStateCustomers` являются элементами сложного типа \(`customerType`\).  Поэтому процесс сопоставления формирует в наборе **DataSet** две следующие одинаковые таблицы.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## В этом подразделе  
 [Сопоставление ограничений схемы XML \(XSD\) с ограничениями DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Описание элементов схемы XML, используемых для создания ограничений уникального и внешнего ключа в **DataSet**.  
  
 [Формирование связей DataSet на основе схемы XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Описание элементов схемы XML, используемых для создания связей между столбцами таблиц в **DataSet**.  
  
 [Ограничения и связи схемы XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 Описание неявного создания связей при использовании элементов схемы XML для создания ограничений в наборе **DataSet**.  
  
## Связанные подразделы  
 [Использование XML в DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Описание загрузки и сохранения реляционной структуры и данных в наборе **DataSet** как XML\-данных.  
  
## См. также  
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)