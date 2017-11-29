---
title: "Исключения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 065205cc-52dd-4f30-9578-b17d8d113136
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d1484f3b0af3ee09f1cb18d3d90f81fb0a2044a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="exceptions"></a>Исключения
Рабочие процессы могут использовать действие <xref:System.Activities.Statements.TryCatch> для обработки исключений, возникающих в ходе выполнения рабочего процесса. Эти исключения обрабатываются либо вызываются повторно при помощи действия <xref:System.Activities.Statements.Rethrow>. Действия в разделе <xref:System.Activities.Statements.TryCatch.Finally%2A> выполняются при завершении либо раздела <xref:System.Activities.Statements.TryCatch.Try%2A>, либо раздела <xref:System.Activities.Statements.TryCatch.Catches%2A>. Рабочие процессы, размещаемые <xref:System.Activities.WorkflowApplication> экземпляра можно также использовать <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> обработчик событий для обработки исключений, которые не обрабатываются <xref:System.Activities.Statements.TryCatch> действия.  
  
## <a name="causes-of-exceptions"></a>Причины исключений  
 в рабочем процессе исключения могут создаваться следующим образом:  
  
-   Время ожидания транзакций в <xref:System.Activities.Statements.TransactionScope>.  
  
-   Явное исключение, вызываемое рабочим процессом с помощью действия <xref:System.Activities.Statements.Throw>.  
  
-   Исключение [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], возникшее из действия.  
  
-   Исключение, возникающее из внешнего кода, например из библиотек, компонентов или служб, используемых в рабочем процессе.  
  
## <a name="handling-exceptions"></a>Обработка исключений  
 Если исключение возникает из действия и не обрабатывается, поведение по умолчанию состоит в завершении экземпляра рабочего процесса. Если присутствует пользовательский обработчик <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, он может переопределить поведение по умолчанию. Обработчик предоставляет автору узла рабочего процесса возможность выполнить соответствующую обработку, например пользовательское протоколирование, прерывание, отмену или прекращение рабочего процесса.  Если рабочий процесс создает необрабатываемое исключение, вызывается обработчик <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>. Метод <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> может вернуть три действия, определяющие окончательный результат рабочего процесса.  
  
-   **Отмена** -отменяется экземпляр рабочего процесса, являющийся результатом выполнения ветви. Вы можете моделировать поведение отмены (например, с помощью действия CancellationScope). После завершения процесса отмены вызывается обработчик завершения (Completed). Отмененный рабочий процесс находится в состоянии Cancelled (Отменено).  
  
-   **Завершение** -завершенный экземпляр рабочего процесса нельзя возобновить или перезапустить.  Формируется событие Completed (Завершено), в котором вы можете указать исключение, являющееся причиной. После завершения процесса вызывается обработчик завершения (Terminated). Завершенный рабочий процесс находится в состоянии ошибки (Faulted).  
  
-   **Прервать** -прерванные экземпляры рабочего процесса может быть возобновлена только в том случае, если он настроен как постоянную.  Без сохраняемости рабочий процесс нельзя возобновить.  На этой стадии рабочий процесс прерывается, любые результаты работы (в памяти) с момента последнего сохранения будут потеряны. Для прерванного рабочего процесса вызывается обработчик прерывания (Aborted) с использованием исключения как основания, когда процесс прерывания завершается. Однако в отличие от обработчиков Cancelled и Terminated обработчик Completed не вызывается. Прерванный рабочий процесс находится в состоянии Aborted (Прервано).  
  
 В следующем примере кода вызывается рабочий процесс, в котором создается исключение. Исключение не обрабатывается рабочим процессом, и вызывается обработчик <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>. Чтобы получить сведения об исключении, проверяются аргументы <xref:System.Activities.WorkflowApplicationUnhandledExceptionEventArgs>, и рабочий процесс завершается.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#1)]  
  
### <a name="handling-exceptions-with-the-trycatch-activity"></a>Обработка исключений при помощи действия TryCatch  
 Обработка исключений внутри рабочего процесса выполняется при помощи действия <xref:System.Activities.Statements.TryCatch>. Действие <xref:System.Activities.Statements.TryCatch> имеет коллекцию <xref:System.Activities.Statements.TryCatch.Catches%2A> действий <xref:System.Activities.Statements.Catch>, из которых каждое связано с определенным типом <xref:System.Exception>. Если исключение, возникшее из действия, содержащегося в разделе <xref:System.Activities.Statements.TryCatch.Try%2A> действия <xref:System.Activities.Statements.TryCatch>, совпадает с исключением действия <xref:System.Activities.Statements.Catch%601> в коллекции <xref:System.Activities.Statements.TryCatch.Catches%2A>, то исключение будет обработано. Если исключение возникает повторно явным образом или если возникает новое исключение, то это исключение передается родительскому действию. В следующем примере кода показано действие <xref:System.Activities.Statements.TryCatch>, которое обрабатывает исключение <xref:System.ApplicationException>, вызванное в разделе <xref:System.Activities.Statements.TryCatch.Try%2A> в результате действия <xref:System.Activities.Statements.Throw>. Сообщение исключения записывается в консоль действием <xref:System.Activities.Statements.Catch%601>, после чего сообщение выводится на консоль в разделе <xref:System.Activities.Statements.TryCatch.Finally%2A>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#33](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#33)]  
  
 Действия в разделе <xref:System.Activities.Statements.TryCatch.Finally%2A> выполняются при успешном завершении либо раздела <xref:System.Activities.Statements.TryCatch.Try%2A>, либо раздела <xref:System.Activities.Statements.TryCatch.Catches%2A>. Раздел <xref:System.Activities.Statements.TryCatch.Try%2A> успешно завершается при отсутствии исключений из него, а раздел <xref:System.Activities.Statements.TryCatch.Catches%2A> успешно завершается, если не создаются собственные исключения и не вызываются из него повторно. При возникновении исключения в разделе <xref:System.Activities.Statements.TryCatch.Try%2A> блока <xref:System.Activities.Statements.TryCatch>, которое либо не обрабатывается обработчиком <xref:System.Activities.Statements.Catch%601> в разделе <xref:System.Activities.Statements.TryCatch.Catches%2A>, либо повторно вызывается из <xref:System.Activities.Statements.TryCatch.Catches%2A>, действия из раздела <xref:System.Activities.Statements.TryCatch.Finally%2A> не будут выполнены, если только не возникнет одна из следующих ситуаций.  
  
-   Исключение перехватывается действием более высокого уровня <xref:System.Activities.Statements.TryCatch> в рабочем процессе независимо от того, вызывается ли повторно с более высокого уровня <xref:System.Activities.Statements.TryCatch>.  
  
-   Исключение, не обработанное более высоким уровнем <xref:System.Activities.Statements.TryCatch>, покидает корневой элемент рабочего процесса, и рабочий процесс используется для отмены вместо завершения или прерывания транзакции. Рабочие процессы, размещенные с помощью <xref:System.Activities.WorkflowApplication>, могут настроить это путем обработки <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, после чего будет возвращено значение <xref:System.Activities.UnhandledExceptionAction.Cancel>. Пример обработки <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> приведен ранее в этом разделе. Службы Workflow Services можно настроить, используя <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> и задавая <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction.Cancel>. Пример настройки <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, в разделе [расширяемость узла службы рабочего процесса](../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="exception-handling-versus-compensation"></a>Обработка исключений и компенсация  
 Отличие между обработкой исключений и компенсацией заключается в том, что обработка исключений имеет место во время выполнения действия. Компенсация имеет место после успешного завершения действия. Обработка исключений предоставляет возможность выполнить очистку после того, как действие вызывает исключение, в то время как компенсация обеспечивает механизм, с помощью которого можно отменить успешно завершенную работу ранее завершенного действия. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Компенсации](../../../docs/framework/windows-workflow-foundation/compensation.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Activities.Statements.TryCatch>  
 <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>  
 <xref:System.Activities.Statements.CompensableActivity>
