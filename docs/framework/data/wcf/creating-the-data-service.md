---
title: Создание службы данных WCF в Visual Studio
ms.date: 08/24/2018
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
ms.openlocfilehash: d23df38d479cb8f29f3e49225e96552ccdb84645
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64641140"
---
# <a name="create-the-data-service"></a>Создание службы данных

В этом разделе создайте образец службы данных, который использует службы данных WCF для предоставления [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канал, основанный на образце базы данных "Борей". Задача включает следующие основные шаги.

1. создайте веб-приложение ASP.NET;

2. Определение модели данных с использованием средств для работы с моделью EDM.

3. Добавление службы данных в веб-приложение.

4. Включите доступ к службе данных.

## <a name="create-the-aspnet-web-app"></a>Создание веб-приложения ASP.NET

1. В Visual Studio на **файл** меню, выберите **New** > **проекта**.

1. В **новый проект** диалоговое окно, в разделе Visual Basic или Visual C# выберите **Web** категории, а затем выберите **веб-приложение ASP.NET**.

1. Введите `NorthwindService` как имя проекта и выберите **ОК**.

1. В **новое веб-приложение ASP.NET** диалоговом окне выберите **пустой** , а затем выберите **ОК**.

1. (Необязательно) Укажите конкретный номер порта для веб-приложения. Примечание: номер порта `12345` используется в этой серии разделы краткого руководства.

    1. В **обозревателе решений**, щелкните правой кнопкой мыши на проекте ASP.NET, который вы только что создали и затем выберите **свойства**.

    2. Выберите **Web** и задайте значение **определенный порт** текстового поля, чтобы `12345`.

## <a name="define-the-data-model"></a>Определение модели данных

1. В **обозревателе решений**, щелкните правой кнопкой мыши имя проекта ASP.NET и нажмите кнопку **добавить** > **новый элемент**.

2. В **Добавление нового элемента** выберите **данных** категории, а затем выберите **ADO.NET Entity Data Model**.

3. Введите имя модели данных `Northwind.edmx`.

4. В **мастер моделей EDM**выберите **конструктор EF из базы данных**, а затем нажмите кнопку **Далее**.

5. Подключите модель данных в базу данных, выполнив одно из следующих действий, а затем нажмите кнопку **Далее**:

    - Если у вас нет подключения к базе данных уже настроена, нажмите кнопку **новое подключение** и создайте новое соединение. Дополнительные сведения см. в разделе [Как Создание подключений к базам данных SQL Server](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/s4yys16a(v=vs.90)). Этот экземпляр SQL Server должен содержать присоединенный образец базы данных Northwind.

         \- или -

    - Если имеется уже настроенное подключение к базе данных Northwind, выберите это подключение из списка.

6. На завершающей странице мастера установите флажки для всех таблиц базы данных и снимите флажки для представлений и хранимых процедур.

7. Нажмите кнопку **Готово** чтобы закрыть мастер.

## <a name="create-the-wcf-data-service"></a>Создание службы данных WCF

1. В **обозревателе решений**, правой кнопкой мыши проект ASP.NET и затем выберите **добавить** > **новый элемент**.

2. В **Добавление нового элемента** выберите **WCF-сервиса данных** шаблон элемента из **Web** категории.

   ![Шаблон элемента службы данных WCF в Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > **WCF-сервиса данных** шаблон доступен в Visual Studio 2015, но не в Visual Studio 2017.

3. Имя службы, введите `Northwind`.

     В Visual Studio для новой службы создаются файлы разметки и кодов XML. По умолчанию открывается окно редактора кода. В **обозревателе решений**, служба имеет имя Northwind с расширением *. svc.cs* или *. svc.vb*.

4. В коде службы данных замените комментарий `/* TODO: put your data source class name here */` в определении класса, задающего службу данных, типом контейнера сущностей модели данных, который в данном случае равен `NorthwindEntities`. Определение класса должно выглядеть следующим образом.

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

## <a name="enable-access-to-data-service-resources"></a>Разрешить доступ к ресурсам службы данных

1. В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:

     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]

     Это обеспечивает авторизованным клиентам доступ для чтения и записи к ресурсам указанных наборов сущностей.

    > [!NOTE]
    > Любой клиент, имеющий доступ к приложению ASP.NET, имеет также доступ к ресурсам, предоставляемым службой данных. Для предотвращения несанкционированного доступа к ресурсам производственной службы данных необходимо также установить защиту самого приложения. Дополнительные сведения см. в разделе [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).

## <a name="next-steps"></a>Следующие шаги

Вы успешно создали новую службу данных, предоставляющего канал OData, основанный на образце базы данных Northwind и включили доступ к каналу для клиентов, имеющих разрешения на веб-приложения ASP.NET. Далее необходимо запустить службу данных из Visual Studio и доступа к каналу путем отправки запросов HTTP GET через веб-браузер OData:

> [!div class="nextstepaction"]
> [Доступ к службе из веб-браузер](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

## <a name="see-also"></a>См. также

- [Средства модели EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))