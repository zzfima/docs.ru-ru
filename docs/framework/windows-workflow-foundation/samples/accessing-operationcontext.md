---
title: Доступ к контексту OperationContext
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: 83f3a6cacd3ee86050f65a886d446ab8da7d3690
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094713"
---
# <a name="accessing-operationcontext"></a>Доступ к контексту OperationContext
В этом примере показано, как действия обмена сообщениями (<xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.Send>) можно использовать с действием пользовательской области для доступа к <xref:System.ServiceModel.OperationContext.Current%2A> и присоединения или получения пользовательского заголовка сообщения в исходящем или входящем сообщении.  
  
## <a name="demonstrates"></a>Что демонстрирует  
 Действия обмена сообщениями, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце показано, как использовать точки расширяемости (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) в действиях обмена сообщения для доступа к <xref:System.ServiceModel.OperationContext.Current%2A>. Обратные вызовы регистрируются в среде выполнения рабочего процесса в качестве реализации свойства <xref:System.Activities.IExecutionProperty>, которое выбирается действиями обмена сообщениями после выполнения. Затрагиваются все действия обмена сообщениями в той же области, что и реализация <xref:System.Activities.IExecutionProperty>. В частности, в этом образце используется действие пользовательской области для принудительного задания поведения обратного вызова. <xref:System.ServiceModel.Activities.ISendMessageCallback> используется в клиентском рабочем процессе, чтобы включить состояние <xref:System.Activities.WorkflowApplication.Id%2A> рабочего процесса в качестве заголовка <xref:System.ServiceModel.Channels.MessageHeader> исходящего сообщения. Затем этот заголовок выбирается в службе с помощью <xref:System.ServiceModel.Activities.IReceiveMessageCallback>, и значение заголовка выводится на консоли.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. В этом образце доступ к службе рабочего процесса предоставляется через конечные точки HTTP. Чтобы выполнить этот пример, необходимо добавить соответствующие списки ACL URL-адресов (см. Дополнительные сведения о [настройке HTTP и HTTPS](../../wcf/feature-details/configuring-http-and-https.md) ), запустив Visual Studio от имени администратора или выполнив следующую команду в командной строке с повышенными привилегиями, чтобы добавить соответствующие списки ACL. Убедитесь, что подставлены нужный домен и имя пользователя.  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. После добавления списков управления доступом по URL-адресу выполните следующие действия.  
  
    1. Создайте решение.  
  
    2. Задайте несколько проектов запуска, щелкнув решение правой кнопкой мыши и выбрав пункт **задать запускаемые проекты**.  
  
    3. Добавьте **службу** и **клиент** (в этом порядке) в качестве нескольких запускаемых проектов.  
  
    4. Запустите приложение. На консоли клиента показан дважды выполняемый рабочий процесс, а в окне службы показаны идентификаторы экземпляров этих рабочих процессов.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
