---
title: Использование действия InvokeMethod
ms.date: 03/30/2017
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
ms.openlocfilehash: f6e32d002a4a2002037a6d74c5a2c3e275568efb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`