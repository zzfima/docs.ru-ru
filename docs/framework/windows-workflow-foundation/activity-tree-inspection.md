---
title: Проверка дерева действий
ms.date: 03/30/2017
ms.assetid: 100d00e4-8c1d-4233-8fbb-dd443a01155d
ms.openlocfilehash: 692f36d993c3f9c27839122b388a24d0698a2b59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183038"
---
# <a name="activity-tree-inspection"></a>Проверка дерева действий
Проверка дерева действий используется авторами приложений рабочих процессов для проверки рабочих процессов, размещенных приложением. Используя службы <xref:System.Activities.WorkflowInspectionServices>, в рабочих процессах можно искать определенные дочерние действия, отдельно взятые действия и их свойства могут быть перечислены, а метаданные действий времени выполнения могут быть кэшированы в определенное время. В этом разделе представлены общие сведения о службах <xref:System.Activities.WorkflowInspectionServices> и их использовании для проверки дерева действий.  
  
## <a name="using-workflowinspectionservices"></a>Использование WorkflowInspectionServices  
 Метод <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> используется для перечисления всех действий в указанном дереве действий. <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> возвращает перечислимый объект, который касается всех действий в дереве, включая дочерние действия, обработчики делегатов, значения переменных по умолчанию и выражения аргументов. В следующем примере создается определение рабочего процесса при помощи <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.WriteLine> и выражений. После того, как определение рабочего процесса создано, выполняется его вызов, а затем вызывается метод `InspectActivity`.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#45](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#45)]  
  
 Для перечисления действий вызывается метод <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> относительно корневого действия и рекурсивно относительно каждого возвращенного действия. В следующем примере имя <xref:System.Activities.Activity.DisplayName%2A> каждого действия и выражения в дереве действий записывается в консоль.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#46](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#46)]  
  
 Результатом этого образца кода является следующее.  
  
 **Элемент списка 1**  
**Список Пункт 2**
**Список Пункт 3**
**Список Пункт 4**
**Список Пункт 5**
**Пунктов, добавленных в коллекцию.** 
 **Последовательность** **Литературный\<<список струнных>>**  
 **While**  
 **Строка\<адд-коллекции>**  
 **VariableValue<\<ICollection струнный>>**  
 **ЛамбдаВалд\<струнный>**  
 **LocationReferenceValue<\<список строки>>**  
 **ЛамбдаВале\<Булеан>**  
 **LocationReferenceValue<\<список строки>>**  
 **ForEach\<String>**  
 **ПеременныйValue<IEnumerable\<String>>**  
 **WriteLine**  
 **ДелегатАргументВалуд\<Струнный>**  
 **Последовательности**  
 **WriteLine**  
 **Используется\<буквальная строка>** Для получения определенной деятельности вместо <xref:System.Activities.WorkflowInspectionServices.Resolve%2A> перечисления всех действий. Как <xref:System.Activities.WorkflowInspectionServices.Resolve%2A>, так <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> выполняют кэширование метаданных, если метод `WorkflowInspectionServices.CacheMetadata` не был вызван ранее. Если метод <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> уже был вызван, то <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> основывается на существующих метаданных. Таким образом, если с момента последнего вызова метода <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> в дерево были внесены изменения, <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A> может возвратить неожиданные результаты. Если изменения были внесены в <xref:System.Activities.WorkflowInspectionServices.GetActivities%2A>рабочий процесс после вызова, метаданные <xref:System.Activities.Validation.ActivityValidationServices> <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> могут быть повторно кэшированы, вызывая метод. Кэширование метаданных рассматривается в следующем разделе.  
  
### <a name="caching-metadata"></a>Кэширование метаданных  
 При кэшировании метаданных для действия создается и проверяется описание аргументов, переменных, дочерних действий и делегатов действия. По умолчанию метаданные кэшируются средой выполнения во время подготовки действия к выполнению. Если автору узла рабочего процесса необходимо кэшировать метаданные для действия или дерева действий раньше, например для выведения всех расходов на передний план, можно использовать метод <xref:System.Activities.WorkflowInspectionServices.CacheMetadata%2A> для выполнения кэширования метаданных в нужное время.
