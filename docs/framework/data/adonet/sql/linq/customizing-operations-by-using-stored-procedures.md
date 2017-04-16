---
title: "Настройка операций с помощью хранимых процедур | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aedbecc1-c33c-4fb4-8861-fdf7e1dc6b8a
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Настройка операций с помощью хранимых процедур
Использование хранимых процедур является наиболее распространенным методом переопределения поведения по умолчанию.  В примерах данного раздела показано, как можно использовать созданные оболочки методов для хранимых процедур и непосредственно вызывать хранимые процедуры.  
  
 При использовании [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] назначение хранимых процедур для настройки операций вставки, обновления и удаления можно выполнять с помощью [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  
  
> [!NOTE]
>  Чтобы считать значения, созданные базой данных, используются выходные параметры хранимых процедур.  Если использовать выходные параметры невозможно, то вместо применения переопределений, созданных конструктором [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], реализуйте разделяемый метод.  После успешного завершения операций `INSERT` или `UPDATE` необходимо установить соответствующие значения членов, сопоставленных значениям, созданным базой данных.  Дополнительные сведения см. в разделе [Обязанности разработчика при переопределении поведения по умолчанию](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md).  
  
## Пример  
  
### Описание  
 В следующем примере предполагается, что класс `Northwind` содержит два метода для вызова хранимых процедур, используемых для переопределений в производном классе.  
  
### Код  
 [!code-csharp[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#1)]  
  
## Пример  
  
### Описание  
 Следующий класс использует эти методы для переопределения.  
  
### Код  
 [!code-csharp[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#2)]  
  
## Пример  
  
### Описание  
 Класс `NorthwindThroughSprocs` можно использовать точно так же, как класс `Northwnd`.  
  
### Код  
 [!code-csharp[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#3)]  
  
## См. также  
 [Обязанности разработчика при переопределении поведения по умолчанию](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)