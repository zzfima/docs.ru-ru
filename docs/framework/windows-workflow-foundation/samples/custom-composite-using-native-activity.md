---
title: Пользовательское составное действие, использующее собственное действие
ms.date: 03/30/2017
ms.assetid: ef9e739c-8a8a-4d11-9e25-cb42c62e3c76
ms.openlocfilehash: 2b922ef721ab4d125f390e908eb8ea4d3b087035
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142801"
---
# <a name="custom-composite-using-native-activity"></a>Пользовательское составное действие, использующее собственное действие
В этом образце показано, как разработать действие <xref:System.Activities.NativeActivity>, которое планирует другие объекты <xref:System.Activities.Activity> для управления потоком выполнения рабочего процесса. В этом образце используются два общих потока управления, Sequence и While, для демонстрации того, как это сделать.

## <a name="sample-details"></a>Подробные сведения об образце
 Прежде всего об объекте `MySequence` следует отметить, что он является производным от <xref:System.Activities.NativeActivity>. <xref:System.Activities.NativeActivity> - объект <xref:System.Activities.Activity>, который предоставляет доступ ко всем возможностям среды выполнения рабочего процесса с помощью объекта <xref:System.Activities.NativeActivityContext>, передаваемого методу `Execute`.

 Действие `MySequence` предоставляет доступ к общедоступной коллекции объектов <xref:System.Activities.Activity>, которая заполняется разработчиком рабочего процесса. Перед выполнением рабочего процесса среда выполнения рабочего процесса вызывает метод <xref:System.Activities.Activity.CacheMetadata%2A> для каждого действия в рабочем процессе. В ходе этого процесса среда выполнения определяет связи типа «родитель-потомок» в целях управления областью определения данных и временем существования. В выполнении <xref:System.Activities.Activity.CacheMetadata%2A> метода <xref:System.ComponentModel.TypeDescriptor> по умолчанию `MySequence` используется класс экземпляра <xref:System.Activities.Activity> для <xref:System.Collections.IEnumerable> \< <xref:System.Activities.Activity> действия для `MySequence` добавления любой публичной собственности типа или> в качестве детей действия.

 Каждый раз, когда действие предоставляет доступ к общедоступной коллекции дочерних действий, возникает вероятность того, что эти дочерние действия будут приобретать одинаковое состояние. Рекомендуется, чтобы родительское действие, в данном случае `MySequence`, также предоставляло доступ к коллекции переменных, с помощью которых дочерние действия могли бы это осуществить. Как и действия <xref:System.Activities.Activity.CacheMetadata%2A> детей, метод <xref:System.Activities.Variable> добавляет <xref:System.Collections.IEnumerable> \< <xref:System.Activities.Variable> общедоступные свойства `MySequence` типа или> в качестве переменных, связанных с действием.

 Помимо общедоступных переменных, которыми управляют действия, дочерние по отношению к `MySequence`, действие `MySequence` должно также следить, где оно находится с точки зрения выполнения его дочерних действий. Для этого в нем используется закрытая переменная `currentIndex`. Эта переменная регистрируется как часть среды `MySequence` путем добавления вызова метода <xref:System.Activities.NativeActivityMetadata.AddImplementationVariable%2A> в метод `MySequence` действия <xref:System.Activities.Activity.CacheMetadata%2A>. Объекты, <xref:System.Activities.Activity> добавленные в коллекцию, `MySequence` `Activities` не могут получить доступ к переменным, добавленным таким образом.

 При выполнении средой выполнения действия `MySequence` она вызывает его метод <xref:System.Activities.NativeActivity.Execute%2A>, передавая ему контекст <xref:System.Activities.NativeActivityContext>. <xref:System.Activities.NativeActivityContext> выполняет для действия роль посредника к среде выполнения для разыменования аргументов и переменных, а также планирования работы других объектов <xref:System.Activities.Activity> или `ActivityDelegates`. `MySequence` использует метод `InternalExecute` для инкапсуляции логики планирования работы первого дочернего элемента и всех последующих дочерних элементов в единственном методе. Он начинает свое функционирование с разыменования `currentIndex`. Если это значение равно количеству в коллекции `Activities`, то последовательность завершается, действие выполняет возврат без планирования какой-либо работы и среда выполнения переводит его в состояние <xref:System.Activities.ActivityInstanceState.Closed>. Если `currentIndex` меньше, чем количество мероприятий, следующий ребенок `Activities` получается `MySequence` <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>из коллекции и звонки, <xref:System.Activities.CompletionCallback> проходя в `InternalExecute` ребенка, который будет запланирован и что указывает на метод. Наконец, значение `currentIndex` увеличивается и управление снова передается среде выполнения. Пока экземпляр действия `MySequence` имеет запланированный дочерний объект <xref:System.Activities.Activity>, среда выполнения считает, что оно находится в состоянии выполнения.

 После завершения дочернего действия выполняется <xref:System.Activities.CompletionCallback>. Выполнение цикла продолжается с его верхней части. Как и метод `Execute`, обратный вызов <xref:System.Activities.CompletionCallback> принимает контекст <xref:System.Activities.NativeActivityContext>, предоставляя средству реализации доступ к среде выполнения.

 `MyWhile`отличается `MySequence` от того, что <xref:System.Activities.Activity> он планирует один объект неоднократно, и\> `Condition` в том, что он использует <xref:System.Activities.Activity%601><bool имени, чтобы определить, является ли это планирование должно произойти. Как и действие `MySequence`, действие `MyWhile` использует метод `InternalExecute` для централизации своей логики планирования. Он `Condition` <xref:System.Activities.Activity> \> планирует<bool <xref:System.Activities.CompletionCallback%601> \<с bool `OnEvaluationCompleted`> имени . После завершения выполнения проверки `Condition` ее результат становится доступным через этот обратный вызов <xref:System.Activities.CompletionCallback> в строго типизированном параметре с именем `result`. Если значение равно `true`, действие `MyWhile` вызывает метод <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, передавая объект `Body` типа <xref:System.Activities.Activity> и метод `InternalExecute` в качестве обратного вызова <xref:System.Activities.CompletionCallback>. После завершения выполнения `Body` проверка `Condition` планируется еще раз в действии `InternalExecute`, что приводит к очередному запуску цикла. Если проверка `Condition` возвращает значение `false`, экземпляр действия `MyWhile` передает управление среде выполнения без планирования `Body`, а среда выполнения переводит действие в состояние <xref:System.Activities.ActivityInstanceState.Closed>.

#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Откройте пример решения Composite.sln в Visual Studio 2010.

2. Выполните сборку и запуск решения.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\CustomCompositeNativeActivity`
