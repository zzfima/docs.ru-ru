---
title: Архитектура рабочих процессов Windows
ms.date: 03/30/2017
ms.assetid: 1d4c6495-d64a-46d0-896a-3a01fac90aa9
ms.openlocfilehash: d341ebd354d5324c5ad71436837cb85737f46c08
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64605897"
---
# <a name="windows-workflow-architecture"></a>Архитектура рабочих процессов Windows
Windows Workflow Foundation (WF) повышает уровень абстракции для разработки интерактивных длительных приложений. Блоки обработки инкапсулируются в виде действий. Действия работают в среде, которая обеспечивает средства для управления потоком, обработки исключений, распространения ошибок, сохранения данных состояния, загрузки и выгрузки текущих рабочих процессов из памяти, отслеживания и управления потоком транзакций.  
  
## <a name="activity-architecture"></a>Архитектура действий  
 Действия разрабатываются в виде типов среды CLR, которые являются производными либо от <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> или <xref:System.Activities.NativeActivity>, либо от их вариантов, возвращающих значение, <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601> или <xref:System.Activities.NativeActivity%601>. Разработка действий, которые являются производными от действия <xref:System.Activities.Activity>, позволяет пользователю собирать существующие действия для быстрого создания блоков обработки, работающих в среде рабочих процессов. С другой стороны, действие <xref:System.Activities.CodeActivity> позволяет создавать логику выполнения в управляемом коде с использованием <xref:System.Activities.CodeActivityContext> в основном для доступа к аргументам действий. <xref:System.Activities.AsyncCodeActivity> аналогично <xref:System.Activities.CodeActivity>, за исключением того, что его можно использовать для реализации асинхронных задач. Разработка действий, которые являются производными от действия <xref:System.Activities.NativeActivity>, позволяет пользователям получать доступ к среде выполнения посредством <xref:System.Activities.NativeActivityContext> для таких функций, как планирование дочерних объектов, создание закладок, вызов асинхронной работы, регистрации транзакций и других операций.  
  
 Создание действий, которые происходят от действия <xref:System.Activities.Activity>, является декларативным, при этом эти действия не могут быть созданы на языке XAML. В следующем примере действие `Prompt` создается при помощи других действий для тела выполнения.  
  
```xml  
<Activity x:Class='Prompt'  
  xmlns:x='http://schemas.microsoft.com/winfx/2006/xaml'  
    xmlns:z='http://schemas.microsoft.com/netfx/2008/xaml/schema'  
xmlns:my='clr-namespace:XAMLActivityDefinition;assembly=XAMLActivityDefinition'  
xmlns:s="clr-namespace:System;assembly=mscorlib"  
xmlns="http://schemas.microsoft.com/2009/workflow">  
<z:SchemaType.Members>  
    <z:SchemaType.SchemaProperty Name='Text' Type=' InArgument(s:String)' />  
  <z:SchemaType.SchemaProperty Name='Response' Type='OutArgument(s:String)' />  
</z:SchemaType.Members>  
  <Sequence>  
    <my:WriteLine Text='[Text]' />  
    <my:ReadLine BookmarkName='r1' Result='[Response]' />  
  </Sequence>  
</Activity>  
```  
  
## <a name="activity-context"></a>Контекст действия  
 <xref:System.Activities.ActivityContext> представляет собой интерфейс автора действий со средой выполнения рабочих процессов и обеспечивает доступ ко многим функциям среды выполнения. В следующем примере определяется действие, которое использует контекст выполнения для создания закладки (механизм, позволяющий действию зарегистрировать точку продолжения в ходе выполнения, которое может быть возобновлено при передаче узлом данных в действие).  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
## <a name="activity-life-cycle"></a>Жизненный цикл действия  
 Экземпляр действия запускается в состоянии <xref:System.Activities.ActivityInstanceState.Executing>. Если исключения не обнаружены, экземпляр остается в этом состоянии до тех пор, пока дочерние действия и любые другие ожидающие операции (объекты <xref:System.Activities.Bookmark>, например) не завершены, после чего экземпляр переходит в состояние <xref:System.Activities.ActivityInstanceState.Closed>. Родитель экземпляра действия может запросить прекращение работы дочернего действия; если дочернее действие может быть отменено, оно будет завершено в состоянии <xref:System.Activities.ActivityInstanceState.Canceled>. Если в ходе выполнения возникает исключение, среда выполнения переводит действие в состояние <xref:System.Activities.ActivityInstanceState.Faulted> и распространяет исключение по родительской цепочке действий. Далее приводятся три состояния завершения действия.  
  
- **Закрыто:** Действие завершает свою работу и завершила работу.  
  
- **Отменено:** Действие правильно прекратило работу и завершила работу. При переходе в это состояние откат операции не будет выполнен явным образом.  
  
- **Произошел сбой:** Действие обнаружила ошибку и выполнило выход без завершения его работы.  
  
 Во время сохранения или выгрузки действия остаются в состоянии <xref:System.Activities.ActivityInstanceState.Executing>.
