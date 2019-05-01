---
title: Практическое руководство. Как создать модель объектов в виде внешнего файла
ms.date: 03/30/2017
ms.assetid: 2496fa06-3df4-4ecb-86c4-70a49ea08565
ms.openlocfilehash: 2e439cd6628daa5b574be2049393dc2964896679
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033752"
---
# <a name="how-to-generate-the-object-model-as-an-external-file"></a>Практическое руководство. Как создать модель объектов в виде внешнего файла
В качестве альтернативы сопоставления на основе атрибутов с помощью инструмента командной строки SQLMetal можно создать собственную объектную модель в виде внешнего файла XML. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md). За счет использования внешнего XML-файла сопоставления можно снизить перегруженность кода. Кроме того, можно изменить поведение, отредактировав внешний файл без повторной компиляции двоичных файлов приложения. Дополнительные сведения см. в разделе [внешнего сопоставления](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
> [!NOTE]
>  [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] не поддерживает создание внешнего файла сопоставления.  
  
## <a name="example"></a>Пример  
 Следующая команда формирует внешний файл сопоставления из образца базы данных Northwind.  
  
```  
sqlmetal /server:myserver /database:northwind /map:externalfile.xml  
```  
  
## <a name="example"></a>Пример  
 Следующий фрагмент внешнего файла сопоставления показывает сопоставление для таблицы Customers в образце базы данных Northwind. Этот фрагмент создан путем запуска программы SQLMetal с **/map** параметр.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Database xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Name="northwnd">  
  <Table Name="Customers">  
    <Type Name=".Customer">  
      <Column Name="CustomerID" Member="CustomerID" Storage="_CustomerID" DbType="NChar(5) NOT NULL" CanBeNull="False" IsPrimaryKey="True" />  
      <Column Name="CompanyName" Member="CompanyName" Storage="_CompanyName" DbType="NVarChar(40) NOT NULL" CanBeNull="False" />  
      <Column Name="ContactName" Member="ContactName" Storage="_ContactName" DbType="NVarChar(30)" />  
      <Column Name="ContactTitle" Member="ContactTitle" Storage="_ContactTitle" DbType="NVarChar(30)" />  
      <Column Name="Address" Member="Address" Storage="_Address" DbType="NVarChar(60)" />  
      <Column Name="City" Member="City" Storage="_City" DbType="NVarChar(15)" />  
      <Column Name="Region" Member="Region" Storage="_Region" DbType="NVarChar(15)" />  
      <Column Name="PostalCode" Member="PostalCode" Storage="_PostalCode" DbType="NVarChar(10)" />  
      <Column Name="Country" Member="Country" Storage="_Country" DbType="NVarChar(15)" />  
      <Column Name="Phone" Member="Phone" Storage="_Phone" DbType="NVarChar(24)" />  
      <Column Name="Fax" Member="Fax" Storage="_Fax" DbType="NVarChar(24)" />  
      <Association Name="FK_CustomerCustomerDemo_Customers" Member="CustomerCustomerDemos" Storage="_CustomerCustomerDemos" ThisKey="CustomerID" OtherTable="CustomerCustomerDemo" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
      <Association Name="FK_Orders_Customers" Member="Orders" Storage="_Orders" ThisKey="CustomerID" OtherTable="Orders" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
    </Type>  
  </Table>  
</Database>  
```  
  
## <a name="see-also"></a>См. также

- [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [Внешнее сопоставление](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
- [Практическое руководство. Создание модели объектов на языке Visual Basic или C#](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
