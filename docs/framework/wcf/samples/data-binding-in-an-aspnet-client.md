---
title: "Привязка данных в клиенте ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Привязка данных в клиенте ASP.NET
В этом образце показано, как выполнить привязку к данным, обычно возвращаемым службой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в приложении веб\-форм.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для этого образца приведены в конце этого раздела.  
  
 В этом образце показана служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос\-ответ".Этот образец состоит из приложения веб\-форм, доступного из веб\-браузера, и службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], размещенной в службах IIS.  
  
 Служба реализует контракт, определяющий шаблон взаимодействия "запрос\-ответ".Контракт определяется интерфейсом `IWeatherService`, который предоставляет операцию с именем `GetWeatherData`.Данная операция принимает массив городов и возвращает массив объектов `WeatherData`, представляющих максимальные и минимальные прогнозируемые значения температуры для городов.  
  
 На странице ASPX клиента [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] определен веб\-элемент управления DataGrid, содержащий графическое представление данных, возвращенных службой.Код на странице ASPX вызывает службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для получения данных о погоде и возвращает эти данные в виде массива объектов `WeatherData`.Элемент управления DataGrid задает, откуда он получает свои данные, задавая в свойстве `DataSource` этот массив.Привязка данных производится вызовом метода `DataBind` элемента управления DataGrid.Весь этот код содержится в методе `Page_Load` страницы `aspx`, поэтому каждый раз, когда пользователь обновляет страницу браузера, обновляются данные в элементе управления DataGrid.  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы выполнить построение версии решения для языка C\# или Visual Basic .NET, следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Клиент этого образца представляет собой веб\-сайт, работающий под управлением веб\-сервера разработки.Чтобы запустить веб\-сервер разработки, введите в командной строке следующую команду: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`.Затем перейдите по адресу http:\/\/localhost:8000\/client.Чтобы запустить этот образец на нескольких компьютерах, замените все вхождения `localhost` в файле Web.config клиента именем компьютера сервера.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`  
  
## См. также