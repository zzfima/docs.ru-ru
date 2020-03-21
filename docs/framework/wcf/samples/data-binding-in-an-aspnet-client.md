---
title: Привязка данных в клиенте ASP.NET
ms.date: 03/30/2017
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
ms.openlocfilehash: c068c1cab5a5b9dad75e781e58076f4066a3b2a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145011"
---
# <a name="data-binding-in-an-aspnet-client"></a>Привязка данных в клиенте ASP.NET
В этом примере показано, как связывать данные, возвращенные типичным сервисом Windows Communication Foundation (WCF) в приложении Web Forms.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце показана служба, которая реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Выборка состоит из клиентского приложения Web Forms, доступного из браузера, и сервиса WCF, размещенного информационными службами Интернета (IIS).  
  
 Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `IWeatherService`, который предоставляет операцию с именем `GetWeatherData`. Данная операция принимает массив городов и возвращает массив объектов `WeatherData`, представляющих максимальные и минимальные прогнозируемые значения температуры для городов.  
  
 На странице ASP.NET клиент .aspx определяется веб-контроль DataGrid, содержащий графическое представление данных, возвращенных службой. Код на странице .aspx вызывает службу WCF для данных `WeatherData` о погоде и возвращает данные массиву объектов. Элемент управления DataGrid задает, откуда он получает свои данные, задавая в свойстве `DataSource` этот массив. Привязка данных производится вызовом метода `DataBind` элемента управления DataGrid. Весь этот код содержится внутри .`aspx` `Page_Load` метод страницы, поэтому каждый раз, когда пользователь обновляет страницу браузера, данные обновляются в DataGrid.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Клиент этого образца представляет собой веб-сайт, работающий под управлением веб-сервера разработки. Чтобы запустить веб-сервер разработки, введите `%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client`следующий запрос команды: . Затем просмотрите. `http://localhost:8000/client` Чтобы запустить этот пример на нескольких компьютерах, замените все вхождения `localhost` в файле Web.config клиента именем компьютера сервера.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`
