---
title: "Шаблон автоподтверждения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 668aec65-78d3-4636-9c7b-deed643a18f9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aaf4d72396438178d807f28ba8cb0ac5c5cb368e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="auto-confirm-pattern"></a>Шаблон автоподтверждения
Данный образец включает три сценария, иллюстрирующих пользовательское действие `AutoConfirmScope`. В первом образце показано успешное выполнение последовательности из четырех подлежащих компенсации действий, из которых второе и третье действия являются вложенными в `AutoConfirmScope`. Во втором образце показана та же последовательность с исключением, сформированным после выполнения четвертого действия <xref:System.Activities.Statements.CompensableActivity>. В третьем сценарии показана та же последовательность с исключением, сформированным в `AutoConfirmScope` после завершения второго действия <xref:System.Activities.Statements.CompensableActivity>.  
  
 В образце демонстрируется шаблон автоматического подтверждения, в котором все дочерние действия, подлежащие компенсации, подтверждаются после успешного завершения области. Этот шаблон определяет время существования всех дочерних действий, подлежащих компенсации, поскольку они больше не могут быть компенсированы или подтверждены.  
  
 Область включает объект <xref:System.Activities.Statements.TryCatch>, где <xref:System.Activities.Statements.TryCatch.Try%2A> является внутренним действием <xref:System.Activities.Statements.CompensableActivity>. Определенное пользователем текст действия `AutoConfirmScope` является текстом внутреннего действия <xref:System.Activities.Statements.CompensableActivity>. Когда это внутреннее действие <xref:System.Activities.Statements.CompensableActivity> завершается, оно создает объект <xref:System.Activities.Statements.CompensationToken> как выходной аргумент. Действие `AutoConfirmScope` использует свойство <xref:System.Activities.Statements.TryCatch.Finally%2A> для проверки, создан ли маркер, и если да, то подтверждает внутреннее действие <xref:System.Activities.Statements.CompensableActivity>. Внутреннее действие <xref:System.Activities.Statements.CompensableActivity> вызывает компенсацию по умолчанию для всех подлежащих компенсации действий, которые могут существовать в его теле.  
  
 В первом сценарии показано успешное выполнение рабочего процесса, и демонстрируется, что второе и третье действия, подлежащие компенсации, уже подтверждены, когда завершается рабочий процесс, а первое и четвертое действия подтверждаются. При этом создается порядок подтверждения: третье, второе, четвертое и первое.  
  
 Во втором сценарии показано исключение после завершения четырех подлежащих компенсации действий. Поскольку второе и третье подлежащие компенсации действия уже подтверждены, они не затрагиваются, но первое и четвертое компенсируются. При этом создается порядок следующий порядок: подтверждение третьего, подтверждение второго, компенсация четвертого и компенсация первого.  
  
 В последнем сценарии показано неуспешное выполнение действия `AutoConfirmScope`. В этом сценарии исключение возникает после завершения второго действия <xref:System.Activities.Statements.CompensableActivity>. Поскольку третье и четвертое подлежащие компенсации действия не выполнялись, они не затрагиваются. Поскольку область не завершена успешно, второе действие <xref:System.Activities.Statements.CompensableActivity> не подтверждено. При этом создается порядок подтверждения: второе, затем первое.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  В среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] откройте файл решения AutoConfirmSample.sln.  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Compensation\AutoConfirm`