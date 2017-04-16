---
title: "Предоставление и вызов действий ActivityActions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Предоставление и вызов действий ActivityActions
В этом образце показано, как разработать настраиваемое действие, имеющее <xref:System.Activities.ActivityAction>.Также демонстрируется, как использовать данное действие, обеспечив реализацию <xref:System.Activities.ActivityAction>.  
  
 <xref:System.Activities.ActivityAction> позволяет создателям действий предоставлять «дыры» с определенными сигнатурами, для которых пользователи действия могут подключить пользовательское поведение.Например, действие <xref:System.Activities.Statements.ForEach> \(совершающее операции с коллекцией элементов\) имеет <xref:System.Activities.ActivityAction>, что позволяет пользователю действия подключить поведение, работающее с текущим элементом итерации.  
  
#### Настройка, построение и выполнение образца  
  
1.  Откройте образец решения **ActivityAction.sln** в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`  
  
## См. также