---
title: Практическое руководство. Удаление системного ресурса (Visual Basic)
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
ms.openlocfilehash: cbb66934833da2bd6f0b797944dbb9c4df267cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>Практическое руководство. Удаление системного ресурса (Visual Basic)
Можно использовать `Using` блок, чтобы гарантировать, что система удаляет ресурс, когда код выходит из блока. Это полезно, если вы используете системный ресурс, который потребляет большой объем памяти или другие компоненты также планируете использовать.  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>Чтобы освободить подключения к базе данных, когда она завершает ваш код  
  
1.  Убедитесь, что включены соответствующие [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для подключения к базе данных в начале файла исходного кода (в данном случае <xref:System.Data.SqlClient>).  
  
2.  Создание `Using` блоке с `Using` и `End Using` инструкции. Внутри блока поместите код, который реагирует на подключение к базе данных.  
  
3.  Объявите соединение и создайте его экземпляр как часть `Using` инструкции.  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     Система удаляет ресурс независимо от способа выхода из блоков, включая регистр необработанное исключение.  
  
     Обратите внимание, что не удается получить доступ к `sqc` из вне `Using` заблокировать, так как его область ограничена блока.  
  
     Этот же способ можно использовать на системный ресурс, такие как дескриптор файла или оболочки COM. Вы используете `Using` заблокировать, если нужно чтобы оставить ресурс доступным для других компонентов после закрытия `Using` блока.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.SqlClient.SqlConnection>  
 [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Структуры решений](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Другие структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [Вложенные структуры управления](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Оператор Using](../../../../visual-basic/language-reference/statements/using-statement.md)
