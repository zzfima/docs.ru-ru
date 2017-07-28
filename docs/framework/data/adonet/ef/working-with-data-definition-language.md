---
title: "Работа с языком описания данных DDL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Работа с языком описания данных DDL
Начиная с версии [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 4, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] поддерживает язык описания данных DDL.  Это позволяет создавать и удалять экземпляры базы данных с использованием строки подключения и метаданных модели хранения \(SSDL\).  
  
 В следующих методах в <xref:System.Data.Objects.ObjectContext> с помощью строки соединения и содержимого SSDL выполняются следующие задачи: создание базы данных, удаление базы данных, проверка наличия базы данных и просмотр сформированного скрипта DDL.  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  Предполагается наличие достаточных разрешений для выполнения команд DDL.  
  
 Ранее указанные методы делегируют большую часть работы базовому поставщику данных ADO.NET.  Поставщик отвечает за соблюдение соглашения об именах, применяемых при создании объектов базы данных, в соответствии с правилами, используемыми для запросов и обновлений.  
  
 В следующем примере показано, как создать базу данных по существующей модели.  Кроме того, новый объект сущности добавляется в контекст объекта, а затем сохраняется в базе данных.  
  
## Процедуры  
  
#### Определение базы данных по существующей модели  
  
1.  Создайте консольное приложение.  
  
2.  Добавьте существующую модель в приложение.  
  
    1.  Добавьте пустую модель с именем `SchoolModel`.  Сведения о создании пустой модели см. в разделе [How to: Create a New .edmx File](http://msdn.microsoft.com/ru-ru/beb8189e-e51c-4051-839c-9902c224abf2).  
  
     В проект будет добавлен файл SchoolModel.edmx.  
  
    1.  Скопируйте концептуальную модель, модель хранения и содержимое о сопоставлении для модели School из раздела [School Model](http://msdn.microsoft.com/ru-ru/859a9587-81ea-4a45-9bc0-f8d330e1adac).  
  
    2.  Откройте файл SchoolModel.edmx и вставьте нужное содержимое в тегах `edmx:Runtime`.  
  
3.  Добавьте следующий код в функцию main.  Этот код инициализирует строку подключения с сервером базы данных, просматривает скрипт DDL, создает базу данных, добавляет новую сущность в контекст и сохраняет изменения в базе данных.  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]