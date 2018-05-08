---
title: Обработчик отмены действия, подлежащего компенсации
ms.date: 03/30/2017
ms.assetid: afd98bee-eccf-47e9-99c9-27cea84ce5ce
ms.openlocfilehash: ce4d67b26a2b4c6a9b507715b48e75e328c5b100
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cancellation-handler-on-compensable-activity"></a>Обработчик отмены действия, подлежащего компенсации
В этом образце показано использование обработчика отмены в <xref:System.Activities.Statements.CompensableActivity>.  
  
 Образец содержит два сценария, демонстрирующих использования отмены <xref:System.Activities.Statements.CompensableActivity>. Первый сценарий содержит корневое действие, подлежащее компенсации, включающее в себя три дочерних действия, подлежащих компенсации. Два дочерних действия успешно заканчивают выполнение своих действий. Когда выполняется текст третьего дочернего действия, встречает исключение, осуществляющее отмену обработки третьего действия, что вызывает, в свою очередь, отмену корневого действия. Логика корневого действия в данном примере состоит в компенсации двух других дочерних действий, завершившихся ранее.  
  
```  
Try  
{  
    CA   
    {  
        CA1   
        {  
        }  
        CA2  
        {  
        }  
        CA3  
        {  
            //Exception here  
            // Then this will get cancelled  
        }  
  
       // Cancellation for the root activity automatically gets called, which, in turn, adds some logic to revert what was done (Or can decide to actually confirm CA1 & CA2 if the user so desires).  
    }  
}  
Catches {  
// Can do more stuff...  
}  
```  
  
 Второй сценарий демонстрирует выполнение <xref:System.Activities.Statements.TryCatch> параллельно с <xref:System.Activities.Statements.Delay>, завершающееся до ветви <xref:System.Activities.Statements.TryCatch>. Для условия завершения устанавливается значение `true` после завершения выполнения первой ветви, в результате чего вторая ветвь отменяется.  
  
```  
Parallel   
{  
    Branch1   
    {  
        // Small Delay that times out (timeout1) before branch2.  
    }  
    Branch2   
    {  
        CA   
        {  
            CA1   
            {  
            }  
            CA2   
            {  
            }  
            CA3   
            {  
            }  
            If (timeout1)    
            {  
                call Cancel CA  
            }  
        }  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте CompensationCancellation.sln.  
  
2.  Выполните сборку образца, нажав сочетание клавиш CTRL+SHIFT+B, или выберите команду «Выполнить сборку решения» в меню «Сборка».  
  
3.  Запустите образец, нажав F5, или выберите команду Начать отладку в меню Отладка. Другой способ - нажать Ctrl+F5 или выбрать команду Запуск без отладки в меню Отладка.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`