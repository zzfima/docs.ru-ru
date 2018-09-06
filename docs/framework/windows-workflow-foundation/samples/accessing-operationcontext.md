---
title: Доступ к контексту OperationContext
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: 3c7ce1c9c37ee93b58a07376e0aeae045f0ca408
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43788848"
---
# <a name="accessing-operationcontext"></a>Доступ к контексту OperationContext
В этом образце показано как действия обмена сообщениями (<xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.Send>) можно использовать с действием пользовательской области для доступа к <xref:System.ServiceModel.OperationContext.Current%2A> и подключить или извлечь пользовательского заголовка сообщения исходящего или входящего сообщения.  
  
## <a name="demonstrates"></a>Демонстрации  
 Действия обмена сообщениями, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце показано, как использовать точки расширяемости (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) в действиях обмена сообщения для доступа к <xref:System.ServiceModel.OperationContext.Current%2A>. Обратные вызовы регистрируются в среде выполнения рабочего процесса в качестве реализации свойства <xref:System.Activities.IExecutionProperty>, которое выбирается действиями обмена сообщениями после выполнения. Затрагиваются все действия обмена сообщениями в той же области, что и реализация <xref:System.Activities.IExecutionProperty>. В частности, в этом образце используется действие пользовательской области для принудительного задания поведения обратного вызова. <xref:System.ServiceModel.Activities.ISendMessageCallback> используется в клиентском рабочем процессе, чтобы включить состояние <xref:System.Activities.WorkflowApplication.Id%2A> рабочего процесса в качестве заголовка <xref:System.ServiceModel.Channels.MessageHeader> исходящего сообщения. Затем этот заголовок выбирается в службе с помощью <xref:System.ServiceModel.Activities.IReceiveMessageCallback>, и значение заголовка выводится на консоли.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  В этом образце доступ к службе рабочего процесса предоставляется через конечные точки HTTP. Для выполнения этого образца, соответствующие URL ACL необходимо добавить (см. в разделе [Настройка HTTP и HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) сведения), запустив Visual Studio от имени администратора или выполните следующую команду в строке с повышенными привилегиями, чтобы добавить нужные списки управления доступом. Убедитесь, что подставлены нужный домен и имя пользователя.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  После добавления списков управления доступом по URL-адресу выполните следующие действия.  
  
    1.  Постройте решение.  
  
    2.  Задайте несколько запускаемых проектов, щелкните правой кнопкой мыши решение и выбрав **назначить запускаемые проекты**.  
  
    3.  Добавить **службы** и **клиента** (в таком порядке) в качестве запускаемых проектов.  
  
    4.  Запустите приложение. На консоли клиента показан дважды выполняемый рабочий процесс, а в окне службы показаны идентификаторы экземпляров этих рабочих процессов.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
