---
title: "Использование действия InvokeMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5d3f6734f9d6a3b0e2279b2bb6cca71141c8f5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-invokemethod-activity"></a>Использование действия InvokeMethod
В этом примере демонстрируется использование <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) действию для вызова открытых методов открытых классов. <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) Действия позволяет рабочему процессу вызывать методы для объектов, передавать параметры, получения возвращаемого значения, задавать типы универсальных методов и указать, является ли метод синхронным или асинхронные. 
  
Неуниверсальном версии <xref:System.Activities.Statements.InvokeMethod> действия, в которых возвращаемое значение равно <xref:System.Activities.Statements.InvokeMethod.Result%2A> свойство и универсальная версия <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) действия которых возвращает возвращаемое значение через <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx) свойство типа `TResult`. 
  
 В этом образце показано, как вызывать различные типы методов. В следующем списке указаны типы методов, которые демонстрируются в этом образце:  
  
-   Вызовите метод экземпляра без параметров.  
  
-   Вызовите метод экземпляра с двумя параметрами (System.String и System.Int32).  
  
-   Вызовите метод экземпляра с двумя параметрами (System.String и System.Int32) и массивом параметров типа System.String[].  
  
-   Вызовите метод экземпляра с двумя параметрами (двумя числами System.Int32) и результатом типа System.Int32.  
  
     Возвращаемое значение привязано к переменной и выдается на консоль с помощью действия <xref:System.Activities.Statements.WriteLine>.  
  
-   Вызовите статический метод с двумя параметрами (System.String и System.Int32).  
  
-   Вызовите метод экземпляра с одним универсальным параметром (System.String).  
  
-   Вызовите статический метод с двумя универсальными параметрами (System.String и System.Int32).  
  
-   Вызовите метод экземпляра, который имеет один параметр, передаваемый по ссылке (System.String).  
  
     Этот параметр, передаваемый по ссылке, привязан к переменной и выдается на консоль с помощью действия <xref:System.Activities.Statements.WriteLine>.  
  
-   Вызовите асинхронный метод экземпляра.  
  
## <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл решения PInvokeMethodUsage.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`