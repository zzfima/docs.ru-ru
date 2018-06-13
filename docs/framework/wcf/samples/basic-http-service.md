---
title: Базовая служба HTTP
ms.date: 03/30/2017
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
ms.openlocfilehash: 0f93b43a08f586e99d8a49379cfb2e283ff7918d
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33808862"
---
# <a name="basic-http-service"></a>Базовая служба HTTP
Этот образец демонстрирует реализацию службы на основе HTTP, на основе RPC - часто называют службы «POX» (Plain Old XML) — с использованием модели программирования REST Windows Communication Foundation (WCF). В этом примере состоит из двух компонентов: резидентной службы WCF HTTP (Service.cs) и консольного приложения (Program.cs), создающего службу и выполняющего вызовы к нему.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Служба WCF предоставляет 2 операции `EchoWithGet` и `EchoWithPost`, который возвращает строку, которая была передана в качестве входных данных.  
  
 Операция `EchoWithGet` аннотируется <xref:System.ServiceModel.Web.WebGetAttribute>, указывающим на обработку операцией HTTP-запросов `GET`. Поскольку <xref:System.ServiceModel.Web.WebGetAttribute> не указывает явно <xref:System.UriTemplate>, оператор ожидает передачи входной строки с помощью параметра строки запроса с именем `s`. Обратите внимание, что формат URI, ожидаемого службой, может быть изменен с помощью свойства <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A>.  
  
 Операция `EchoWithPost` аннотируется <xref:System.ServiceModel.Web.WebInvokeAttribute>, указывающим на то, что это не является операцией `GET` (имеющей побочные эффекты). Поскольку <xref:System.ServiceModel.Web.WebInvokeAttribute> не указывает явно `Method`, операция обрабатывает HTTP-запросы `POST`, содержащие строку в тексте запроса (например, в формате XML). Обратите внимание, что метод HTTP и формат URI запроса можно изменить с помощью свойств <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> и <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate> соответственно.  
  
 Файл App.config настраивает для службы WCF конечную точку по умолчанию <xref:System.ServiceModel.Description.WebHttpEndpoint>, для свойства которого <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> задано значение `true`. В результате инфраструктура WCF создает автоматический страницу справки формате HTML по адресу `http://localhost:8000/Customers/help` , предоставляющий сведения о способах создания HTTP-запросов к службе и как использовать службы HTTP-ответа.  
  
 Program.cs показывает, как фабрику каналов WCF можно использовать для выполнения вызовов службы и обработки ответов. Заметьте, что это лишь один из способов доступа к WCF-службе. Также возможен доступ к службе с помощью других классов .NET Framework, например <xref:System.Net.HttpWebRequest> и <xref:System.Net.WebClient>. Другие примеры в пакете SDK (такие как [автоматический выбор формата](../../../../docs/framework/wcf/samples/automatic-format-selection.md) образца и [базовой службы ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md) образец) показано, как использовать эти классы для взаимодействия со службой WCF.  
  
 Образец состоит из резидентной службы и клиента, которые работают в консольном приложении. Во время выполнения консольного приложения клиент совершает запросы к службе и выводит в окно консоли нужные сведения из ответов.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте решение в образце базовой службы Http. Для успешного выполнения образца среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] необходимо запускать от имени администратора. Для этого щелкните правой кнопкой мыши [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] значок и выбрав **Запуск от имени администратора** в контекстном меню.  
  
2.  Нажмите сочетание клавиш CTRL+SHIFT+B, чтобы построить решение, а затем сочетание клавиш Ctrl+F5 для запуска консольного приложения без отладки. Открывается окно консоли с URI запущенной службы и URI HTML-страницы справки для запущенной службы. HTML-страницу справки можно просмотреть в любой момент времени, введя URI этой страницы в браузере. Во время работы образца клиент записывает состояние текущего действия.  
  
3.  Чтобы завершить образец, нажмите любую клавишу.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`  
  
## <a name="see-also"></a>См. также  
 [Автоматический выбор формата](../../../../docs/framework/wcf/samples/automatic-format-selection.md)  
 [Основная служба ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md)
