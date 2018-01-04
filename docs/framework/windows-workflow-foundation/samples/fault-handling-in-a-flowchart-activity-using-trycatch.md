---
title: "Обработка ошибок в действии блок-схемы с помощью TryCatch"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a179ae5aaca959383a88105b96cbba2cebd1919
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a>Обработка ошибок в действии блок-схемы с помощью TryCatch
В этом образце показано использование действия <xref:System.Activities.Statements.TryCatch> в рамках действия сложного потока управления.  
  
 В этом образце промокод и несколько дочерних элементов передаются как переменные в действие <xref:System.Activities.Statements.Flowchart>, которое вычисляет скидку на основе формулы, которая соответствует промокоду. Образец включает императивный код и версии конструктора рабочих процессов образца.  
  
 В следующей таблице представлены переменные для действия `CreateFlowchartWithFaults`.  
  
|Параметры|Описание|  
|----------------|-----------------|  
|promoCode|Промокод. Тип данных: String<br /><br /> Возможные значения с описанием в скобках.<br /><br /> -Одно (один)<br />-MNK (женат, детей нет.)<br />-MWK (женат, детей.)|  
|numKids|Число детей. Тип: int|  
  
 Действие `CreateFlowchartWithFaults` использует действие <xref:System.Activities.Statements.FlowSwitch%601>, которое производит переключения на аргументе `promoCode` и вычисляет скидку с использованием следующей формулы.  
  
|Значение `promoCode`|Скидка (%)|  
|--------------------------|--------------------|  
|Single|10|  
|MNK|15|  
|MWK|15 + (1 – 1 /`numberOfKids`)\*10 **Примечание:** потенциально может вызвать это вычисление <xref:System.DivideByZeroException>. Поэтому вычисление скидки упаковано в действие <xref:System.Activities.Statements.TryCatch>, которое кэширует исключение <xref:System.DivideByZeroException> и устанавливает скидку в нуль.|  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл решения FlowchartWithFaultHandling.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавишу F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a>См. также  
 [Рабочие процессы с блок-схемой](../../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)  
 [Исключения](../../../../docs/framework/windows-workflow-foundation/exceptions.md)
