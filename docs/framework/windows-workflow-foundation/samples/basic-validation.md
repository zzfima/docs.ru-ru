---
title: Базовая проверка
ms.date: 03/30/2017
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
ms.openlocfilehash: 74d99e2d426e9ea5701fad80418fdf019112cc9e
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44264241"
---
# <a name="basic-validation"></a>Базовая проверка
Этот образец демонстрирует действие `CreateProduct`, проверяющее, что аргумент `Cost` меньше аргумента `Price` или равен ему.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Проверку осуществляют два создателя: создатель действия (создает логику проверки для действия) и создатель рабочего процесса, вызывающий службы проверки для конкретного рабочего процесса. В этом сценарии создатель действия желает обеспечить стоимость каждого экземпляра действия, которая меньше цены или равна ей.  
  
 Создатель действия (внутри действия) должен:  
  
-   Создайте ограничение (`PriceGreaterThanCost`). Здесь размещается вся логика проверки.  
  
-   Переопределите `System.Activities.CodeActivity.OnGetConstraints()` и добавьте ограничение (`PriceGreaterThanCost`) в список ограничений <xref:System.Collections.IList>.  
  
 Создатель рабочего процесса (главная программа) должен:  
  
-   Создайте рабочий процесс с экземпляром действия для проверки (`CreateProduct`).  
  
-   Вызывает метод <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, возвращающий коллекцию <xref:System.Activities.Validation.ValidationResults> объектов <xref:System.Activities.Validation.ValidationError>.  
  
-   Напечатайте объекты <xref:System.Activities.Validation.ValidationError> (необязательно).  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте образец решения BasicValidation.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите это решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`