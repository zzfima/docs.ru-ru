---
title: "Пользовательское составное действие, использующее собственное действие | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef9e739c-8a8a-4d11-9e25-cb42c62e3c76
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Пользовательское составное действие, использующее собственное действие
В этом образце показано, как разработать действие <xref:System.Activities.NativeActivity>, которое планирует другие объекты <xref:System.Activities.Activity> для управления потоком выполнения рабочего процесса.В этом образце используются два общих потока управления, Sequence и While, для демонстрации того, как это сделать.  
  
## Подробные сведения об образце  
 Начиная с `MySequence`, прежде всего следует отметить, что он является производным от <xref:System.Activities.NativeActivity>.<xref:System.Activities.NativeActivity> — объект <xref:System.Activities.Activity>, который предоставляет доступ ко всем возможностям среды выполнения рабочего процесса с помощью объекта <xref:System.Activities.NativeActivityContext>, передаваемого методу `Execute`.  
  
 Действие `MySequence` предоставляет доступ к общедоступной коллекции объектов <xref:System.Activities.Activity>, которая заполняется разработчиком рабочего процесса.Перед выполнением рабочего процесса среда выполнения рабочего процесса вызывает метод <xref:System.Activities.Activity.CacheMetadata%2A> для каждого действия в рабочем процессе.В ходе этого процесса среда выполнения определяет связи типа «родитель\-потомок» в целях управления областью определения данных и временем существования.В реализации метода <xref:System.Activities.Activity.CacheMetadata%2A> по умолчанию используется класс экземпляра <xref:System.ComponentModel.TypeDescriptor> для действия `MySequence` в целях добавления любого общедоступного свойства типа <xref:System.Activities.Activity> или <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Activity>\> в качестве дочернего для действия `MySequence`.  
  
 Каждый раз, когда действие предоставляет доступ к общедоступной коллекции дочерних действий, возникает вероятность того, что эти дочерние действия будут приобретать одинаковое состояние.Рекомендуется, чтобы родительское действие, в данном случае `MySequence`, также предоставляло доступ к коллекции переменных, с помощью которых дочерние действия могли бы это осуществить.По аналогии с дочерними действиями метод <xref:System.Activities.Activity.CacheMetadata%2A> добавляет общедоступные свойства типа <xref:System.Activities.Variable> или <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Variable>\> в качестве переменных, которые связаны с действием `MySequence`.  
  
 Помимо общедоступных переменных, которыми управляют действия, дочерние по отношению к `MySequence`, действие `MySequence` должно также следить, где оно находится с точки зрения выполнения его дочерних действий.Для этого в нем используется закрытая переменная `currentIndex`.Эта переменная регистрируется как часть среды `MySequence` путем добавления вызова метода <xref:System.Activities.NativeActivityMetadata.AddImplementationVariable%2A> в метод <xref:System.Activities.Activity.CacheMetadata%2A> действия `MySequence`.Объекты <xref:System.Activities.Activity>, добавленные в коллекцию `MySequence` `Activities`, не могут получить доступ к переменным, добавленным таким образом.  
  
 При выполнении средой выполнения действия `MySequence` она вызывает его метод <xref:System.Activities.NativeActivity.Execute%2A>, передавая ему контекст <xref:System.Activities.NativeActivityContext>.<xref:System.Activities.NativeActivityContext> выполняет для действия роль посредника к среде выполнения для разыменования аргументов и переменных, а также планирования работы других объектов <xref:System.Activities.Activity> или `ActivityDelegates`.`MySequence` использует метод `InternalExecute` для инкапсуляции логики планирования работы первого дочернего элемента и всех последующих дочерних элементов в единственном методе.Он начинает свое функционирование с разыменования `currentIndex`.Если это значение равно количеству в коллекции `Activities`, то последовательность завершается, действие выполняет возврат без планирования какой\-либо работы и среда выполнения переводит его в состояние <xref:System.Activities.ActivityInstanceState>.Если значение `currentIndex` меньше количества действий, происходит получение следующего дочернего элемента из коллекции `Activities`, а действие `MySequence` вызывает метод <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A> с передачей ему подлежащего планированию дочернего элемента и <xref:System.Activities.CompletionCallback>, который указывает на метод `InternalExecute`.Наконец, значение `currentIndex` увеличивается и управление снова передается среде выполнения.Пока экземпляр действия `MySequence` имеет запланированный дочерний объект <xref:System.Activities.Activity>, среда выполнения считает, что оно находится в состоянии выполнения.  
  
 После завершения дочернего действия выполняется <xref:System.Activities.CompletionCallback>.Выполнение цикла продолжается с его верхней части.Как и метод `Execute`, обратный вызов <xref:System.Activities.CompletionCallback> принимает контекст <xref:System.Activities.NativeActivityContext>, предоставляя средству реализации доступ к среде выполнения.  
  
 Действие `MyWhile` отличается от действия `MySequence` тем, что оно неоднократно планирует один объект <xref:System.Activities.Activity> и в нем используется переменная типа <xref:System.Activities.Activity%601>\<bool\> с именем `Condition` для определения того, должно ли быть выполнено это планирование.Как и действие `MySequence`, действие `MyWhile` использует метод `InternalExecute` для централизации своей логики планирования.Оно планирует значение `Condition` типа <xref:System.Activities.Activity>\<bool\> с помощью значения типа <xref:System.Activities.CompletionCallback%601>\<bool\> с именем `OnEvaluationCompleted`.После завершения выполнения проверки `Condition` ее результат становится доступным через этот обратный вызов <xref:System.Activities.CompletionCallback> в строго типизированном параметре с именем `result`.Если значение равно `true`, действие `MyWhile` вызывает метод <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, передавая объект `Body`<xref:System.Activities.Activity> и метод `InternalExecute` в качестве обратного вызова <xref:System.Activities.CompletionCallback>.После завершения выполнения `Body` проверка `Condition` планируется еще раз в действии `InternalExecute`, что приводит к очередному запуску цикла.Если проверка `Condition` возвращает значение `false`, экземпляр действия `MyWhile` передает управление среде выполнения без планирования `Body`, а среда выполнения переводит действие в состояние <xref:System.Activities.ActivityInstanceState>.  
  
#### Настройка, построение и выполнение образца  
  
1.  Откройте образец решения Composite.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Постройте и запустите решение.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\CustomCompositeNativeActivity`  
  
## См. также