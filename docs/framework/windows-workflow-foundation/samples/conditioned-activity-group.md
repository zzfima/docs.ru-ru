---
title: Группа действий с условиями
ms.date: 03/30/2017
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
ms.openlocfilehash: 144a6c76ea6314c553e201fe4e2364890d869f34
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418173"
---
# <a name="conditioned-activity-group"></a>Группа действий с условиями
В данном образце демонстрируется приложение бронирования путешествия. В объекте класса <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) содержатся два действия кода: действия "Car" и "Airline". В конструкторе `SimpleCAGWorkflow` объект "ArrayList" с именем "travelNeedType" заполняется типами требуемых бронирования путешествия. При комментировании одной или обеих этих инструкций `travelNeeds.Add` поведение CAG соответствующим образом изменяется. В обоих действиях "Car" и "Airline" их условие <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>, заполнено объектом класса <xref:System.Workflow.Activities.CodeCondition>. Действие Car выполняется, только если в коллекции `travelNeeds` есть запись `TravelNeeds.Car`; действие Airline выполняется только в том случае, если в коллекции `travelNeeds` содержится запись `TravelNeeds.Airline`.  
  
 При выполнении каждого из действий из коллекции удаляется соответствующая запись. Условие свойства <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> по умолчанию задает выход из CAG в том случае, если дочерние действия в настоящий момент не выполняются или готовы для выполнения (в зависимости от их условий <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>). В данном образце это означает, что выход из CAG выполняется, если коллекция `travelNeeds` пуста.  
  
### <a name="to-build-the-sample"></a>Сборка образца  
  
1.  Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.  
  
3.  Запустите решение без отладки, нажав сочетание клавиш CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Выполнение образца  
  
-   В окне командной строки пакета SDK запустите файл с расширением EXE в папке «SimpleCAG\bin\debug» (или в папке «SimpleCAG\bin» для образца в Visual Basic), вложенной в главную папку образца.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец находится в следующем каталоге:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
