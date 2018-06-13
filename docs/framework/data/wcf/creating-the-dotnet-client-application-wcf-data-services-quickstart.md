---
title: Создание клиентского приложения .NET Framework (краткое руководство по службам данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 09981a7aee2db24d8464bbc7412b82a57ec8115b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365359"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a>Создание клиентского приложения .NET Framework (краткое руководство по службам данных WCF)
Это последняя задача [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] краткое руководство. В этой задаче будет добавить в решение консольное приложение, добавьте ссылку на [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канала в новое клиентское приложение, а доступ [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала из клиентского приложения с помощью сформированных клиентских классов службы данных и клиента библиотеки.  
  
> [!NOTE]
>  Для доступа к каналу данных наличие клиентского приложения на основе .NET Framework необязательно. Доступ к службе данных любой может получить, используя компонент приложения, реализующий канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Дополнительные сведения см. в разделе [использование служб данных в клиентском приложении](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
### <a name="to-create-the-client-application-by-using-visual-studio"></a>Создание клиентского приложения в среде Visual Studio  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши решение, нажмите кнопку **добавить**, а затем нажмите кнопку **новый проект**.  
  
2.  В **типов проектов**, нажмите кнопку **Windows**и выберите **приложение WPF** в **шаблоны** области.  
  
3.  Введите `NorthwindClient` для имени проекта и нажмите кнопку **ОК**.  
  
4.  Откройте файл MainWindow.xaml и замените XAML-код следующим кодом.  
  
     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]  
  
### <a name="to-add-a-data-service-reference-to-the-project"></a>Добавление в проект ссылки на службу данных  
  
1.  Щелкните правой кнопкой мыши проект NorthwindClient, выберите **добавить ссылку на службу**, а затем нажмите кнопку **Discover**.  
  
     При этом отображается служба данных Northwind, созданная в первой задаче.  
  
2.  В **имен** введите `Northwind`, а затем нажмите кнопку **ОК**.  
  
     При этом в проект добавляется новый файл кода, содержащий классы данных, которые используются для обращения и взаимодействия с ресурсами службы данных как с объектами. Классы данных создаются в пространстве имен `NorthwindClient.Northwind`.  
  
### <a name="to-access-data-service-data-in-the-wpf-application"></a>Обращение к данным службы данных в приложении WPF  
  
1.  В **обозревателе решений** под **NorthwindClient**, щелкните правой кнопкой мыши проект и нажмите кнопку **добавить ссылку**.  
  
2.  В диалоговом окне «Добавление ссылки» щелкните **.NET** вкладке, выберите сборку System.Data.Services.Client.dll и нажмите кнопку **ОК**. В **обозревателе решений** под **NorthwindClient**, откройте страницу кода для файла MainWindow.xaml и добавьте следующие `using` инструкции (`Imports` в Visual Basic).  
  
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
  
### <a name="to-build-and-run-the-northwindclient-application"></a>Сборка и запуск приложения NothwindClient  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши проект NorthwindClient и выберите **Назначить запускаемым проектом**.  
  
2.  Нажмите клавишу F5 для запуска приложения.  
  
     При этом выполняется сборка решения и запуск клиентского приложения. Данные извлекаются из службы данных и отображаются в консоли.  
  
3.  Изменение значения в **количество** столбца сетки данных, а затем нажмите кнопку **Сохранить**.  
  
     Изменения будут сохранены в службе данных.  
  
    > [!NOTE]
    >  Эта версия приложения NorthwindClient не поддерживает добавление и удаление сущностей.  
  
## <a name="next-steps"></a>Следующие шаги  
 Итак, мы успешно создали клиентское приложение, обращающееся к образцу канала Northwind [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Также мы ознакомились с кратким руководством по службам [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Дополнительные сведения о доступе к [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] канала из [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] приложения, в разделе [клиентскую библиотеку служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).  
  
## <a name="see-also"></a>См. также  
 [Начало работы](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [Ресурсы](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
