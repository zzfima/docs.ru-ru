---
title: Типы ограничений
ms.date: 03/30/2017
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
ms.openlocfilehash: 202a2c7b3a3fc400552e42c8606457964af66af2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506616"
---
# <a name="constraint-types"></a>Типы ограничений
Этот образец демонстрирует два способа применения ограничений к рабочему процессу, один из которых применяется изнутри действия (сборка), а второй - снаружи действия (политика). В этом сценарии создатель действия (представитель сторонней компании-разработчика программного обеспечения) желает проверить соотношение между двумя аргументами. В этом случае стоимость не должна превышать цену. Это является общим проверочным ограничением для сборки.  
  
 Затем владелец магазина желает добавить к этому общему действию ряд других проверок. Допустим, он желает, чтобы большая часть его продуктов имела стоимость 9,99 долларов или менее. Для этого он использует ограничение политики, являющееся надстройкой над действием `CreateProduct`.  
  
 В данном образце:  
  
 Создатель действия (сборка) должен:  
  
-   Создайте ограничение (`PriceGreaterThanCost`). Здесь размещается вся логика проверки.  
  
-   Переопределите `System.Activities.CodeActivity.OnGetConstraints()` и добавьте ограничение (`PriceGreaterThanCost`) в список ограничений <xref:System.Collections.IList>.  
  
 Создатель рабочего процесса (политика) должен:  
  
-   Создайте рабочий процесс с экземпляром действия для проверки (`CreateProduct`).  
  
-   Создайте ограничение (`MaxPrice`).  
  
-   Создать экземпляр <xref:System.Activities.Validation.ValidationSettings> (`validationSettings`) и добавить ограничение (`MaxPrice`) к коллекции `AdditionalConstraints`. В этом случае создатель рабочего процесса может добавить ограничения политики к любому действию, например, к последовательному или параллельному.  
  
-   Вызвать метод <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, возвращающий коллекцию <xref:System.Activities.Validation.ValidationResults> объектов <xref:System.Activities.Validation.ValidationError>.  
  
-   Напечатайте объекты <xref:System.Activities.Validation.ValidationError> (необязательно).  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте образец решения ConstraintTypes.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите это решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`