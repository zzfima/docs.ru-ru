---
title: "Обработчик отмены действия, подлежащего компенсации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: afd98bee-eccf-47e9-99c9-27cea84ce5ce
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Обработчик отмены действия, подлежащего компенсации
В этом образце показано использование обработчика отмены в <xref:System.Activities.Statements.CompensableActivity>.  
  
 Образец содержит два сценария, демонстрирующих использования отмены <xref:System.Activities.Statements.CompensableActivity>. Первый сценарий содержит корневое действие, подлежащее компенсации, включающее в себя три дочерних действия, подлежащих компенсации.Два дочерних действия успешно заканчивают выполнение своих действий.Когда выполняется текст третьего дочернего действия, встречает исключение, осуществляющее отмену обработки третьего действия, что вызывает, в свою очередь, отмену корневого действия.Логика корневого действия в данном примере состоит в компенсации двух других дочерних действий, завершившихся ранее.  
  
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
  
 Второй сценарий демонстрирует выполнение <xref:System.Activities.Statements.TryCatch> параллельно с <xref:System.Activities.Statements.Delay>, завершающееся до ветви <xref:System.Activities.Statements.TryCatch>.Для условия завершения устанавливается значение `true` после завершения выполнения первой ветви, в результате чего вторая ветвь отменяется.  
  
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
  
### Настройка, построение и выполнение образца  
  
1.  Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте CompensationCancellation.sln.  
  
2.  Постройте образец, нажав клавишу CTRL\+SHIFT\+B, или выберите команду «Построить решение» в меню «Построение».  
  
3.  Запустите образец, нажав F5, или выберите команду Начать отладку в меню Отладка.Другой способ — нажать Ctrl\+F5 или выбрать команду Запуск без отладки в меню Отладка.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`  
  
## См. также