---
title: "Проверка внешнего действия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da326969e622a51f6a93b9faf5f81da079ea4003
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="external-activity-validation"></a>Проверка внешнего действия
В этом образце показано, как добавить логику проверки во встроенное действие, созданное другим пользователем. Логика проверки включает принудительное обеспечение для всех свойств <xref:System.Activities.Statements.If>, входящих в рабочий процесс, установки либо свойства <xref:System.Activities.Statements.If.Then%2A>, либо свойства <xref:System.Activities.Statements.If.Else%2A>. Кроме того, логика проверки включает проверку наличия у всех действий <xref:System.Activities.Statements.Pick>, присутствующих в рабочем процессе, нескольких ветвей. В противном случае создается предупреждение.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В данном образце создается рабочий процесс с экземпляром каждого подлежащего проверке действия: действия <xref:System.Activities.Statements.If> и действия <xref:System.Activities.Statements.Pick>. Для каждого вида поведения проверки создается объект <xref:System.Activities.Validation.Constraint>. В этом образце создаются ограничения `ConstraintError_IfShouldHaveThenOrElse` и `ConstraintWarning_PickHasOneBranch`. Далее эти ограничения добавляются в коллекцию `AdditionalConstraints` экземпляра <xref:System.Activities.Validation.ValidationSettings>. Наконец, для проверки действий в рабочем процессе вызывается метод `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> служб <xref:System.Activities.Validation.ActivityValidationServices>, а результаты проверки выводятся на консоль.  
  
> [!NOTE]
>  Ограничения политики можно добавить к любому действию. Например, можно добавить ограничение политики к действию <xref:System.Activities.Statements.Sequence> или <xref:System.Activities.Statements.Parallel>.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл ExternalActivityValidation.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`