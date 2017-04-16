---
title: "Методы System.Math | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f299521-6f41-4720-bd70-67c93fc50948
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Методы System.Math
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает следующие методы <xref:System.Math>.  
  
-   <xref:System.Math.DivRem%28System.Int32%2CSystem.Int32%2CSystem.Int32%40%29?displayProperty=fullName>  
  
-   <xref:System.Math.DivRem%28System.Int64%2CSystem.Int64%2CSystem.Int64%40%29?displayProperty=fullName>  
  
-   <xref:System.Math.IEEERemainder%28System.Double%2CSystem.Double%29?displayProperty=fullName>  
  
## Отличия от платформы .NET  
 Семантики округления в .NET Framework отличаются от подобных семантик SQL Server.  В платформе .NET Framework с помощью метода <xref:System.Math.Round%2A> выполняется *банковское округление*, при котором числа, оканчивающиеся на 0,5, округляются до ближайшего четного числа, а не до ближайшего большего числа.  Например, число 2,5 округляется до 2, а 3,5 \- до 4.  \(Это помогает избежать систематического смещения в сторону более высоких значений в транзакциях данных.\)  
  
 В SQL, наоборот, функция `ROUND` всегда округляет от нуля.  Поэтому число 2,5 округляется до 3, тогда как в платформе .NET Framework \- до 2.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] передается в семантики SQL `ROUND` и не пытается реализовать банковское округление.  
  
## См. также  
 [Типы данных и функции](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)