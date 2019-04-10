---
title: Практическое руководство. Включение сохраняемости для рабочих процессов и служб рабочих процессов
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 6a2a8d73298e14f92f376b97b9637db91532e937
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340156"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a>Практическое руководство. Включение сохраняемости для рабочих процессов и служб рабочих процессов
В этом разделе описывается процесс включения сохраняемости для рабочих процессов и служб рабочих процессов.  
  
## <a name="enable-persistence-for-workflows"></a>Включение сохраняемости для рабочих процессов  
 Можно связать хранилище экземпляров с **WorkflowApplication** с помощью <xref:System.Activities.WorkflowApplication.InstanceStore%2A> свойство <xref:System.Activities.WorkflowApplication> класса. Метод <xref:System.Activities.WorkflowApplication.Persist%2A> сохраняет рабочий процесс в хранилище экземпляров, связанном с приложением. Метод <xref:System.Activities.WorkflowApplication.Unload%2A> сохраняет рабочий процесс в хранилище экземпляров, а затем выгружает экземпляр из памяти. **Нагрузки** метод загружает рабочий процесс в память с помощью рабочего процесса данные, хранящиеся в хранилище сохраняемости экземпляра.  
  
 **Persist** метод выполняет следующие действия:  
  
1. Приостанавливает работу планировщика рабочих процессов и ждет перехода рабочего процесса в состояние бездействия.  
  
2. Сохраняет рабочий процесс в хранилище сохраняемости.  
  
3. Возобновляет работу планировщика рабочих процессов.  
  
 **Unload** метод выполняет следующие действия:  
  
1. Приостанавливает работу планировщика рабочих процессов и ждет перехода рабочего процесса в состояние бездействия.  
  
2. Сохраняет рабочий процесс в хранилище сохраняемости.  
  
3. Удаляет экземпляр рабочего процесса из памяти.  
  
 Оба **Persist** и **Unload** методы будут блокироваться, пока рабочий процесс находится в зоне несохраняемости, пока рабочий процесс выходит из зоны несохраняемости. Метод продолжает работу, выполняя операции сохранения или выгрузки после выхода из зоны несохраняемости. Если зона несохраняемости не завершается до истечения времени ожидания или если процесс сохраняемости занимает слишком много времени, формируется исключение TimeoutException.  
  
## <a name="enable-persistence-for-workflow-services-in-code"></a>Включение сохраняемости для служб Workflow Services в коде  
 **DurableInstancingOptions** членом <xref:System.ServiceModel.WorkflowServiceHost> класс имеет свойство с именем **InstanceStore** , можно использовать для связать хранилище экземпляров с **WorkflowServiceHost** .  
  
```  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
```  
  
 Когда **WorkflowServiceHost** будет открыт, сохраняемость автоматически включена, если **DurableInstancingOptions.InstanceStore** не равно null.  
  
 Как правило, поведение служб предоставляет конкретное хранилище экземпляров для использования с узлом службы рабочего процесса с помощью **InstanceStore** свойство. Например, SqlWorkflowInstanceStoreBehavior создает экземпляр класса **SqlWorkflowInstanceStore**, настраивает и присваивает его **DurableInstancingOptions.InstanceStore**.  
  
## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a>Включение сохраняемости для служб Workflow Services с помощью файла конфигурации приложения  
 Сохраняемость можно включить с помощью файла конфигурации приложения, добавив следующий код в файл app.config или web.config.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="myBehavior">  
          <SqlWorkflowInstanceStore connectionString="Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase">  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
```
