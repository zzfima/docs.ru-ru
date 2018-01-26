---
title: "Создание асинхронных действий в WF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 497e81ed-5eef-460c-ba55-fae73c05824f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1d06f825b96f66e35bdd30db272b99bb4e2e3e1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="creating-asynchronous-activities-in-wf"></a>Создание асинхронных действий в WF
Класс <xref:System.Activities.AsyncCodeActivity> предоставляет авторам действий базовый класс, обеспечивающий реализацию логики асинхронного выполнения в производных от него действиях. Это особенно полезно для пользовательских действий, которые должны выполнять работу асинхронно, не останавливая поток расписания рабочих процессов и не блокируя другие действия, которые могут выполняться параллельно. В данном разделе приводятся общие сведения о процессе создания пользовательских асинхронных действий с использованием <xref:System.Activities.AsyncCodeActivity>.  
  
## <a name="using-asynccodeactivity"></a>Использование AsyncCodeActivity  
 <xref:System.Activities?displayProperty=nameWithType> предоставляет авторам пользовательских действий различные базовые классы для различных требований, предъявляемых при создании действий. Каждый класс имеет определенную семантику и предоставляет автору рабочего процесса (и среде выполнения действия) соответствующий контракт. Действие, основанное на <xref:System.Activities.AsyncCodeActivity> - это действие, выполняющее работу асинхронно относительно потока планировщика, а логика выполнения такого действия выражена в управляемом коде. Вследствие асинхронности <xref:System.Activities.AsyncCodeActivity> может вызывать точку бездействия во время выполнения. В силу изменчивого характера асинхронной работы <xref:System.Activities.AsyncCodeActivity> всегда создает несохраняемый блок на время выполнения действия. Это позволяет защитить среду выполнения рабочего процесса от сохранения экземпляра рабочего процесса во время выполнения асинхронной работы, а также предотвратить выгрузку экземпляра рабочего процесса во время выполнения асинхронного кода.  
  
### <a name="asynccodeactivity-methods"></a>Методы AsyncCodeActivity  
 Действия, производные от <xref:System.Activities.AsyncCodeActivity>, могут создавать логику асинхронного выполнения перепрограммированием метода <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> и методов интерфейса <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>. При вызове средой выполнения эти методы передаются <xref:System.Activities.AsyncCodeActivityContext>. <xref:System.Activities.AsyncCodeActivityContext>позволяет автору действия обеспечить общее состояние между <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> /  <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> в контексте <xref:System.Activities.AsyncCodeActivityContext.UserState%2A> свойство. В следующем примере действие `GenerateRandom` асинхронно формирует случайное число.  
  
 [!code-csharp[CFX_ActivityExample#8](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#8)]  
  
 Действие, описанное в предыдущем примере, является производным от <xref:System.Activities.AsyncCodeActivity%601>, имеет аргумент более высокого уровня `OutArgument<int>` с именем `Result`. Значение, возвращаемое методом `GetRandom`, извлекается и возвращается путем переопределения <xref:System.Activities.AsyncCodeActivity%601.EndExecute%2A>, после чего это значение задается как значение `Result`. Асинхронные действия, не возвращающие результат, должны наследоваться от <xref:System.Activities.AsyncCodeActivity>. В следующем примере, определяется действие `DisplayRandom`, являющееся производным от <xref:System.Activities.AsyncCodeActivity>. Это действие подобно действию `GetRandom`, однако вместо возвращения результата оно отображает сообщение на экране консоли.  
  
 [!code-csharp[CFX_ActivityExample#11](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#11)]  
  
 Обратите внимание, что из-за отсутствия возвращаемого значения действие `DisplayRandom` использует класс <xref:System.Action> вместо <xref:System.Func%602> для вызова своего делегата, а делегат не возвращает значение.  
  
 <xref:System.Activities.AsyncCodeActivity> также предоставляет переопределение <xref:System.Activities.AsyncCodeActivity.Cancel%2A>. В то время как <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> и <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> являются обязательными переопределениями, <xref:System.Activities.AsyncCodeActivity.Cancel%2A> является необязательным и может быть переопределен, чтобы действие могло очистить необработанное асинхронное состояние в случае своей отмены или прерывания. Если очистка возможна и `AsyncCodeActivity.ExecutingActivityInstance.IsCancellationRequested` имеет значение `true`, то действие должно вызвать <xref:System.Activities.AsyncCodeActivityContext.MarkCanceled%2A>. Любые исключения, возникшие при выполнении данного метода, являются неустранимыми для экземпляра рабочего процесса.  
  
 [!code-csharp[CFX_ActivityExample#10](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#10)]  
  
### <a name="invoking-asynchronous-methods-on-a-class"></a>Вызов асинхронных методов в классе  
 Многие классы в [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] обеспечивают асинхронное функционирование. Такой функциональностью можно асинхронно воспользоваться с помощью действий, основанных на <xref:System.Activities.AsyncCodeActivity>. В следующем примере из [использование AsyncOperationContext в действии](../../../docs/framework/windows-workflow-foundation/samples/using-asyncoperationcontext-in-an-activity-sample.md), создать действие, асинхронно создает файл с помощью <xref:System.IO.FileStream> класса.  
  
 [!code-csharp[CFX_ActivityExample#12](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#12)]  
  
### <a name="sharing-state-between-the-beginexecute-and-endexecute-methods"></a>Общее состояние между методами BeginExecute и EndExecute  
 В предыдущем примере доступ к объекту <xref:System.IO.FileStream>, созданному в <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>, был выполнен в <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>. Это обусловлено тем, что переменная `file` была передана в свойстве <xref:System.Activities.AsyncCodeActivityContext.UserState%2A?displayProperty=nameWithType> методом <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>. Это правильный метод для совместного использования состояния между <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> и <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>. Использовать переменную-член в производном классе (в данном случае `FileWriter`) для совместного использования состояния между <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> и <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> неверно, так как на объект действия могут ссылаться несколько экземпляров действия. Попытка использовать переменную-член для совместного использования состояния может привести к перезаписи значений из одного <xref:System.Activities.ActivityInstance> или потреблению значений из другого <xref:System.Activities.ActivityInstance>.  
  
### <a name="accessing-argument-values"></a>Доступ к значениям аргументов  
 Среда <xref:System.Activities.AsyncCodeActivity> состоит из аргументов, определенных для действия. Эти аргументы можно обращаться из <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> / <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> переопределяет с помощью <xref:System.Activities.AsyncCodeActivityContext> параметра. Получить доступ к аргументам в делегате невозможно, но значения аргументов или любые другие требуемые данные можно передать в делегат через его параметры. В следующем примере определяется действие создания случайного числа, которое получает инклюзивную верхнюю границу создаваемого числа в аргументе `Max`. При вызове делегата значение аргумента передается в асинхронный код.  
  
 [!code-csharp[CFX_ActivityExample#9](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#9)]  
  
### <a name="scheduling-actions-or-child-activities-using-asynccodeactivity"></a>Планирование действий или дочерних действий с помощью AsyncCodeActivity  
 Производные от <xref:System.Activities.AsyncCodeActivity> настраиваемых действий предоставляют метод для асинхронного выполнения работы в отношении к потоку рабочего процесса, но не предоставляют возможности планирования действий или дочерних действий. Однако асинхронное поведение можно встроить в планирование дочерних действий посредством композиции. Асинхронное действие можно создать, а затем сочетать с действием, производным от <xref:System.Activities.Activity> или <xref:System.Activities.NativeActivity>, предоставив асинхронное поведение и планирование действий или дочерних действий. Например, можно создать действие, производное от <xref:System.Activities.Activity>, у которого в качестве его реализации будет <xref:System.Activities.Statements.Sequence>, содержащий асинхронное действие, а также другие действия, реализующие логику этого действия. Дополнительные примеры составления действий с помощью <xref:System.Activities.Activity> и <xref:System.Activities.NativeActivity>, в разделе [как: создается действие](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md), [параметры разработки действий](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)и [составного](../../../docs/framework/windows-workflow-foundation/samples/composite.md) образцы действий.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Action>  
 <xref:System.Func%602>  
 [Использование AsyncOperationContext в действии](../../../docs/framework/windows-workflow-foundation/samples/using-asyncoperationcontext-in-an-activity-sample.md)
