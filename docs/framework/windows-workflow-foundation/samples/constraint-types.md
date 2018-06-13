---
title: Типы ограничений
ms.date: 03/30/2017
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
ms.openlocfilehash: 53e5975017c3a27ede8ad07cd93f78f71df2d3e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517512"
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`