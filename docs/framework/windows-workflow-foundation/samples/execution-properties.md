---
title: Свойства выполнения
ms.date: 03/30/2017
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
ms.openlocfilehash: 4906c2ad11c8b5822764435d2b39a5b51f2673ba
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43748198"
---
# <a name="execution-properties"></a>Свойства выполнения
В этом образце показано, как определить и использовать свойство выполнения в настраиваемом действии. В этом примере свойство выполнения определяет цвет переднего плана консоли. Рабочий процесс в примере показывает, как разные логические пути выполнения (ответвления действия <xref:System.Activities.Statements.Parallel>) могут поддерживать различные цвета консоли, несмотря на поочередное исполнение действий (по всем ответвлениям действия <xref:System.Activities.Statements.Parallel>).  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте образец решения ExecutionProperties.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    > [!NOTE]
    >  При попытке просмотра ThreeColors.xaml до построения решения произойдет ошибка, поскольку применяемые пользовательские действия должны быть построены одновременно с решением.  
  
2.  Постройте и запустите это решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`