---
title: Простая политика
ms.date: 03/30/2017
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
ms.openlocfilehash: dff3979d75fdeb5a45be3940af3568c26f5e8f98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец находится в следующем каталоге:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [Дополнительная политика](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
