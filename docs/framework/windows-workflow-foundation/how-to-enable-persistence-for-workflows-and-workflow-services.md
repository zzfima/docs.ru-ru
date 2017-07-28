---
title: "Как включить сохраняемость для рабочих процессов и служб рабочих процессов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Как включить сохраняемость для рабочих процессов и служб рабочих процессов
В этом разделе описывается процесс включения сохраняемости для рабочих процессов и служб рабочих процессов.  
  
## Включение сохраняемости для рабочих процессов  
 Посредством свойства <xref:System.Activities.WorkflowApplication.InstanceStore%2A> класса <xref:System.Activities.WorkflowApplication> можно связать хранилище экземпляров с **WorkflowApplication**.Метод <xref:System.Activities.WorkflowApplication.Persist%2A> сохраняет рабочий процесс в хранилище экземпляров, связанном с приложением.Метод <xref:System.Activities.WorkflowApplication.Unload%2A> сохраняет рабочий процесс в хранилище экземпляров, а затем выгружает экземпляр из памяти.Метод **Load** загружает рабочий процесс в память, используя данные рабочего процесса из хранилища сохраняемости экземпляра.  
  
 Метод **Persist** выполняет следующие шаги.  
  
1.  Приостанавливает работу планировщика рабочих процессов и ждет перехода рабочего процесса в состояние бездействия.  
  
2.  Сохраняет рабочий процесс в хранилище сохраняемости.  
  
3.  Возобновляет работу планировщика рабочих процессов.  
  
 Метод **Unload** выполняет следующие шаги.  
  
1.  Приостанавливает работу планировщика рабочих процессов и ждет перехода рабочего процесса в состояние бездействия.  
  
2.  Сохраняет рабочий процесс в хранилище сохраняемости.  
  
3.  Удаляет экземпляр рабочего процесса из памяти.  
  
 Методы **Persist** и **Unload** блокируются на время нахождения рабочего процесса в зоне несохраняемости до тех пор, пока рабочий процесс не выйдет из этой зоны.Метод продолжает работу, выполняя операции сохранения или выгрузки после выхода из зоны несохраняемости.Если зона несохраняемости не завершается до истечения времени ожидания или если процесс сохраняемости занимает слишком много времени, формируется исключение TimeoutException.  
  
## Включение сохраняемости для служб рабочих процессов в коде  
 Элемент **DurableInstancingOptions** класса <xref:System.ServiceModel.WorkflowServiceHost> имеет свойство **InstanceStore**, с помощью которого хранилища экземпляров вы можете связывать с **WorkflowServiceHost**.  
  
```  
  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
  
```  
  
 Когда **WorkflowServiceHost** открыт, сохраняемость автоматически включена, если **DurableInstancingOptions.InstanceStore** имеет значение, отличное от null.  
  
 Обычно поведение служб предоставляет конкретное хранилище экземпляров, которое используется узлом службы рабочих процессов с помощью свойства **InstanceStore**.Например, SqlWorkflowInstanceStoreBehavior создает экземпляр **SqlWorkflowInstanceStore**, настраивает и присваивает его **DurableInstancingOptions.InstanceStore**.  
  
## Включение сохраняемости для служб рабочих процессов с помощью файла конфигурации приложения  
 Сохраняемость можно включить с помощью файла конфигурации приложения, добавив следующий код в файл app.config или web.config.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name=”myBehavior”>  
          <SqlWorkflowInstanceStore connectionString=”Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase”>  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
  
```