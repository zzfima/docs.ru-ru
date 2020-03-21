---
title: Доступ к контексту OperationContext
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: 5a2731c7918c216221b0adcafd5c804e80f36dfb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182858"
---
# <a name="accessing-operationcontext"></a>Доступ к контексту OperationContext
Этот пример демонстрирует, как<xref:System.ServiceModel.Activities.Receive> действия <xref:System.ServiceModel.Activities.Send>обмена сообщениями (и) могут <xref:System.ServiceModel.OperationContext.Current%2A> быть использованы с пользовательским действием области для доступа и присоединения или извлечения пользовательского заголовка сообщений в исходящих или входящих сообщениях.  
  
## <a name="demonstrates"></a>Что демонстрирует  
 Действия обмена сообщениями, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.  
  
## <a name="discussion"></a>Обсуждение  
 В этом образце показано, как использовать точки расширяемости (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) в действиях обмена сообщения для доступа к <xref:System.ServiceModel.OperationContext.Current%2A>. Обратные вызовы регистрируются в среде выполнения рабочего процесса в качестве реализации свойства <xref:System.Activities.IExecutionProperty>, которое выбирается действиями обмена сообщениями после выполнения. Затрагиваются все действия обмена сообщениями в той же области, что и реализация <xref:System.Activities.IExecutionProperty>. В частности, в этом образце используется действие пользовательской области для принудительного задания поведения обратного вызова. <xref:System.ServiceModel.Activities.ISendMessageCallback> используется в клиентском рабочем процессе, чтобы включить состояние <xref:System.Activities.WorkflowApplication.Id%2A> рабочего процесса в качестве заголовка <xref:System.ServiceModel.Channels.MessageHeader> исходящего сообщения. Затем этот заголовок выбирается в службе с помощью <xref:System.ServiceModel.Activities.IReceiveMessageCallback>, и значение заголовка выводится на консоли.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. В этом образце доступ к службе рабочего процесса предоставляется через конечные точки HTTP. Для выполнения этого образца необходимо добавить надлежащие URL-аКЛз (см. [Настройка HTTP и HTTPS](../../wcf/feature-details/configuring-http-and-https.md) для деталей), либо запустив Visual Studio в качестве администратора, либо выполняя следующую команду в повышенной подсказке для добавления соответствующих ACL. Убедитесь, что подставлены нужный домен и имя пользователя.  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. После добавления списков управления доступом по URL-адресу выполните следующие действия.  
  
    1. Создайте решение.  
  
    2. Установите несколько проектов запуска, нажав на решение правой кнопкой мыши и выбрав **настройку startup Projects.**  
  
    3. Добавление **обслуживания** и **клиента** (в этом порядке) в качестве нескольких стартап-проектов.  
  
    4. Запустите приложение. На консоли клиента показан дважды выполняемый рабочий процесс, а в окне службы показаны идентификаторы экземпляров этих рабочих процессов.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
