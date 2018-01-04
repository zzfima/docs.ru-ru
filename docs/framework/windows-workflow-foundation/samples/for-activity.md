---
title: "Для действия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3305defd4f2819a3ebe9d3b7429ddac11ae6833
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="for-activity"></a>Для действия
В образце For демонстрируется построение пользовательского действия, которое наследует от <xref:System.Activities.NativeActivity> и используется в рабочем процессе для выполнения реального примера. Пользовательское действие в этом образце работает подобно инструкции `for` языка C#. T  
  
 Пользовательское действие `For` имеет свойства `InitAction`, `IterationAction`, `Condition` и `Body`, которые соответствуют оператору инициализации, оператору итерации, условию продолжения и оператору тела, обычно присутствующим в стандартной инструкции `For` языка C#.  
  
 В следующей таблице описаны файлы ключа в образце.  
  
|Файл|Описание|  
|----------|-----------------|  
|For.cs|Определение класса для пользовательского действия `For`, которое расширяет класс <xref:System.Activities.NativeActivity> и обеспечивает функциональность, аналогичную оператору `For` языка C#.|  
|Program.cs|Клиентское приложение, которое выполняет базовый перебор (итерацию по) коллекции с помощью пользовательского действия `For`.|  
  
> [!NOTE]
>  При применении пользовательского действия `For` убедитесь, что задано свойство `Condition`. В противном случае может произойти зацикливание.  
  
## <a name="demonstrates"></a>Демонстрации  
 Создайте пользовательское действие, которое наследует от класса <xref:System.Activities.NativeActivity>.  
  
## <a name="discussion"></a>Обсуждение  
 В следующей таблице представлено описание свойств действия, используемого в этом образце.  
  
 InitAction  
 Инструкция инициализации  
  
 IterationAction  
 Инструкция итерации  
  
 Условие  
 Инструкция продолжения  
  
 Body  
 Инструкция текста (цикла)  
  
 Действие наследует от действия <xref:System.Activities.NativeActivity> для получения доступа к функциям времени выполнения, таким как планирование выполнения дополнительных действий с помощью одного из методов `ScheduleActivity` из контекста <xref:System.Activities.NativeActivityContext>.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения For.sln.  
  
2.  Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.  
  
3.  Запустите решение, нажав клавишу F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`