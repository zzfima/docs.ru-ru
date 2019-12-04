---
title: Базовая служба HTTP
ms.date: 03/30/2017
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
ms.openlocfilehash: 8dfcd5a751bcef6aa24b5cb4a200c8820c43fe81
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716093"
---
# <a name="basic-http-service"></a>Базовая служба HTTP

В этом образце показано, как реализовать службу на основе протокола RPC на основе HTTP, которая называется службой POX (обычная старая XML), с использованием модели программирования Windows Communication Foundation (WCF). Этот пример состоит из двух компонентов: автономной службы HTTP WCF (Service.cs) и консольного приложения (Program.cs), которое создает службу и выполняет в ней вызовы.

## <a name="sample-details"></a>Подробные сведения об образце

Служба WCF предоставляет 2 операции, `EchoWithGet` и `EchoWithPost`, которые возвращают строку, переданную в качестве входных данных.

К операции `EchoWithGet` добавляется заметка <xref:System.ServiceModel.Web.WebGetAttribute>, указывающим на обработку операцией HTTP-запросов `GET`. Поскольку <xref:System.ServiceModel.Web.WebGetAttribute> не указывает явно <xref:System.UriTemplate>, оператор ожидает передачи входной строки с помощью параметра строки запроса с именем `s`. Обратите внимание, что формат URI, ожидаемого службой, может быть изменен с помощью свойства <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A>.

К операции `EchoWithPost` добавляется заметка <xref:System.ServiceModel.Web.WebInvokeAttribute>, указывающая на то, что это не является операцией `GET` (имеющей побочные эффекты). Поскольку <xref:System.ServiceModel.Web.WebInvokeAttribute> не указывает явно `Method`, операция обрабатывает HTTP-запросы `POST`, содержащие строку в тексте запроса (например, в формате XML). Обратите внимание, что метод HTTP и формат URI запроса можно изменить с помощью свойств <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> и <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate> соответственно.

Файл App.config настраивает для службы WCF конечную точку по умолчанию <xref:System.ServiceModel.Description.WebHttpEndpoint>, для свойства которого <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> задано значение `true`. В результате инфраструктура WCF создает автоматическую HTML-страницу справки на `http://localhost:8000/Customers/help`, которая предоставляет сведения о том, как создавать HTTP-запросы к службе и как использовать HTTP-ответ службы.

Program.cs демонстрирует, как фабрику каналов WCF можно использовать для выполнения вызовов службы и обработки ответов. Заметьте, что это лишь один из способов доступа к WCF-службе. Также возможен доступ к службе с помощью других классов .NET Framework, например <xref:System.Net.HttpWebRequest> и <xref:System.Net.WebClient>.

Образец состоит из резидентной службы и клиента, которые работают в консольном приложении. Во время выполнения консольного приложения клиент совершает запросы к службе и выводит в окно консоли нужные сведения из ответов.

#### <a name="to-use-this-sample"></a>Использование этого образца

1. Откройте решение в образце базовой службы Http. При запуске Visual Studio 2012 для успешного выполнения примера необходимо запустить от имени администратора. Для этого щелкните правой кнопкой мыши значок Visual Studio 2012 и выберите в контекстном меню команду **Запуск от имени администратора** .

2. Нажмите сочетание клавиш CTRL+SHIFT+B, чтобы построить решение, а затем сочетание клавиш Ctrl+F5 для запуска консольного приложения без отладки. Открывается окно консоли с URI запущенной службы и URI HTML-страницы справки для запущенной службы. HTML-страницу справки можно просмотреть в любой момент времени, введя URI этой страницы в браузере. Во время работы образца клиент записывает состояние текущего действия.

3. Чтобы завершить образец, нажмите любую клавишу.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`
