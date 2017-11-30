---
title: "Базовая проверка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dd6f85dc7961a7c3fd51e67b9fd6e16de9faa41d
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
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
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`