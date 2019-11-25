---
title: Создание клиентского приложения .NET Framework (краткое руководство по службам данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 4beaba24e42b15ebc45ece6e5319a2b14df54ab6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975384"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a>Создание клиентского приложения .NET Framework (краткое руководство по службам данных WCF)

Это последняя задача краткого руководства по WCF Data Services. В этой задаче вы добавите в решение консольное приложение, добавите ссылку на веб-канал Open Data Protocol (OData) в это новое клиентское приложение и получите доступ к каналу OData из клиентского приложения с помощью созданных клиентских классов службы данных и клиента. Libraries.

> [!NOTE]
> Для доступа к каналу данных наличие клиентского приложения на основе .NET Framework необязательно. Доступ к службе данных может осуществляться любым компонентом приложения, использующим канал OData. Дополнительные сведения см. [в разделе Использование службы данных в клиентском приложении](using-a-data-service-in-a-client-application-wcf-data-services.md).

## <a name="to-create-the-client-application-by-using-visual-studio"></a>Создание клиентского приложения в среде Visual Studio

1. В **Обозреватель решений**щелкните решение правой кнопкой мыши, выберите **Добавить**, а затем — **Новый проект**.

2. В левой области выберите **установленные** > [**Visual C#**  или **Visual Basic**] > **Рабочий стол Windows**, а затем выберите шаблон **приложения WPF** .

3. Введите `NorthwindClient` в поле имя проекта, а затем нажмите кнопку **ОК**.

4. Откройте файл MainWindow.xaml и замените XAML-код следующим кодом.

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a>Добавление в проект ссылки на службу данных

1. В **Обозреватель решений**щелкните правой кнопкой мыши проект узлом NorthwindClient, выберите **Добавить** > **ссылку на службу**, а затем нажмите кнопку **обнаружить**.

     При этом отображается служба данных Northwind, созданная в первой задаче.

2. В текстовом поле **пространство имен** введите `Northwind`и нажмите кнопку **ОК**.

     При этом в проект добавляется новый файл кода, содержащий классы данных, которые используются для обращения и взаимодействия с ресурсами службы данных как с объектами. Классы данных создаются в пространстве имен `NorthwindClient.Northwind`.

## <a name="to-access-data-service-data-in-the-wpf-application"></a>Обращение к данным службы данных в приложении WPF

1. В **Обозреватель решений** в разделе **узлом NorthwindClient**щелкните правой кнопкой мыши проект и выберите команду **Добавить ссылку**.

2. В диалоговом окне **Добавление ссылки** перейдите на вкладку **.NET** , выберите сборку System. Data. Services. Client. dll и нажмите кнопку **ОК**.

3. В **Обозреватель решений** в разделе **узлом NorthwindClient**откройте кодовую страницу файла MainWindow. XAML и добавьте следующую инструкцию `using` (`Imports` в Visual Basic).

    [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
    [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

4. Вставьте следующий код, запрашивающий службу данных и привязывающий результат к коллекции <xref:System.Data.Services.Client.DataServiceCollection%601> класса `MainWindow`.

    > [!NOTE]
    > Имя узла `localhost:12345` нужно заменить на сервер и порт, на котором размещен экземпляр службы данных Northwind.

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

5. Вставьте следующий код, сохраняющий изменения, в класс `MainWindow`.

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a>Сборка и запуск приложения NothwindClient

1. В **Обозреватель решений**щелкните правой кнопкой мыши проект узлом NorthwindClient и выберите **Назначить запускаемым проектом**.

2. Нажмите клавишу **F5** , чтобы запустить приложение.

     При этом выполняется сборка решения и запуск клиентского приложения. Данные извлекаются из службы данных и отображаются в консоли.

3. Измените значение в столбце **количество** сетки данных и нажмите кнопку **сохранить**.

     Изменения будут сохранены в службе данных.

    > [!NOTE]
    > Эта версия приложения NorthwindClient не поддерживает добавление и удаление сущностей.

## <a name="next-steps"></a>Следующие шаги

Вы успешно создали клиентское приложение, которое обращается к примеру веб-канала OData Northwind. Вы также выполнили WCF Data Services быстрый запуск.

Дополнительные сведения о доступе к каналу OData из .NET Framework приложения см. в разделе [WCF Data Services Client Library](wcf-data-services-client-library.md).

## <a name="see-also"></a>См. также

- [Начало работы](getting-started-with-wcf-data-services.md)
- [Ресурсы](wcf-data-services-resources.md)
