---
title: "Предоставление и вызов действий ActivityActions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 45920f913a1d7252858fd0e563da944c10fae75c
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="exposing-and-invoking-activityactions"></a>Предоставление и вызов действий ActivityActions
В этом образце показано, как разработать настраиваемое действие, имеющее <xref:System.Activities.ActivityAction>. Также демонстрируется, как использовать данное действие, обеспечив реализацию <xref:System.Activities.ActivityAction>.  
  
 <xref:System.Activities.ActivityAction> Позволяет создателям действий предоставлять «дыры» с определенными сигнатурами которых пользователи действия могут подключить пользовательское поведение. Например <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` действия (совершающее операции с коллекцией элементов) имеет <xref:System.Activities.ActivityAction> , позволяет пользователю действия подключить поведение, работающее с текущим элементом итерации.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте **ActivityAction.sln** образец решения в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите это решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`