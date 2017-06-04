---
title: "Базовая служба HTTP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Базовая служба HTTP
В образце демонстрируется способ реализации службы HTTP на основе RPC \(такую службу часто называют службой POX \(Plain Old XML — обычный XML\)\) с использованием модели программирования HTTP [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Данный образец состоит из двух компонентов: резидентной службы HTTP [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \(Service.cs\) и консольного приложения \(Program.cs\), создающего службу и выполняющего вызовы в этой службе.  
  
## Подробные сведения об образце  
 Служба [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] предоставляет 2 операции — `EchoWithGet` и `EchoWithPost`, которые возвращают строку, переданную им на входе.  
  
 Операция `EchoWithGet` аннотируется <xref:System.ServiceModel.Web.WebGetAttribute>, указывающим на обработку операцией HTTP\-запросов `GET`.Поскольку <xref:System.ServiceModel.Web.WebGetAttribute> не указывает явно <xref:System.UriTemplate>, оператор ожидает передачи входной строки с помощью параметра строки запроса с именем `s`.Обратите внимание, что формат URI, ожидаемого службой, может быть изменен с помощью свойства <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A>.  
  
 Операция `EchoWithPost` аннотируется <xref:System.ServiceModel.Web.WebInvokeAttribute>, указывающим на то, что это не является операцией `GET` \(имеющей побочные эффекты\).Поскольку <xref:System.ServiceModel.Web.WebInvokeAttribute> не указывает явно `Method`, операция обрабатывает HTTP\-запросы `POST`, содержащие строку в тексте запроса \(например, в формате XML\).Обратите внимание, что метод HTTP и формат URI запроса можно изменить с помощью свойств <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> и <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate> соответственно.  
  
 Файл App.config настраивает для службы WCF конечную точку по умолчанию <xref:System.ServiceModel.Description.WebHttpEndpoint>, для свойства которого <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> задано значение `true`.В результате в инфраструктуре создается страница автоматической справки в формате HTML [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в `http://localhost:8000/Customers/help`, которая содержит данные о способах создания HTTP\-запросов к службе и способах использования HTTP\-ответов службы.  
  
 В Program.cs показаны способы использования фабрики каналов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для выполнения вызовов службы и обработки ответов.Заметьте, что это лишь один из способов доступа к службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Также возможен доступ к службе с помощью других классов .NET Framework, например <xref:System.Net.HttpWebRequest> и <xref:System.Net.WebClient>.В других образцах из пакета SDK \(например, образец [Автоматический выбор формата](../../../../docs/framework/wcf/samples/automatic-format-selection.md) и образец [Основная служба ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md)\) показано, как использовать эти классы для связи со службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Образец состоит из резидентной службы и клиента, которые работают в консольном приложении.Во время выполнения консольного приложения клиент совершает запросы к службе и выводит в окно консоли нужные сведения из ответов.  
  
#### Использование этого образца  
  
1.  Откройте решение в образце базовой службы Http.Для успешного выполнения образца среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] необходимо запускать от имени администратора.Для этого щелкните правой кнопкой мыши значок [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] и выберите в контекстном меню команду **Запуск от имени администратора**.  
  
2.  Нажмите сочетание клавиш CTRL\+SHIFT\+B, чтобы построить решение, а затем сочетание клавиш Ctrl\+F5 для запуска консольного приложения без отладки.Открывается окно консоли с URI запущенной службы и URI HTML\-страницы справки для запущенной службы.HTML\-страницу справки можно просмотреть в любой момент времени, введя URI этой страницы в браузере.Во время работы образца клиент записывает состояние текущего действия.  
  
3.  Чтобы завершить образец, нажмите любую клавишу.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`  
  
## См. также  
 [Автоматический выбор формата](../../../../docs/framework/wcf/samples/automatic-format-selection.md)   
 [Основная служба ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md)