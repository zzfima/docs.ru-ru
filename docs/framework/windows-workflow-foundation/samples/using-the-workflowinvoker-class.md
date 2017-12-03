---
title: "Использование класса WorkflowInvoker"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4265cd7fb0f894cc9cefd793727ebb513d3021c8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-workflowinvoker-class"></a>Использование класса WorkflowInvoker
В этом образце показано, как использовать класс <xref:System.Activities.WorkflowInvoker> для вызова действия, как если бы это был метод.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Использование класса <xref:System.Activities.WorkflowInvoker> - самый простой способ выполнения действия. Класс создан для запуска действия напрямую, как будто это вызов метода. Это простой, быстродействующий и удобный API-интерфейс для использования в сценариях, в которых исполнение действия не требует инфраструктуры контроля, которую предоставляют другие варианты размещения.  
  
 В образце используется настраиваемое действие, которое является производным от <xref:System.Activities.CodeActivity%601>< Int32\> с именем `Add` , добавляющий два <xref:System.Activities.InArgument%601>, `X` и `Y`и возвращает `Result` <xref:System.Activities.OutArgument%601>. (<xref:System.Activities.CodeActivity%601>\<T > является производным от <xref:System.Activities.Activity%601>< T\>, который имеет <xref:System.Activities.OutArgument%601> \<T > с именем `Result`.) Объект `Dictionary` \<строка, объект > используется для передачи аргументов действию, вызываемому посредством <xref:System.Activities.WorkflowInvoker>. Ключ словаря соответствует имени аргумента для вызываемого действия. Значение, связанное с определенным ключом, привязано к аргументу, идентифицируемому ключом.  
  
 В образце выполняется вызов метода <xref:System.Activities.WorkflowInvoker.Invoke%2A> и передача словаря, который содержит значения для аргументов `X` и `Y`. Класс <xref:System.Activities.WorkflowInvoker> привязывает эти значения к аргументам действия `Add`, выполняет действие и возвращает результат.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения Invoker.sln.  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавишу F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`