---
title: "Сопоставления типов данных Oracle | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d2521bcc-0051-4f35-8be3-e8723edeaf6f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
---
# Сопоставления типов данных Oracle
В приведенной ниже таблице показаны выводимые типы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для типов данных поставщика данных .NET Framework для Oracle \(<xref:System.Data.OracleClient>\). Приведены также типизированные методы доступа для <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Тип Oracle|Тип [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]|Типизированный метод доступа [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]|Типизированный метод доступа OracleType|  
|----------------|---------------------------------------------------------------------|----------------------------------------------------------------------------------------------|---------------------------------------------|  
|BFILE|Byte\[\]|GetBytes\(\)|GetOracleBFile\(\)|  
|BLOB|Byte\[\]|GetBytes\(\)|GetOracleLob\(\)|  
|CHAR|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|CLOB|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleLob\(\)|  
|DATE|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|FLOAT|Десятичное число|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|INTEGER|Десятичное число|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|INTERVAL YEAR TO MONTH \*|Int32|GetInt32\(\)|GetOracleMonthSpan\(\)|  
|INTERVAL DAY TO SECOND \*|TimeSpan|GetTimeSpan\(\)|GetOracleTimeSpan\(\)|  
|LONG|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|LONG RAW|Byte\[\]|GetBytes\(\)|GetOracleBinary\(\)|  
|NCHAR|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|NCLOB|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleLob\(\)|  
|NUMBER|Десятичное число|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|NVARCHAR2|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|RAW|Byte\[\]|GetBytes\(\)|GetOracleBinary\(\)|  
|REF CURSOR||||  
|ROWID|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|TIMESTAMP \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|TIMESTAMP WITH LOCAL TIME ZONE \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|TIMESTAMP WITH TIME ZONE \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|UNSIGNED INTEGER|Десятичное число|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|VARCHAR2|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
  
 \* Указанный тип Oracle доступен только при использовании программного обеспечения Oracle 9i как для клиента, так и для сервера.  
  
 \*\* Тип данных NUMBER, применяемый в СУБД Oracle, может иметь максимум 38 значащих цифр. Тип [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]`decimal` ограничен 28 разрядами. Чтение типа данных Oracle NUMBER в тип [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]`decimal` приводит к вызову исключения `OverflowException` для значения NUMBER, длина которого превышает 28 разрядов. Если значение типа NUMBER Oracle считывается из `OracleDataReader`, рекомендуется вызывать типизированный метод доступа `GetOracleNumber`, который возвращает значения NUMBER Oracle как `OracleNumber`. При заполнении объекта `DataSet` можно использовать событие `FillError`, чтобы определить, произошло ли исключение `OverflowException`, и предпринять необходимые действия. Дополнительные сведения о событии `FillError` см. в разделе [Обработка событий DataAdapter](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## См. также  
 [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [Получение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)