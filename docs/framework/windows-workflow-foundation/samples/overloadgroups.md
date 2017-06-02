---
title: "OverloadGroups | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# OverloadGroups
Этот образец состоит из действия \(`CreateLocation`\) с двумя интересными характеристиками.  
  
1.  Оно имеет несколько обязательных и несколько необязательных аргументов.  
  
2.  С его помощью пользователь может выбрать предоставление одного или двух разных наборов аргументов.  
  
 Такие поведения достигаются с помощью двух следующих функций.  
  
-   `[isRequired]` проверяет, является ли свойство или определенное действие assign, и, если не является, формирует исключение.  
  
-   `[OverloadGroup]` составляет набор аргументов, чтобы пользователь действия мог выбрать, какой из наборов будет использован.В одном и том же экземпляре пользователь не может использовать аргументы из различных групп перегруженных вариантов.  
  
 После настройки различных рабочих процессов вызовите метод <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, возвращающий коллекцию <xref:System.Activities.Validation.ValidationResults> объектов <xref:System.Activities.Validation.ConstraintViolation>.Вывести объекты <xref:System.Activities.Validation.ConstraintViolation> в консоль.  
  
### Настройка, построение и выполнение образца  
  
1.  Откройте образец решения **OverloadGroups.sln** в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`  
  
## См. также