---
title: "Использование действия InvokeMethod | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Использование действия InvokeMethod
Этот образец показывает, как использовать действие <xref:System.Activities.Statements.InvokeMethod%601> для вызова открытых методов в открытых классах.Действие <xref:System.Activities.Statements.InvokeMethod%601> позволяет рабочему процессу вызывать методы для объектов, передавать параметры, получать выходное значение, задавать типы универсальных методов и указывать, является ли метод синхронным или асинхронным.  
  
 Существует неуниверсальная версия действия <xref:System.Activities.Statements.InvokeMethod>, где возвращаемое значение устанавливается в значение свойства <xref:System.Activities.Statements.InvokeMethod.Result%2A>, а также универсальная версия действия <xref:System.Activities.Statements.InvokeMethod%601>, где результат возвращается через свойство <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> типа `TResult`.  
  
 В этом образце показано, как вызывать различные типы методов.В следующем списке указаны типы методов, которые демонстрируются в этом образце:  
  
-   Вызовите метод экземпляра без параметров.  
  
-   Вызовите метод экземпляра с двумя параметрами \(System.String и System.Int32\).  
  
-   Вызовите метод экземпляра с двумя параметрами \(System.String и System.Int32\) и массивом параметров типа System.String\[\].  
  
-   Вызовите метод экземпляра с двумя параметрами \(двумя числами System.Int32\) и результатом типа System.Int32.  
  
     Возвращаемое значение привязано к переменной и выдается на консоль с помощью действия <xref:System.Activities.Statements.WriteLine>.  
  
-   Вызовите статический метод с двумя параметрами \(System.String и System.Int32\).  
  
-   Вызовите метод экземпляра с одним универсальным параметром \(System.String\).  
  
-   Вызовите статический метод с двумя универсальными параметрами \(System.String и System.Int32\).  
  
-   Вызовите метод экземпляра, который имеет один параметр, передаваемый по ссылке \(System.String\).  
  
     Этот параметр, передаваемый по ссылке, привязан к переменной и выдается на консоль с помощью действия <xref:System.Activities.Statements.WriteLine>.  
  
-   Вызовите асинхронный метод экземпляра.  
  
## Использование этого образца  
  
1.  Откройте файл решения PInvokeMethodUsage.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL\+SHIFT\+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL\+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`  
  
## См. также