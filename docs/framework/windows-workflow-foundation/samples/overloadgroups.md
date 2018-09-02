---
title: OverloadGroups
ms.date: 03/30/2017
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
ms.openlocfilehash: 0773e76d36b25ad5485cc8912c7012815412de9f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43469873"
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
