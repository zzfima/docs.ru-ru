---
title: "Использование CancellationScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 39c5c338-b316-43d6-b7fe-a543281dd1ec
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d621991c1250c073e485193059d426e7cd4682f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-cancellationscope"></a>Использование CancellationScope
В данном образце показывается, как с помощью действия <xref:System.Activities.Statements.CancellationScope> отменять работу в приложении.  
  
 Во многих компонентах и службах среднего уровня отмена работ зависит от хорошо известных программных конструкций транзакций, которые непосредственно и отрабатывают отмену.  Тем не менее, во многих случаях требуется отменить работу, которую нельзя совершить в транзакции.  Отменой пользоваться сложнее, чем транзакциями, поскольку отменяемую работу необходимо сначала отследить. [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] облегчает это, предоставляя действие <xref:System.Activities.Statements.CancellationScope>.  
  
 Отмену можно запустить как изнутри действия, так и из его родительского элемента.  Дочерние действия планируются своим родительским действием (например, <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.Flowchart> или пользовательским составным действием).  Родительское действие может отменить дочерние действия по любой причине.  Например, действие <xref:System.Activities.Statements.Parallel> с тремя дочерними ветвями отменяет остающиеся дочерние ветви, как только хоть одна ветвь будет выполнена и при вычислении выражения <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> будет получено значение `true`. Рабочий процесс можно отменить и извне, вызвав из ведущего приложения метод <xref:System.Activities.WorkflowApplication.Cancel%2A>.  
  
 Чтобы использовать действие <xref:System.Activities.Statements.CancellationScope>, поместите отменяемую работу в <xref:System.Activities.Statements.CancellationScope.Body%2A>, а работу, выполняемую после отмены, в <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>.  
  
 В образце показана отмена действия из самого действия.  
  
 В сценарии, с помощью которого образец демонстрирует действие <xref:System.Activities.Statements.CancellationScope>, клиенту необходимо как можно быстрее купить билет до Майами. Свои услуги ему предлагают два туристических агентства. Чтобы смоделировать бизнес-логику процесса, в образце используется две области <xref:System.Activities.Statements.CancellationScope> в действии <xref:System.Activities.Statements.Parallel>. Параметр <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> действия <xref:System.Activities.Statements.Parallel> установлен в значение `true`; поскольку <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> проверяется после выполнения любой из ветвей, оставшаяся ветвь будет отменена после выполнения первой. Клиентское приложение запрашивает оба бюро о покупке билетов, и когда одно из них подтверждает покупку билета, заказ во втором бюро отменяется.  
  
## <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения CancelationScopeXAML.sln.  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\CancellationScope`  
  
## <a name="see-also"></a>См. также
