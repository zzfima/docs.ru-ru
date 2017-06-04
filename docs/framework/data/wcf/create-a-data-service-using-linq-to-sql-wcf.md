---
title: "Как создать службу данных с помощью источника данных LINQ to SQL (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Службы WCF Data Services, LINQ to SQL"
  - "Службы WCF Data Services, поставщики"
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как создать службу данных с помощью источника данных LINQ to SQL (службы WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] предоставляет данные сущности в виде службы данных.  Поставщик отражения позволяет определить модель данных на основе любого класса, предоставляющего элементы, возвращаемые реализацией интерфейса <xref:System.Linq.IQueryable%601>.  Для выполнения обновлений данных в источнике данных эти классы должны также реализовать интерфейс <xref:System.Data.Services.IUpdatable>.  Для получения дополнительной информации см. [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  В этом разделе показано, как создать классы LINQ to SQL, обращающиеся к образцу базы данных Northwind с помощью поставщика, а также как создать службу данных на основе этих классов.  
  
### Добавление в проект объектов классов LINQ to SQL  
  
1.  Из приложения на Visual Basic или C\# в меню **Проект** щелкните по пункту **Добавить новый элемент**.  
  
2.  Выберите шаблон **LINQ to SQL Classes**.  
  
3.  Измените имя на Northwind.dbml.  
  
4.  Нажмите кнопку **Добавить**.  
  
     Файл Northwind.dbml добавляется в проект и открывается реляционный конструктор объектов.  
  
5.  В **обозревателе базы данных**\/**сервера** в окне Northwind разверните узел **Таблицы** и перетащите таблицу `Customers` в реляционный конструктор объектов.  
  
     При этом в области конструктора создается и отображается класс сущностей `Customer`.  
  
6.  Повторите шаг 6 для таблиц `Orders`, `Order_Details` и `Products`.  
  
7.  Щелкните правой кнопкой мыши DBML\-файл, представляющий классы запросов LINQ to SQL, и выберите команду **Просмотр кода**.  
  
     При этом создается новая страница с выделенным кодом Northwind.cs, содержащая разделяемый класс, производный от класса <xref:System.Data.Linq.DataContext>, представляющего в данном случае контекст `NorthwindDataContext`.  
  
8.  Замените содержимое файла Northwind.cs следующим кодом.  Этот код реализует поставщик отражения, расширяя контекст <xref:System.Data.Linq.DataContext> и классы данных, сформированные LINQ to SQL.  
  
     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]  
  
### Создание службы данных с использованием модели данных на основе LINQ to SQL  
  
1.  В **обозревателе решений** щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавить новый элемент**.  
  
2.  В диалоговом окне **Добавление нового элемента** выберите пункт **Служба данных WCF**.  
  
3.  Введите имя службы и нажмите кнопку **ОК**.  
  
     В Visual Studio для новой службы создаются файлы разметки и кодов XML.  По умолчанию открывается окно редактора кода.  
  
4.  В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindDataContext`.  
  
5.  В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:  
  
     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]  
  
     Это позволяет авторизованным клиентам осуществлять доступ к ресурсам трех указанных наборов сущностей.  
  
6.  Для проверки службы данных Northwind.svc с помощью веб\-браузера следуйте инструкциям в разделе [Доступ к службе из веб\-браузера](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## См. также  
 [Как создать службу данных с использованием источника данных ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)   
 [Как создать службу данных с помощью поставщика отражения](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)   
 [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)