---
title: "Образец компенсируемого действия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4ad3de1b3e9361e5de4803e06c8d257fbb9de76e
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="compensable-activity-sample"></a>Образец компенсируемого действия
В этом образце демонстрируется использование действия `CompensableActivity` для определения задания, необходимого для выполнения в ходе этого действия при нормальном течении процесса, и задания, необходимого для выполнения компенсации этого действия, если это потребуется позднее.  В первой части образца показан способ определения единиц подлежащего компенсации задания в [!INCLUDE[wf](../../../../includes/wf-md.md)] с использованием действия `CompensableActivity` и способ их исполнения при успешном выполнении.  Во второй части образца показано, как те же единицы подлежащего компенсации задания автоматически проводят компенсацию при возникновении неожиданного события и при отмене экземпляра рабочего процесса.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте в среде Visual Studio 2010 решение CompensableActivity.sln.  
  
2.  Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.  
  
3.  Запустите приложение, нажав клавишу F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`