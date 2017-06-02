---
title: "Как сделать файлы модели и сопоставления внедренными ресурсами | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
  - "jsharp"
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как сделать файлы модели и сопоставления внедренными ресурсами
Платформа [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] позволяет развертывать файлы моделей и сопоставления как внедренные ресурсы приложения.  Сборка с внедренными файлами моделей и сопоставления должна быть загружена в том же домене приложения, что и соединение сущности.  Для получения дополнительной информации см. [Строки соединения](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  По умолчанию средства [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] внедряют файлы модели и сопоставления. При определении файлов модели и сопоставления вручную следует использовать данную процедуру для обеспечения того, чтобы файлы были развернуты как внедренные ресурсы совместно с приложением [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
>  Чтобы обеспечить поддержку внедренных ресурсов, необходимо повторить эту процедуру после каждого изменения файлов модели и сопоставления.  
  
### Внедрение файлов модели и сопоставления  
  
1.  В окне **Обозревателя решений** выберите файл концептуальной модели с расширением CSDL.  
  
2.  В области **Свойства** задайте для параметра **Действие сборки** значение **Внедренный ресурс**.  
  
3.  Повторите шаги 1 и 2 для файла хранения с расширением SSDL и файла сопоставления с расширением MSL.  
  
4.  В окне **Обозреватель решений** дважды щелкните файл App.config, а затем задайте параметр `Metadata` в атрибуте `connectionString` в одном из следующих форматов.  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     Для получения дополнительной информации см. [Строки соединения](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  
  
## Пример  
 В следующей строке соединения применяется ссылка на внедренные файлы модели и сопоставления для модели [AdventureWorks Sales](http://msdn.microsoft.com/ru-ru/f16cd988-673f-4376-b034-129ca93c7832).  Эта строка соединения хранится в файле App.config проекта.  
  
  
  
## См. также  
 [Моделирование и сопоставление](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)   
 [Как определить строки соединения.](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)   
 [Как построить строку соединения EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)   
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/ru-ru/91076853-0881-421b-837a-f582f36be527)