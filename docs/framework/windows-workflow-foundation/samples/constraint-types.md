---
title: "Типы ограничений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Типы ограничений
Этот образец демонстрирует два способа применения ограничений к рабочему процессу, один из которых применяется изнутри действия \(сборка\), а второй — снаружи действия \(политика\).В этом сценарии создатель действия \(представитель сторонней компании\-разработчика программного обеспечения\) желает проверить соотношение между двумя аргументами.В этом случае стоимость не должна превышать цену.Это является общим проверочным ограничением для сборки.  
  
 Затем владелец магазина желает добавить к этому общему действию ряд других проверок.Допустим, он желает, чтобы большая часть его продуктов имела стоимость 9,99 долларов или менее.Для этого он использует ограничение политики, являющееся надстройкой над действием `CreateProduct`.  
  
 В данном образце:  
  
 Создатель действия \(сборка\) должен:  
  
-   Создайте ограничение \(`PriceGreaterThanCost`\).Здесь размещается вся логика проверки.  
  
-   Переопределите <xref:System.Activities.CodeActivity%601.OnGetConstraints%2A> и добавьте ограничение \(`PriceGreaterThanCost`\) в список ограничений <xref:System.Collections.IList>.  
  
 Создатель рабочего процесса \(политика\) должен:  
  
-   Создайте рабочий процесс с экземпляром действия для проверки \(`CreateProduct`\).  
  
-   Создайте ограничение \(`MaxPrice`\).  
  
-   Создать экземпляр <xref:System.Activities.Validation.ValidatorSettings> \(`validatorSettings`\) и добавить ограничение \(`MaxPrice`\) к коллекции `AdditionalConstraints`.В этом случае создатель рабочего процесса может добавить ограничения политики к любому действию, например, к последовательному или параллельному.  
  
-   Вызвать метод <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, возвращающий коллекцию <xref:System.Activities.Validation.ValidationResults> объектов <xref:System.Activities.Validation.ConstraintViolation>.  
  
-   Напечатайте объекты <xref:System.Activities.Validation.ConstraintViolation> \(необязательно\).  
  
### Настройка, построение и выполнение образца  
  
1.  Откройте образец решения ConstraintTypes.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`  
  
## См. также