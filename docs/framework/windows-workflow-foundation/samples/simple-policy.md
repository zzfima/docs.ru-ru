---
title: "Простая политика"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 884a099c1334b53c904173987d2f1ccfe6dd741a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="simple-policy"></a>Простая политика
В данном образце показано, как использовать действие класса <xref:System.Workflow.Activities.PolicyActivity> в рабочем процессе.  
  
 В этом образце последовательный рабочий процесс создается с помощью действия класса <xref:System.Workflow.Activities.PolicyActivity>. Рабочий процесс определяет поля `orderValue`, `customerType` и `discount`, которые используются для определения рабочего процесса скидки на товар. Правила, определенные в наборе файлов правил, задают значение скидки на основе значений `orderValue` и `customerType`. Значения `orderValue` и `customerType` заданы в определении класса `SimplePolicyWorkflow`, и их можно редактировать, чтобы изменить поведение. Конечная скидка записывается в консоль в обработчике событий <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted>, определенном в классе `SimplePolicyWorkflow`.  
  
### <a name="to-build-the-sample"></a>Сборка образца  
  
1.  Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.  
  
3.  Запустите решение без отладки, нажав сочетание клавиш CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Выполнение образца  
  
-   В окне командной строки пакета SDK запустите файл с расширением EXE в папке «SimplePolicy\bin\debug» (или в папке «SimplePolicy\bin» для образца в Visual Basic), вложенной в главную папку образца.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец находится в следующем каталоге:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [Дополнительная политика](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
