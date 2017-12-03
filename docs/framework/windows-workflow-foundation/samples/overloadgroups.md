---
title: OverloadGroups
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f644f09af3ce9e191dc6c5680472de4ef5ab727d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="overloadgroups"></a>OverloadGroups
Этот образец состоит из действия (`CreateLocation`) с двумя интересными характеристиками.  
  
1.  Оно имеет несколько обязательных и несколько необязательных аргументов.  
  
2.  С его помощью пользователь может выбрать предоставление одного или двух разных наборов аргументов.  
  
 Такие поведения достигаются с помощью двух следующих функций.  
  
-   `[isRequired]` проверяет, является ли свойство или определенное действие assign, и, если не является, формирует исключение.  
  
-   `[OverloadGroup]` составляет набор аргументов, чтобы пользователь действия мог выбрать, какой из наборов будет использован. В одном и том же экземпляре пользователь не может использовать аргументы из различных групп перегруженных вариантов.  
  
 После настройки различных рабочих процессов вызовите метод <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, возвращающий коллекцию <xref:System.Activities.Validation.ValidationResults> объектов <xref:System.Activities.Validation.Constraint>. Вывести объекты <xref:System.Activities.Validation.Constraint> в консоль.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте **OverloadGroups.sln** образец решения в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите это решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
