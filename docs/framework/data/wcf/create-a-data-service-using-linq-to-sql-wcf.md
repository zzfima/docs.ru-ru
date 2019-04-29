---
title: Практическое руководство. Создание службы данных с использованием LINQ к источнику данных SQL (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: b33eb8f470fc8ce3851c7843de992b39e86ce018
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765823"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a>Практическое руководство. Создание службы данных с использованием LINQ к источнику данных SQL (службы данных WCF)

Службы данных WCF предоставляет данные сущности в виде службы данных. Поставщик отражения позволяет определить модель данных, основанный на любой класс, который предоставляет члены, которые возвращают <xref:System.Linq.IQueryable%601> реализации. Для выполнения обновлений данных в источнике данных эти классы должны также реализовать интерфейс <xref:System.Data.Services.IUpdatable>. Дополнительные сведения см. в разделе [поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md). В этом разделе показано, как создать классы LINQ to SQL, обращающиеся к образцу базы данных Northwind с помощью поставщика, а также как создать службу данных на основе этих классов.

## <a name="to-add-linq-to-sql-classes-to-a-project"></a>Добавление в проект объектов классов LINQ to SQL

1. Из приложения Visual Basic или C#, на **проекта** меню, щелкните **добавить** > **новый элемент**.

2. Нажмите кнопку **LINQ to SQL Classes** шаблона.

3. Измените имя на **Northwind.dbml**.

4. Нажмите кнопку **Добавить**.

     Файл Northwind.dbml добавляется в проект и открывается реляционный конструктор объектов.

5. В **Server**/**обозреватель баз данных**, в окне Northwind разверните **таблиц** и перетащите `Customers` таблицы на реляционный конструктор объектов (O/R Конструктор).

     При этом в области конструктора создается и отображается класс сущностей `Customer`.

6. Повторите шаг 6 для таблиц `Orders`, `Order_Details` и `Products`.

7. Щелкните правой кнопкой мыши новый DBML-файл, представляющий LINQ к классам SQL и нажмите кнопку **Просмотр кода**.

     При этом создается новая страница с выделенным кодом Northwind.cs, содержащая разделяемый класс, производный от класса <xref:System.Data.Linq.DataContext>, представляющего в данном случае контекст `NorthwindDataContext`.

8. Замените содержимое файла Northwind.cs следующим кодом. Этот код реализует поставщик отражения, расширяя контекст <xref:System.Data.Linq.DataContext> и классы данных, сформированные LINQ to SQL.

     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.vb#linq2sqlprovider)]

### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a>Создание службы данных с использованием модели данных на основе LINQ to SQL

1. В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и нажмите кнопку **добавить** > **новый элемент**.

2. В **Добавление нового элемента** выберите **WCF-сервиса данных** шаблон из **Web** категории.

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > **WCF-сервиса данных** шаблон доступен в Visual Studio 2015, но не в Visual Studio 2017.

3. Укажите имя для службы и нажмите кнопку **ОК**.

     В Visual Studio для новой службы создаются файлы разметки и кодов XML. По умолчанию открывается окно редактора кода.

4. В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindDataContext`.

5. В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:

     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.svc.vb#enableaccess)]

     Это позволяет авторизованным клиентам осуществлять доступ к ресурсам трех указанных наборов сущностей.

6. Чтобы проверить службы данных Northwind.svc с помощью веб-браузер, следуйте инструкциям в разделе [доступа к службе из веб-браузер](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).

## <a name="see-also"></a>См. также

- [Практическое руководство. Создание службы данных с использованием источника данных ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
- [Практическое руководство. Создание службы данных с помощью поставщика отражения](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)
- [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)