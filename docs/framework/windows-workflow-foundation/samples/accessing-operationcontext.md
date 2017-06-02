---
title: "Доступ к контексту OperationContext | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Доступ к контексту OperationContext
Этот образец демонстрирует способ использования действий обмена сообщениями \(<xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.Send>\) в действии пользовательской области для доступа к <xref:System.ServiceModel.OperationContext.Current%2A> и для прикрепления пользовательского заголовка сообщения к исходящему сообщению или его получения из входящего сообщения.  
  
## Демонстрации  
 Действия обмена сообщениями, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.  
  
## Обсуждение  
 В этом образце показано, как использовать точки расширяемости \(<xref:System.ServiceModel.Activities.ISendMessageCallback>\) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>\) в действиях обмена сообщения для доступа к <xref:System.ServiceModel.OperationContext.Current%2A>.Обратные вызовы регистрируются в среде выполнения рабочего процесса в качестве реализации свойства <xref:System.Activities.IExecutionProperty>, которое выбирается действиями обмена сообщениями после выполнения.Затрагиваются все действия обмена сообщениями в той же области, что и реализация <xref:System.Activities.IExecutionProperty>.В частности, в этом образце используется действие пользовательской области для принудительного задания поведения обратного вызова.<xref:System.ServiceModel.Activities.ISendMessageCallback> используется в клиентском рабочем процессе, чтобы включить состояние <xref:System.Activities.WorkflowApplication.Id%2A> рабочего процесса в качестве заголовка <xref:System.ServiceModel.Channels.MessageHeader> исходящего сообщения.Затем этот заголовок выбирается в службе с помощью <xref:System.ServiceModel.Activities.IReceiveMessageCallback>, и значение заголовка выводится на консоли.  
  
#### Настройка, построение и выполнение образца  
  
1.  В этом образце доступ к службе рабочего процесса предоставляется через конечные точки HTTP.Для выполнения этого образца необходимо добавить списки управления доступом по URL\-адресу \(дополнительные сведения см. в разделе [Настройка HTTP и HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353)\). Для этого запустите среду Visual Studio от имени администратора или выполните следующую команду в командной строке с повышенными привилегиями, чтобы добавить нужные списки управления доступом.Убедитесь, что подставлены нужный домен и имя пользователя.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  После добавления списков управления доступом по URL\-адресу выполните следующие действия.  
  
    1.  Постройте решение.  
  
    2.  Задайте несколько запускаемых проектов. Для этого щелкните решение правой кнопкой мыши и выберите команду **Назначить запускаемые проекты**.  
  
    3.  Добавьте проекты **Служба** и **Клиент** \(в этом порядке\) в качестве запускаемых проектов.  
  
    4.  Запустите приложение.На консоли клиента показан дважды выполняемый рабочий процесс, а в окне службы показаны идентификаторы экземпляров этих рабочих процессов.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`