---
title: "Динамические аргументы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 122ad479-d306-4602-a943-5aefe711329d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96e03aac921cfeb69811a0c51ad2151b7e70cd93
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="dynamic-arguments"></a>Динамические аргументы
В этом образце показано, как реализовать действие, аргументы которого определяются объектом-получателем, а не автором действия. Это достигается переопределением способа построения метаданных действия в среде выполнения.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Перед выполнением среда выполнения строит описание действия путем анализа открытых членов типа действия и автоматического объявления аргументов, переменных, дочерних действий и делегатов действия как частей метаданных действия. Это делается, чтобы обеспечить правильное построение рабочего процесса, а также управление связями времени выполнения и правилами времени существования с помощью реализации. Обычно автор действия определяет аргументы действия, задавая открытые члены типа действия, производные от <xref:System.Activities.Argument>. Для каждого открытого члена, производного от <xref:System.Activities.Argument>, среда выполнения создает <xref:System.Activities.RuntimeArgument> и привязывает его к предоставленному пользователем набору аргументов этого члена. Но в некоторых случаях получатель действия предоставляет конфигурацию, которая определяет набор аргументов. Автор действия переопределяет <xref:System.Activities.Activity.CacheMetadata%2A>, чтобы настроить способ построения метаданных действия, в том числе набор аргументов, связанных с действием.  
  
 В этом образце показано, как динамически построить список аргументов для действия, вызывающего метод. Получатель действия указывает тип и имя метода, который нужно вызвать, наряду с коллекцией передаваемых этому методу аргументов.  
  
> [!NOTE]
>  Цель этого образца - продемонстрировать переопределение метода <xref:System.Activities.CodeActivity.CacheMetadata%2A> и использование класса <xref:System.Activities.RuntimeArgument>. Существует несколько проблем, связанных с разновидностями методов, которые может вызывать действие. Например, оно не работает с универсальными шаблонами или массивами параметров. Действие <xref:System.Activities.Statements.InvokeMethod>, поставляемое с .NET Framework, обрабатывает эти и другие случаи.  
  
 Действие `MethodInvoke` переопределяет метод <xref:System.Activities.CodeActivity.CacheMetadata%2A> и начинает с создания класса <xref:System.Activities.RuntimeArgument> для обработки любого результата вызова метода. Оно привязывает этот аргумент <xref:System.Activities.RuntimeArgument> к открыто задаваемому классу <xref:System.Activities.OutArgument> с именем `Result`. Если `MethodInvoke.Result` имеет значение `null`, среда выполнения автоматически заполняет его значением <xref:System.Activities.OutArgument>, которому присвоено выражение по умолчанию для данного типа. Поэтому автору действия никогда не требуется проверять, имеет ли свойство аргумента значение `null`.  
  
 Затем переопределение метода <xref:System.Activities.CodeActivity.CacheMetadata%2A> определяет `MethodInfo`, используемый для вызова, из предоставляемых пользователем значений `MethodName` и `TargetType`. Метод `DetermineMethodInfo` принимает параметр <xref:System.Activities.CodeActivityMetadata>, переданный переопределению <xref:System.Activities.CodeActivity.CacheMetadata%2A>, чтобы о любых ошибках конфигурации сообщалось как об ошибках проверки. Это выполняется с помощью вызова метода `metadata.AddValidationError`.  
  
 После того, как задано значение `MethodInfo`, образец выполняет перебор параметров `MethodInfo`. Для каждого параметра он создает объект <xref:System.Activities.RuntimeArgument> и привязывает его к соответствующему аргументу в предоставленной пользователем коллекции из свойства `Parameters`. Наконец, коллекция объектов <xref:System.Activities.RuntimeArgument> связывается с действием посредством вызова `metadata.SetArgumentsCollection`.  
  
 Обратите внимание, что разрешение аргументов может быть выполнено с использованием класса <xref:System.Activities.RuntimeArgument>, как в случае с `resultArgument`, или по предоставленному пользователем аргументу, как в случае коллекции `Parameters`.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл DynamicArguments.sln.  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\DynamicArguments`