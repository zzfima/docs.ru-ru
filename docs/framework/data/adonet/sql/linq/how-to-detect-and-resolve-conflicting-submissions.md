---
title: "Как обнаруживать и разрешать конфликты отправки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как обнаруживать и разрешать конфликты отправки
Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет целый ряд ресурсов для обнаружения и разрешения конфликтов, возникающих при внесении изменений в базу данных несколькими пользователями.  Для получения дополнительной информации см. [Как управлять конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).  
  
## Пример  
 В следующем примере показан блок `try`\/`catch`, который перехватывает исключение <xref:System.Data.Linq.ChangeConflictException>.  Сведения о сущностях и членах для каждого конфликта отображаются в окне «Консоль».  
  
> [!NOTE]
>  Для поддержки извлечения этих сведений необходимо включить директиву `using System.Reflection` \(`Imports System.Reflection` в Visual Basic\).  Для получения дополнительной информации см. <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## См. также  
 [Внесение и отправка изменений данных ](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)   
 [Как управлять конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)