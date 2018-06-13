---
title: Привязка данных в клиенте ASP.NET
ms.date: 03/30/2017
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
ms.openlocfilehash: 8fdebec272fbedf23233e03ba7c6fe2d64cb18cc
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804996"
---
# <a name="data-binding-in-an-aspnet-client"></a>Привязка данных в клиенте ASP.NET
В этом примере показано, как выполнить привязку данных, возвращаемых обычной службы Windows Communication Foundation (WCF) в приложении веб-форм.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце показана служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Образец состоит из клиентского приложения веб-форм, доступного из веб-браузер и службы WCF, размещенной Internet Information Services (IIS).  
  
 Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `IWeatherService`, который предоставляет операцию с именем `GetWeatherData`. Данная операция принимает массив городов и возвращает массив объектов `WeatherData`, представляющих максимальные и минимальные прогнозируемые значения температуры для городов.  
  
 На странице ASPX клиента [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] определен веб-элемент управления DataGrid, содержащий графическое представление данных, возвращенных службой. Код на странице ASPX вызывает службу WCF для получения данных о погоде и возвращает данные в виде массива `WeatherData` объектов. Элемент управления DataGrid задает, откуда он получает свои данные, задавая в свойстве `DataSource` этот массив. Привязка данных производится вызовом метода `DataBind` элемента управления DataGrid. Весь этот код содержится внутри.`aspx` на странице `Page_Load` метод, поэтому каждый раз, когда пользователь обновляет страницу браузера, а данные обновляются в элементе управления DataGrid.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Клиент этого образца представляет собой веб-сайт, работающий под управлением веб-сервера разработки. Чтобы запустить веб-сервер разработки, введите следующее в командной строке: "`%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`. Перейдите к http://localhost:8000/client. Чтобы запустить этот пример на нескольких компьютерах, замените все вхождения `localhost` в файле Web.config клиента именем компьютера сервера.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`  
  
## <a name="see-also"></a>См. также
