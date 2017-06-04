---
title: "Архитектура рабочих процессов Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d4c6495-d64a-46d0-896a-3a01fac90aa9
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Архитектура рабочих процессов Windows
[!INCLUDE[wf](../../../includes/wf-md.md)] поднимает уровень абстракции для разработки интерактивных длительных приложений.Блоки обработки инкапсулируются в виде действий.Действия работают в среде, которая обеспечивает средства для управления потоком, обработки исключений, распространения ошибок, сохранения данных состояния, загрузки и выгрузки текущих рабочих процессов из памяти, отслеживания и управления потоком транзакций.  
  
## Архитектура действий  
 Действия разрабатываются в виде типов CLR, которые являются либо производными от <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> или <xref:System.Activities.NativeActivity> или от их вариантов, возвращающих значение <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601> или <xref:System.Activities.NativeActivity%601>.Разработка действий, которые являются производными от действия <xref:System.Activities.Activity>, позволяет пользователям собирать существующие действия для быстрого создания блоков обработки, работающих в среде рабочих процессов.С другой стороны, действие <xref:System.Activities.CodeActivity> позволяет создавать логику выполнения в управляемом коде с использованием <xref:System.Activities.CodeActivityContext> в основном для доступа к аргументам действий.<xref:System.Activities.AsyncCodeActivity> аналогично <xref:System.Activities.CodeActivity>, за исключением того, что его можно использовать для реализации асинхронных задач.Разработка действий, которые являются производными от действия <xref:System.Activities.NativeActivity>, позволяет пользователям получать доступ к среде выполнения посредством <xref:System.Activities.NativeActivityContext> для таких функций, как планирование дочерних объектов, создание закладок, вызов асинхронной работы, регистрации транзакций и других операций.  
  
 Создание действий, которые происходят от действия <xref:System.Activities.Activity>, является декларативным, при этом эти действия не могут быть созданы на языке XAML.В следующем примере действие `Prompt` создается при помощи других действий для тела выполнения.  
  
```  
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
  
## Контекст действия  
 <xref:System.Activities.ActivityContext> представляет собой интерфейс автора действий со средой выполнения рабочих процессов и обеспечивает доступ ко многим функциям среды выполнения.В следующем примере определяется действие, которое использует контекст выполнения для создания закладки \(механизм, позволяющий действию зарегистрировать точку продолжения в ходе выполнения, которое может быть возобновлено при передаче узлом данных в действие\).  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
## Жизненный цикл действия  
 Экземпляр действия запускается в состоянии <xref:System.Activities.ActivityInstanceState>.Если исключения не обнаружены, экземпляр остается в этом состоянии до тех пор, пока дочерние действия и любые другие ожидающие операции \(объекты <xref:System.Activities.Bookmark>, например\) не будут завершены, после чего экземпляр переходит в состояние <xref:System.Activities.ActivityInstanceState>.Родительский экземпляр действия может приказать дочернему действию прекратить работу; если дочернее действие может быть отменено, оно будет завершено в состоянии <xref:System.Activities.ActivityInstanceState>.Если в ходе выполнения возникает исключение, среда выполнения переводит действие в состояние <xref:System.Activities.ActivityInstanceState> и распространяет исключение по родительской цепочке действий.Далее приводятся три состояния завершения действия.  
  
-   **Закрыто** — действие завершило работу и выполнило выход.  
  
-   **Отменено** — действие правильно прекратило работу и выполнило выход.При переходе в это состояние откат операции не будет выполнен явным образом.  
  
-   **Ошибка** — действие обнаружило ошибку и выполнило выход без завершения работы.  
  
 Действия остаются в состоянии <xref:System.Activities.ActivityInstanceState> во время сохранения или выгрузки.