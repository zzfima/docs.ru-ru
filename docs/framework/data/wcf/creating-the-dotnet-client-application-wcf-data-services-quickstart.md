---
title: "Создание клиентского приложения .NET Framework (краткое руководство по службам WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Создание клиентского приложения .NET Framework (краткое руководство по службам WCF Data Services)
Это последняя задача краткого руководства по службам [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  В этой задаче мы добавим в решение консольное приложение, добавим в это новое клиентское приложение ссылку на канал [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] и обратимся к каналу [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из клиентского приложения с помощью сформированных клиентских классов службы данных и клиентских библиотек.  
  
> [!NOTE]
>  Для доступа к каналу данных наличие клиентского приложения на основе .NET Framework необязательно.  Доступ к службе данных любой может получить, используя компонент приложения, реализующий канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Для получения дополнительной информации см. [Использование службы данных в клиентском приложении](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
### Создание клиентского приложения в среде Visual Studio  
  
1.  Щелкните правой кнопкой решение в **обозревателе решений**, выберите **Добавить**, а затем **Новый проект**.  
  
2.  Выберите в списке **Типы проектов** пункт **Windows**, а затем выберите пункт **Приложение WPF** в области **Шаблоны**.  
  
3.  Введите в качестве имени проекта `NorthwindClient` и нажмите кнопку **ОК**.  
  
4.  Откройте файл MainWindow.xaml и замените XAML\-код следующим кодом.  
  
     [!code-xml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]  
  
### Добавление в проект ссылки на службу данных  
  
1.  Щелкните правой кнопкой мыши проект NorthwindClient, выберите команду **Добавить ссылку на службу**, а затем нажмите кнопку **Обнаружить**.  
  
     При этом отображается служба данных Northwind, созданная в первой задаче.  
  
2.  В текстовом поле **Пространство имен** введите `Northwind` и нажмите кнопку **ОК**.  
  
     При этом в проект добавляется новый файл кода, содержащий классы данных, которые используются для обращения и взаимодействия с ресурсами службы данных как с объектами.  Классы данных создаются в пространстве имен `NorthwindClient.Northwind`.  
  
### Обращение к данным службы данных в приложении WPF  
  
1.  В **обозревателе решений** под узлом **NorthwindClient** щелкните проект правой кнопкой мыши и выберите команду **Добавить ссылку**.  
  
2.  В диалоговом окне «Добавление ссылки» щелкните вкладку **.NET**, выберите сборку System.Data.Services.Client.dll, а затем нажмите кнопку **ОК**.  В **Обозревателе решений** на вкладке **NorthwindClient** откройте страницу кода для файла MainWindow.xaml и добавьте следующую инструкцию `using` \(`Imports` в Visual Basic\).  
  
     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#using)]  
  
3.  Вставьте следующий код, запрашивающий службу данных и привязывающий результат к коллекции <xref:System.Data.Services.Client.DataServiceCollection%601> класса `MainWindow`.  
  
    > [!NOTE]
    >  Имя узла `localhost:12345` нужно заменить на сервер и порт, на котором размещен экземпляр службы данных Northwind.  
  
     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#querycode)]  
  
4.  Вставьте следующий код, сохраняющий изменения, в класс `MainWindow`.  
  
     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#savechanges)]  
  
### Сборка и запуск приложения NothwindClient  
  
1.  В **обозревателе решений** щелкните правой кнопкой мыши проект NorthwindClient и выберите команду **Установить как запускаемый проект**.  
  
2.  Нажмите клавишу F5 для запуска приложения.  
  
     При этом выполняется сборка решения и запуск клиентского приложения.  Данные извлекаются из службы данных и отображаются в консоли.  
  
3.  Измените значение в столбце **Количество** сетки данных, затем нажмите кнопку **Сохранить**.  
  
     Изменения будут сохранены в службе данных.  
  
    > [!NOTE]
    >  Эта версия приложения NorthwindClient не поддерживает добавление и удаление сущностей.  
  
## Следующие действия  
 Итак, мы успешно создали клиентское приложение, обращающееся к образцу канала Northwind [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Также мы ознакомились с кратким руководством по службам [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] доступе к веб\-каналу [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из приложения [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] см. в разделе [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).  
  
## См. также  
 [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)   
 [Ресурсы](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)