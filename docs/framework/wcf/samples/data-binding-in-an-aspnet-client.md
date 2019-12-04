---
title: Привязка данных в клиенте ASP.NET
ms.date: 03/30/2017
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
ms.openlocfilehash: 2db29e0c4cdb87961430b80f317160b90e6756d0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715386"
---
# <a name="data-binding-in-an-aspnet-client"></a>Привязка данных в клиенте ASP.NET
В этом образце показано, как привязать данные, возвращаемые стандартной службой Windows Communication Foundation (WCF) в приложении веб-форм.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце показана служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Пример состоит из клиентского приложения Web Forms, доступного из браузера и службы WCF, размещенной службы IIS (IIS).  
  
 Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `IWeatherService`, который предоставляет операцию с именем `GetWeatherData`. Данная операция принимает массив городов и возвращает массив объектов `WeatherData`, представляющих максимальные и минимальные прогнозируемые значения температуры для городов.  
  
 На странице ASP.NET Client. aspx определяется веб-элемент управления DataGrid, который содержит графическое представление данных, возвращенных службой. Код на ASPX-странице вызывает службу WCF для данных о погоде и возвращает данные в массив объектов `WeatherData`. Элемент управления DataGrid задает, откуда он получает свои данные, задавая в свойстве `DataSource` этот массив. Привязка данных производится вызовом метода `DataBind` элемента управления DataGrid. Весь этот код содержится в.`aspx` метод `Page_Load` страницы, поэтому каждый раз, когда пользователь обновляет страницу браузера, данные обновляются в DataGrid.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Клиент этого образца представляет собой веб-сайт, работающий под управлением веб-сервера разработки. Чтобы запустить веб-сервер разработки, введите в командной строке следующую команду: `%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`. Перейдите к `http://localhost:8000/client`. Чтобы запустить этот пример на нескольких компьютерах, замените все вхождения `localhost` в файле Web.config клиента именем компьютера сервера.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`
