---
title: Доступ к контексту OperationContext
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: 8d1c8543180a282a1b196393e5823dc3686aa16e
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038411"
---
# <a name="accessing-operationcontext"></a>Доступ к контексту OperationContext
В этом примере показано, как действия обмена<xref:System.ServiceModel.Activities.Receive> сообщениями (и <xref:System.ServiceModel.Activities.Send>) могут использоваться с действием пользовательской области <xref:System.ServiceModel.OperationContext.Current%2A> для доступа к настраиваемому заголовку сообщения и его получения в исходящем или входящем сообщении.  
  
## <a name="demonstrates"></a>Демонстрации  
 Действия обмена сообщениями, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце показано, как использовать точки расширяемости (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) в действиях обмена сообщения для доступа к <xref:System.ServiceModel.OperationContext.Current%2A>. Обратные вызовы регистрируются в среде выполнения рабочего процесса в качестве реализации свойства <xref:System.Activities.IExecutionProperty>, которое выбирается действиями обмена сообщениями после выполнения. Затрагиваются все действия обмена сообщениями в той же области, что и реализация <xref:System.Activities.IExecutionProperty>. В частности, в этом образце используется действие пользовательской области для принудительного задания поведения обратного вызова. <xref:System.ServiceModel.Activities.ISendMessageCallback> используется в клиентском рабочем процессе, чтобы включить состояние <xref:System.Activities.WorkflowApplication.Id%2A> рабочего процесса в качестве заголовка <xref:System.ServiceModel.Channels.MessageHeader> исходящего сообщения. Затем этот заголовок выбирается в службе с помощью <xref:System.ServiceModel.Activities.IReceiveMessageCallback>, и значение заголовка выводится на консоли.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. В этом образце доступ к службе рабочего процесса предоставляется через конечные точки HTTP. Чтобы выполнить этот пример, необходимо добавить соответствующие списки ACL URL-адресов (см. Дополнительные сведения о [настройке HTTP и HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) ), запустив Visual Studio от имени администратора или выполнив следующую команду в командной строке с повышенными привилегиями, чтобы добавить соответствующие списки ACL. Убедитесь, что подставлены нужный домен и имя пользователя.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. После добавления списков управления доступом по URL-адресу выполните следующие действия.  
  
    1. Постройте решение.  
  
    2. Задайте несколько проектов запуска, щелкнув решение правой кнопкой мыши и выбрав пункт **задать запускаемые проекты**.  
  
    3. Добавьте **службу** и **клиент** (в этом порядке) в качестве нескольких запускаемых проектов.  
  
    4. Запустите приложение. На консоли клиента показан дважды выполняемый рабочий процесс, а в окне службы показаны идентификаторы экземпляров этих рабочих процессов.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и примеры. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
