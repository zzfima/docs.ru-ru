---
title: "Параллельное действие ForEach с ограничением | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Параллельное действие ForEach с ограничением
Действие `ThrottleParallelForEach` аналогично действию <xref:System.Activities.Statements.ParallelForEach>, за одним исключением, которое позволяет настроить коэффициент распараллеливания для ограничения количества одновременно выполняющихся ветвей.Действие `ThrottleParallelForEach` является производным от действия <xref:System.Activities.NativeActivity>, поскольку оно должно планировать другие действия \(дочерние действия\), что можно сделать только через класс <xref:System.Activities.NativeActivityContext>.  
  
## Проекты  
  
||||  
|-|-|-|  
|**Имя проекта**|**Описание**|**Основные файлы**|  
|ThrottledParallelForEach|Содержит действие `ThrottledParallelForEach` и его конструктор.|ThrottledParallelForEach.cs<br /><br /> Определение действия `ThrottledParallelForEach`.|  
|CodeTestClient|Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса с использованием `ThrottledParallelForEach` при помощи императивного кода.|Program.cs<br /><br /> Определяет и выполняет экземпляр образца рабочего процесса.|  
  
#### Использование этого образца  
  
1.  Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения ThrottledParallelForEach.sln.  
  
2.  Для построения решения нажмите CTRL\+SHIFT\+B.  
  
3.  Чтобы запустить решение, нажмите клавишу F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`  
  
## См. также