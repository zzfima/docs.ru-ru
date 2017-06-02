---
title: "Обработка ошибок в действии блок-схемы с помощью TryCatch | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Обработка ошибок в действии блок-схемы с помощью TryCatch
В этом образце показано использование действия <xref:System.Activities.Statements.TryCatch> в рамках действия сложного потока управления.  
  
 В этом образце промокод и несколько дочерних элементов передаются как переменные в действие <xref:System.Activities.Statements.Flowchart>, которое вычисляет скидку на основе формулы, которая соответствует промокоду.Образец включает императивный код и версии конструктора рабочих процессов образца.  
  
 В следующей таблице представлены переменные для действия `CreateFlowchartWithFaults`.  
  
|Параметры|Описание|  
|---------------|--------------|  
|promoCode|Промокод.Тип данных: String<br /><br /> Возможные значения с описанием в скобках.<br /><br /> -   Single \(холост\)<br />-   MNK \(женат, детей нет\).<br />-   MWK \(женат, есть дети\).|  
|numKids|Число детей.Тип: int|  
  
 Действие `CreateFlowchartWithFaults` использует действие <xref:System.Activities.Statements.FlowSwitch%601>, которое производит переключения на аргументе `promoCode` и вычисляет скидку с использованием следующей формулы.  
  
|Значение `promoCode`|Скидка \(%\)|  
|--------------------------|------------------|  
|Single|10|  
|MNK|15|  
|MWK|15 \+ \(1 – 1\/`numberOfKids`\)\*10 **Note:**  Это вычисление может вызвать исключение <xref:System.DivideByZeroException>.Поэтому вычисление скидки упаковано в действие <xref:System.Activities.Statements.TryCatch>, которое кэширует исключение <xref:System.DivideByZeroException> и устанавливает скидку в нуль.|  
  
#### Использование этого образца  
  
1.  Откройте файл решения FlowchartWithFaultHandling.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL\+SHIFT\+B.  
  
3.  Чтобы запустить решение, нажмите клавишу F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## См. также  
 [Рабочие процессы блок\-схемы](../../../../docs/framework/windows-workflow-foundation//flowchart-workflows.md)   
 [Исключения](../../../../docs/framework/windows-workflow-foundation//exceptions.md)