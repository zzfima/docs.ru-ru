---
title: "Использование команд для изменения данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Использование команд для изменения данных
Используя поставщик данных .NET Framework, можно выполнять хранимые процедуры или инструкции языка описания данных DDL \(например, CREATE TABLE и ALTER COLUMN\) для выполнения операций со схемой в базе данных или в каталоге.  Эти команды не возвращают строк, как это делают запросы, так что для их обработки объект **Command** предоставляет **ExecuteNonQuery**.  
  
 Наряду с использованием **ExecuteNonQuery** для изменения схемы, этот метод может быть использован для обработки инструкций SQL, которые изменяют данные, но не возвращают строки, например инструкций INSERT, UPDATE и DELETE.  
  
 Хотя метод **ExecuteNonQuery** не возвращает строки, входные и выходные параметры, а также возвращаемые значения могут передаваться и возвращаться через коллекцию **Parameters** объекта **Command**.  
  
## В этом подразделе  
 [Обновление данных в источнике данных](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 Описывает выполнение команд или хранимых процедур, которые изменяют данные в базе данных.  
  
 [Выполнение операций над каталогами](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 Описывает выполнение команд, которые изменяют схему базы данных.  
  
## См. также  
 [Получение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)