---
title: "Группа действий с условиями | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Группа действий с условиями
В данном образце демонстрируется приложение бронирования путешествия.В объекте класса <xref:System.Workflow.Activities.ConditionedActivityGroup> \(CAG\) содержатся два действия кода: действия "Car" и "Airline".В конструкторе `SimpleCAGWorkflow` объект "ArrayList" с именем "travelNeedType" заполняется типами требуемых бронирования путешествия.При комментировании одной или двух этих инструкций `travelNeeds.Add` поведение CAG соответствующим образом изменяется.В обоих действиях "Car" и "Airline" их условие <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>, заполнено объектом класса <xref:System.Workflow.Activities.CodeCondition>.Действие «Car» выполняется, только если в коллекции `travelNeeds` есть запись `TravelNeeds.Car`; действие «Airline» выполняется только в том случае, если в коллекции `travelNeeds` содержится запись `TravelNeeds.Airline`.  
  
 При выполнении каждого из действий из коллекции удаляется соответствующая запись.Условие свойства <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> по умолчанию задает выход из CAG в том случае, если дочерние действия в настоящий момент не выполняются или готовы для выполнения \(в зависимости от их условий <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>\).В данном образце это означает, что выход из CAG выполняется, если коллекция `travelNeeds` пуста.  
  
### Построение образца  
  
1.  Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте решение, нажав клавиши CTRL\+SHIFT\+B.  
  
3.  Запустите решение без отладки, нажав сочетание клавиш CTRL\+F5.  
  
### Запуск образца  
  
-   В окне командной строки пакета SDK запустите файл с расширением EXE в папке «SimpleCAG\\bin\\debug» \(или в папке «SimpleCAG\\bin» для образца в Visual Basic\), вложенной в главную папку образца.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец находится в следующем каталоге:  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## См. также  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>   
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>   
 <xref:System.Workflow.Activities.CodeCondition>   
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>