---
title: Практическое руководство. Удаление системного ресурса
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: c493051050442597196ba484fb9ce8e99249dbb7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353946"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Практическое руководство. Удаление системного ресурса (Visual Basic)
Можно использовать блок `Using`, чтобы гарантировать, что система удаляет ресурс, когда код выходит из блока. Это полезно, если вы используете системный ресурс, который потребляет большой объем памяти или что другие компоненты также хотят использовать.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Удаление подключения к базе данных после завершения работы с ним кода  
  
1. Убедитесь, что вы включили соответствующий [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для подключения к базе данных в начале исходного файла (в данном случае <xref:System.Data.SqlClient>).  
  
2. Создайте блок `Using` с инструкциями `Using` и `End Using`. Внутри блока разместите код, который работает с подключением к базе данных.  
  
3. Объявите соединение и создайте его экземпляр в составе оператора `Using`.  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Система уничтожает ресурс независимо от того, как вы выйдете из блока, включая случай необработанного исключения.  
  
     Обратите внимание, что доступ к `sqc` извне блока `Using` невозможен, так как его область ограничена блоком.  
  
     Эту же методику можно использовать для системных ресурсов, таких как файловый обработчик или оболочка COM. Используйте блок `Using`, если вы хотите оставить ресурс доступным для других компонентов после выхода из блока `Using`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.SqlClient.SqlConnection>
- [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Using](../../../../visual-basic/language-reference/statements/using-statement.md)
