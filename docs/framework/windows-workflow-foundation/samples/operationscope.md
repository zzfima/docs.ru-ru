---
title: Действие OperationScope
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3bf92d7a726a53c5d625f31b0386e11c941cdde9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="operationscope"></a>Действие OperationScope
В этом образце демонстрируется использование действий по обмену сообщениями <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply> для представления существующего пользовательского действия в качестве операции в службе рабочего процесса. Этот пример включает новое пользовательское действие, названное `OperationScope`. Оно предназначено для облегчения разработки службы рабочего процесса, позволяя пользователям отдельно записывать текст их операций как пользовательские действия, а затем представляя их как операции службы, использующие действие `OperationScope`. Например, пользовательское действие `Add`, которое принимает два аргумента `in` и возвращает один аргумент `out`, может быть представлено как операция `Add` в рабочем процессе путем перетаскивания его в область `OperationScope`.  
  
 Область работает, проверяя действие, предоставленное как ее текст. Предполагается, что непривязанные аргументы `in` являются входными данными из входящего сообщения. Предполагается, что все аргументы `out`, независимо от того, являются ли они привязанными, являются выходными данными в последующем ответном сообщении. Имя предоставляемой операции берется на основе отображаемого имени действия `OperationScope`. Конечным результатом является действие текста, упакованное в <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply> с параметрами из сообщений, привязанных к аргументам действия.  
  
 В этом образце доступ к службе рабочего процесса предоставляется через конечные точки HTTP. Для запуска должны быть добавлены правильные списки URL-адресов ACL. Дополнительные сведения см. в разделе [Настройка протоколов HTTP и HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353). Выполнив следующую команду в командной строке с повышенными привилегиями добавляет соответствующие ACL (Убедитесь, заменены домен и имя пользователя для домена %\\% UserName %).  
  
 **добавить urlacl url-адрес Netsh http =http://+:8000/ пользователь = % DOMAIN %\\% UserName %**  
  
### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Откройте решение OperationScope.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Задайте несколько запускаемых проектов, щелкните правой кнопкой мыши решение в обозревателе решений и выбрав **назначить запускаемые проекты**. Добавьте Scenario и Scenario_Client (в этом порядке) в качестве запускаемых проектов.  
  
3.  Чтобы построить решение, нажмите CTRL+SHIFT+B.  
  
    > [!WARNING]
    >  Этот шаг является обязательным для просмотра рабочего процесса BankService.xaml из-за пользовательского действия `OperationScope`.  
  
4.  Нажмите CTRL+F5, чтобы запустить приложение. На консоли Scenario_Client запрашиваются входные данные, и соответствующий вывод виден на консоли Scenario.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`