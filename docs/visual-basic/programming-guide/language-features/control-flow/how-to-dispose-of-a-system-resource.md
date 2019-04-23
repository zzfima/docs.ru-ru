---
title: Практическое руководство. Удаление ресурса системы (Visual Basic)
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
ms.openlocfilehash: e3594db036edc3a6288b0373737c1ee26a691a57
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59341911"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Практическое руководство. Удаление ресурса системы (Visual Basic)
Можно использовать `Using` блок, чтобы гарантировать, что система удаляет ресурс, когда код выходит из блока. Это полезно, если вы используете системный ресурс, которые используют большой объем памяти или других компонентов также требуется использовать.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Для удаления подключения к базе данных после завершения вашего кода с ним  
  
1. Убедитесь, что вы включить соответствующую [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для подключения к базе данных в начале файла исходного кода (в данном случае <xref:System.Data.SqlClient>).  
  
2. Создание `Using` блоке с `Using` и `End Using` инструкций. Внутри блока поместите код, который имеет дело с подключения к базе данных.  
  
3. Объявите соединение и создайте его экземпляр как часть `Using` инструкции.  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Система удаляет ресурс независимо от того, как выйти из блоков, включая регистр необработанное исключение.  
  
     Обратите внимание, что при отсутствии доступа к `sqc` из за пределами `Using` block, так как ее область ограничена блока.  
  
     Этот же прием можно использовать на системный ресурс, такие как дескриптор файла или оболочки COM. Использовании `Using` заблокировать, если вы хотите чтобы оставить ресурс доступным для других компонентов, после закрытия `Using` блока.  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.SqlClient.SqlConnection>
- [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Оператор Using](../../../../visual-basic/language-reference/statements/using-statement.md)
