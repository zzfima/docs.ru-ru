---
title: "Выполнение рабочего процесса в императивном коде TransactionScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd0e8686-c1d0-4400-a541-da94ed03afc7
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 26117e7b089e85e8953912745ebc74baad8bfa29
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="execute-a-workflow-in-an-imperative-transactionscope"></a>Выполнение рабочего процесса в императивном коде TransactionScope
Этот образец демонстрирует, как выполнить рабочий процесс с использованием <xref:System.Activities.WorkflowInvoker> в рамках транзакции <xref:System.Transactions.Transaction> из императивного кода C#.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В императивном коде C# для инкапсуляции набора работ, выполняемых в той же транзакции, используется класс <xref:System.Transactions.TransactionScope>. <xref:System.Transactions.TransactionScope> создает внешнюю транзакцию и инициализирует свойство <xref:System.Transactions.Transaction.Current%2A>, к которому впоследствии может обращаться любая работа, выполняемая в этом потоке.  
  
 Чтобы получить эквивалентное поведение в рабочем процессе, до выполнения каждого действия в среде выполнения должна быть выполнена дополнительная инициализация <xref:System.Transactions.Transaction.Current%2A>, поскольку рабочий процесс не сохраняет сходство потоков между действиями. С учетом описанных действий в среде выполнения, результирующее поведение будет таким же, как если бы рабочий процесс был выполнен с помощью <xref:System.Activities.WorkflowInvoker> внутри <xref:System.Transactions.TransactionScope>, все действия гарантированно будут выполняться в контексте внешней транзакции, созданной объектом <xref:System.Transactions.TransactionScope>.  
  
 Рабочий процесс может иметь лишь одну внешнюю транзакцию для каждого экземпляра рабочего процесса; использование вложенных транзакций не разрешается. Даже если рабочий процесс содержит действие <xref:System.Activities.Statements.TransactionScope>, это действие не создает новую внутреннюю транзакцию. Вместо этого повторно используется внешняя транзакция, созданная вне рабочего процесса.  
  
 Образец инициализирует новый объект <xref:System.Transactions.TransactionScope>, выводит на экран консоли идентификатор транзакции и запускает рабочий процесс с помощью <xref:System.Activities.WorkflowInvoker>. Рабочий процесс повторно выводит на экран консоли идентификатор транзакции, сообщая тем самым, что это та же самая транзакция, затем запускает <xref:System.Activities.Statements.TransactionScope> и завершает работу. Вызов <xref:System.Activities.WorkflowInvoker.Invoke%2A> в <xref:System.Activities.WorkflowInvoker> является синхронным, поэтому исходный поток блокируется вплоть до завершения рабочего процесса. Как только рабочий процесс будет завершен, транзакция завершается и происходит высвобождение ресурсов.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл решения ImperativeTransactionSample.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавишу F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\ImperativeTransaction`  
  
## <a name="see-also"></a>См. также
