---
title: "Поддержка транзакций | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Поддержка транзакций
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает три различные модели транзакций.  Далее представлен список этих моделей в порядке выполненных проверок.  
  
## Явные локальные транзакции  
 При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, если свойству <xref:System.Data.Linq.DataContext.Transaction%2A> задана транзакция \(`IDbTransaction`\), вызов <xref:System.Data.Linq.DataContext.SubmitChanges%2A> выполняется в контексте этой же транзакции.  
  
 Вашей обязанностью является выполнение фиксации или отката транзакции после ее успешного выполнения.  Подключение, соответствующее транзакции, должно совпадать с подключением, используемым для создания <xref:System.Data.Linq.DataContext>.  При использовании разных подключений создается исключение.  
  
## Явные распределяемые транзакции  
 API [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] \(включая, но не ограничиваясь <xref:System.Data.Linq.DataContext.SubmitChanges%2A>\) можно вызвать в области действия активного <xref:System.Transactions.Transaction>.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обнаруживает, что вызов находится в области данной транзакции, и поэтому не создает новую транзакцию.  В этом случае [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] также не закрывает соединение.  В контексте данной транзакции можно осуществить запрос и выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
## Неявные транзакции  
 При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проверяет наличие вызова в области действия <xref:System.Transactions.Transaction> или задана ли свойству `Transaction` \(`IDbTransaction`\) запускаемая пользователем локальная транзакция.  Если транзакции не обнаружены, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запускает локальную транзакцию \(`IDbTransaction`\) использует ее для выполнения сгенерированных команд SQL.  После успешного выполнения всех команд SQL [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] фиксирует локальную транзакцию и возвращается.  
  
## См. также  
 [Дополнительные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [Как объединить в пакеты отправку данных с помощью транзакций](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)