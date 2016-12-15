---
title: "Практическое руководство. Удаление системного ресурса (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ресурсы [Visual Basic], освобождение системных"
  - "системные ресурсы"
  - "системные ресурсы, освобождение"
  - "Using - блок"
  - "Using - оператор, освобождение системных ресурсов"
  - "Using - оператор, Using...End Using"
  - "код Visual Basic, поток управления"
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Удаление системного ресурса (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Блок `Using` можно использовать, чтобы гарантировать, что система удаляет ресурс, когда ваш код выходит из блока.  Это полезно при использовании ресурса системы, который занимает большой объем памяти, или который хотят использовать другие компоненты.  
  
### Для удаления подключения базы данных, когда она завершает ваш код  
  
1.  Убедитесь, что в начале файла исходного кода \(в данном случае <xref:System.Data.SqlClient>\) включены соответствующие [Оператор Imports \(пространство имен .NET и тип\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для подключения базы данных.  
  
2.  Создайте блок `Using` с помощью `Using` и операторов `End Using`.  Внутри блока поместите код, который имеет дело с подключением базы данных.  
  
3.  Объявите соединение и создайте его экземпляр как часть инструкции `Using`.  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Система удаляет ресурс независимо от способа выхода из блоков, включая случай необработанного исключения.  
  
     Обратите внимание, что не удается получить доступ к `sqc` вне блока `Using`, поскольку ее область ограничена блоком.  
  
     Этот же метод можно использовать для системного ресурса, такого как дескриптор файла или программа\-оболочка COM.  Блок `Using` используется, если требуется оставить ресурс доступным для других компонентов после того, как вы завершили блок `Using`.  
  
## См. также  
 <xref:System.Data.SqlClient.SqlConnection>   
 [Управление ходом выполнения](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Оператор Using](../../../../visual-basic/language-reference/statements/using-statement.md)