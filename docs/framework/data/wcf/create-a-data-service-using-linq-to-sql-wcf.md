---
title: Практическое руководство. Создание службы данных с помощью LINQ to SQL источника данных (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: 7a1075b680ec3310e1bd8d712579872333c6ebed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791051"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a>Практическое руководство. Создание службы данных с помощью LINQ to SQL источника данных (WCF Data Services)

WCF Data Services предоставляет данные сущности в качестве службы данных. Поставщик отражения позволяет определить модель данных, основанную на любом классе, который предоставляет члены, возвращающие <xref:System.Linq.IQueryable%601> реализацию. Для выполнения обновлений данных в источнике данных эти классы должны также реализовать интерфейс <xref:System.Data.Services.IUpdatable>. Дополнительные сведения см. в разделе [поставщики служб данных](data-services-providers-wcf-data-services.md). В этом разделе показано, как создать классы LINQ to SQL, обращающиеся к образцу базы данных Northwind с помощью поставщика, а также как создать службу данных на основе этих классов.

## <a name="to-add-linq-to-sql-classes-to-a-project"></a>Добавление в проект объектов классов LINQ to SQL

1. В Visual Basic C# или приложении в меню **проект** выберите команду **добавить** > **новый элемент**.

2. Щелкните шаблон **LINQ to SQL классы** .

3. Измените имя на **Northwind. dbml**.

4. Нажмите кнопку **Добавить**.

     Файл Northwind.dbml добавляется в проект и открывается реляционный конструктор объектов.

5. В**Обозреватель базы данных** **сервера**/в разделе Northwind разверните узел **таблицы** и перетащите `Customers` таблицу на Реляционный конструктор объектов (конструктор O/R).

     При этом в области конструктора создается и отображается класс сущностей `Customer`.

6. Повторите шаг 6 для таблиц `Orders`, `Order_Details` и `Products`.

7. Щелкните правой кнопкой мыши новый DBML-файл, представляющий классы LINQ to SQL, и выберите пункт **Просмотреть код**.

     При этом создается новая страница с выделенным кодом Northwind.cs, содержащая разделяемый класс, производный от класса <xref:System.Data.Linq.DataContext>, представляющего в данном случае контекст `NorthwindDataContext`.

8. Замените содержимое файла Northwind.cs следующим кодом. Этот код реализует поставщик отражения, расширяя контекст <xref:System.Data.Linq.DataContext> и классы данных, сформированные LINQ to SQL.

     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.vb#linq2sqlprovider)]

### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a>Создание службы данных с использованием модели данных на основе LINQ to SQL

1. В **Обозреватель решений**щелкните правой кнопкой мыши имя проекта ASP.NET и выберите команду **Добавить** > **новый элемент**.

2. В диалоговом окне **Добавление нового элемента** выберите шаблон **WCF Data Service** из категории **веб** .

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Шаблон **службы данных WCF** доступен в visual Studio 2015, но не в visual Studio 2017.

3. Укажите имя службы и нажмите кнопку **ОК**.

     В Visual Studio для новой службы создаются файлы разметки и кодов XML. По умолчанию открывается окно редактора кода.

4. В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindDataContext`.

5. В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:

     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.svc.vb#enableaccess)]

     Это позволяет авторизованным клиентам осуществлять доступ к ресурсам трех указанных наборов сущностей.

6. Чтобы протестировать службу данных Northwind. svc с помощью веб-браузера, следуйте инструкциям в разделе [обращение к службе из веб-браузера](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).

## <a name="see-also"></a>См. также

- [Практическое руководство. Создание службы данных с помощью источника данных ADO.NET Entity Framework](create-a-data-service-using-an-adonet-ef-data-wcf.md)
- [Практическое руководство. Создание службы данных с помощью поставщика отражения](create-a-data-service-using-rp-wcf-data-services.md)
- [Поставщики служб данных](data-services-providers-wcf-data-services.md)
