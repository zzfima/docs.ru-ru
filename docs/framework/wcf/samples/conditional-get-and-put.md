---
title: "Условные методы Get и Put | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d22067f-57b8-4e0f-a571-a694512187ae
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Условные методы Get и Put
В этом образце демонстрируется использование новых интерфейсов API условного получения и обновления для модели программирования WCF REST.Поскольку условное получение и обновление больше всего подходит для служб REST и служб, ориентированных на ресурсы, этот образец расширяет образец [Основная служба ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md).Основное внимание в этом образце уделяется добавлению к образцу [Основная служба ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md) поддержки условного получения и обновления с помощью новых API, появившихся в [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].  
  
## Демонстрации  
 Условное получение и обновление  
  
## Обсуждение  
 В этом образце служба WCF предоставляет доступ к коллекции клиентов в стиле REST и с ориентацией на ресурсы.Подробное описание реализации службы см. в образце [Основная служба ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md).  
  
 Этот образец добавляет возможности условного получения и обновления к образцу [Основная служба ресурсов](../../../../docs/framework/wcf/samples/basic-resource-service.md).Для проверки наличия у клиента последней сущности для данного ресурса при условном получении и обновлении используются теги сущности HTTP и заголовки HTTP If\-None\-Match и If\-Match.Однако реализация кода для правильной проверки заголовков HTTP If\-None\-Match и If\-Match занимает много времени и редко получается без ошибок.В связи с этим в контекст <xref:System.ServiceModel.Web.IncomingWebRequestContext> были добавлены методы <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> и <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>, доступ к которым можно получить с помощью текущего экземпляра контекста <xref:System.ServiceModel.Web.WebOperationContext>.Кроме того, в контекст <xref:System.ServiceModel.Web.OutgoingWebRequestContext> был добавлен метод `SetETag`, что упрощает возврат допустимых тегов сущностей.  
  
 Метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> предназначен для использования с операциями \[WebGet\].Он принимает тег текущей сущности данного ресурса в качестве параметра `entityTag`, который может иметь тип `string`, `int`, `long` или `Guid`.Метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> проверяет тег сущности по заголовку HTTP If\-None\-Match запроса.Если этот тег сущности имеется в заголовке HTTP If\-None\-Match, то формируется исключение <xref:System.ServiceModel.Web.WebFaultException> с кодом состояния «Не изменено» \(304\). В противном случае метод возвращает значение.Этот механизм условного получения позволяет клиенту сообщать серверу, что у него есть эта сущность, и отправлять текущую сущность, только если ее у клиента нет.Пример использования метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> можно посмотреть в операциях `GetCustomer` и `GetCustomers` службы.Важно отметить, что при вызове метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> значение может быть не возвращено.Разработчикам следует реализовывать операцию так, чтобы до вызова метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> уже было известно, что запрос выполнен успешно, с тем чтобы при отсутствии вызова метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> служба отправляла сообщение с кодом состояния успешного выполнения.  
  
 Метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> похож на метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>.Он тоже принимает тег текущей сущности для данного ресурса.Однако он предназначен для использования с операциями \[WebInvoke\], в которых для метода задается значение «PUT» или «DELETE».Метод <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> проверяет тег сущности по заголовку HTTP If\-Match запроса.Если в заголовке HTTP If\-Match тег сущности отсутствует, то формируется исключение <xref:System.ServiceModel.Web.WebFaultException> с кодом состояния «Предварительное условие не выполнено» \(412\).Этот механизм условного обновления позволяет клиенту сообщать серверу, что у него есть эта сущность для ресурса; он позволяет клиенту изменять ресурс, только если имеющаяся у него сущность является текущей.Пример использования метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> можно посмотреть в операциях `UpdateCustomer` и `DeleteCustomer` службы.Как и в случае с методом <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, важно отметить, что при вызове метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> значение может быть не возвращено.Разработчикам следует реализовывать операцию так, чтобы до вызова метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> уже было известно, что запрос выполнен успешно, с тем чтобы при отсутствии вызова метода <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> служба отправляла сообщение с кодом состояния успешного выполнения.  
  
 Образец состоит из резидентной службы и клиента, который работает в консольном приложении.Во время выполнения консольного приложения клиент совершает запросы к службе и выводит в окно консоли нужные сведения из ответов.  
  
#### Выполнение образца  
  
1.  Откройте решение для образца Conditional Get and Put.Для успешного выполнения образца среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] необходимо запускать от имени администратора.Для этого щелкните правой кнопкой мыши значок [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] и выберите в контекстном меню команду **Запуск от имени администратора**.  
  
2.  Нажмите сочетание клавиш CTRL\+SHIFT\+B, чтобы построить решение, а затем сочетание клавиш CTRL\+F5, чтобы запустить проект консольного приложения.Если запустить этот проект с включенной функцией отладки \(нажав клавишу F5 вместо CTRL\+F5\), то отладчик будет останавливаться, когда условная проверка GET и PUT формирует исключение.В этом случае нажмите клавишу F5, чтобы продолжить выполнение образца.  
  
3.  Открывается окно консоли с URI запущенной службы и URI HTML\-страницы справки для запущенной службы.  
  
4.  Во время выполнения образца клиент отправляет запросы к службе и выводит ответы в окно консоли.  
  
5.  Чтобы завершить образец, нажмите любую клавишу.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Web\ConditionalGetAndPut`