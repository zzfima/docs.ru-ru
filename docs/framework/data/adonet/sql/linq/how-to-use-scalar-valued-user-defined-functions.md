---
title: "Как применять определяемые пользователем скалярные функции | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как применять определяемые пользователем скалярные функции
Для сопоставления клиентского метода, определенного в классе, с пользовательской функцией используется атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute>.  Обратите внимание, что тело метода создает выражение, перехватывающее назначение вызова метода, и передает это выражение в <xref:System.Data.Linq.DataContext> для преобразования и выполнения.  
  
> [!NOTE]
>  Прямое выполнение возможно только при вызове функции вне запроса.  Для получения дополнительной информации см. [Как вызывать встроенные определяемые пользователем функции](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).  
  
## Пример  
 В следующем коде SQL представлена скалярная пользовательская функция `ReverseCustName()`.  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 Для этого кода следует отобразить клиентский метод, подобный следующему.  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## См. также  
 [Определяемые пользователем функции](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)