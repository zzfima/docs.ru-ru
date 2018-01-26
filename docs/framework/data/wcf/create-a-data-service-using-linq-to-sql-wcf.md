---
title: "Практическое руководство. Создание службы данных с использованием источника данных LINQ to SQL (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 755df7c86d80214ded4e8c9534f88910a171c7a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a>Практическое руководство. Создание службы данных с использованием источника данных LINQ to SQL (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] предоставляет данные сущности в виде службы данных. Поставщик отражения позволяет определить модель данных, основанный на любой класс, который предоставляет члены, возвращающие <xref:System.Linq.IQueryable%601> реализации. Для выполнения обновлений данных в источнике данных эти классы должны также реализовать интерфейс <xref:System.Data.Services.IUpdatable>. Дополнительные сведения см. в разделе [поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md). В этом разделе показано, как создать классы LINQ to SQL, обращающиеся к образцу базы данных Northwind с помощью поставщика, а также как создать службу данных на основе этих классов.  
  
### <a name="to-add-linq-to-sql-classes-to-a-project"></a>Добавление в проект объектов классов LINQ to SQL  
  
1.  Из приложения Visual Basic или C# на **проекта** меню, нажмите кнопку **Добавление нового элемента**.  
  
2.  Нажмите кнопку **LINQ to SQL Classes** шаблона.  
  
3.  Измените имя на **Northwind.dbml**.  
  
4.  Нажмите кнопку **Добавить**.  
  
     Файл Northwind.dbml добавляется в проект и открывается реляционный конструктор объектов.  
  
5.  В **сервера**/**обозреватель баз данных**, в окне Northwind разверните **таблиц** и перетащите `Customers` таблицы на реляционный конструктор объектов (O/R Конструктор).  
  
     При этом в области конструктора создается и отображается класс сущностей `Customer`.  
  
6.  Повторите шаг 6 для таблиц `Orders`, `Order_Details` и `Products`.  
  
7.  Щелкните правой кнопкой мыши новый DBML-файл, представляющий LINQ для классов SQL и нажмите кнопку **Просмотр кода**.  
  
     При этом создается новая страница с выделенным кодом Northwind.cs, содержащая разделяемый класс, производный от класса <xref:System.Data.Linq.DataContext>, представляющего в данном случае контекст `NorthwindDataContext`.  
  
8.  Замените содержимое файла Northwind.cs следующим кодом. Этот код реализует поставщик отражения, расширяя контекст <xref:System.Data.Linq.DataContext> и классы данных, сформированные LINQ to SQL.  
  
     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.vb#linq2sqlprovider)]  
  
### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a>Создание службы данных с использованием модели данных на основе LINQ to SQL  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавление нового элемента**.  
  
2.  В **Добавление нового элемента** выберите **службы данных WCF**.  
  
3.  Задайте имя для службы и нажмите кнопку **ОК**.  
  
     В Visual Studio для новой службы создаются файлы разметки и кодов XML. По умолчанию открывается окно редактора кода.  
  
4.  В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindDataContext`.  
  
5.  В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:  
  
     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria linq provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria linq provider/vb/northwind.svc.vb#enableaccess)]  
  
     Это позволяет авторизованным клиентам осуществлять доступ к ресурсам трех указанных наборов сущностей.  
  
6.  Для тестирования службы Northwind.svc данных с помощью веб-браузера, следуйте инструкциям в разделе [доступа к службе из веб-браузер](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Создание службы данных с использованием источника данных Entity Framework ADO.NET](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)  
 [Практическое руководство. Создание службы данных с использованием поставщика отражений](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
