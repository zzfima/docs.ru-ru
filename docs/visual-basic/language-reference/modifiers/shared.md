---
title: Shared (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: 12c81a9a0651088a348afeaff3b71935d289da53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816287"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)
Указывает, что один или несколько объявленных программных элементов связаны с классом или структурой целиком, а не с конкретным экземпляром класса или структуры.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="when-to-use-shared"></a>Когда следует использовать Shared  
 Совместное использование членов класса или структуры делает ее доступной для каждого экземпляра, а не *не совместно*, где каждый экземпляр хранит собственную копию. Это полезно, например, если значение переменной, применяется ко всему приложению. Если объявить эту переменную как `Shared`, затем все экземпляры доступа в одно место хранения, и если один экземпляр изменяет значение переменной, все экземпляры доступа обновленное значение.  
  
 Совместное использование не удалось изменить уровень доступа члена. Например, можно использовать член класса и private (доступен только внутри класса), или не совместно, так и общедоступных. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** `Shared` можно использовать только на уровне модуля. Это означает, что контекст объявления для `Shared` элемент должен быть классом или структурой и не может быть исходный файл, пространство имен или процедуры.  
  
-   **Комбинированные модификаторы.** Нельзя указать `Shared` вместе с [переопределяет](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), или [ Статические](../../../visual-basic/language-reference/modifiers/static.md) в одном объявлении.  
  
-   **Доступ к.** Получить доступ к совместно используемому элементу путем указания имени класса или структуры, не с именем переменной определенного экземпляра класса или структуры. У вас еще нет для создания экземпляра класса или структуры, для доступа к его общие члены.  
  
     В следующем примере вызывается общая процедура <xref:System.Double.IsNaN%2A> предоставляемые <xref:System.Double> структуры.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **Неявное совместное использование.** Нельзя использовать `Shared` модификатор в [оператор Const](../../../visual-basic/language-reference/statements/const-statement.md), но константы являются общими неявно. Аналогичным образом нельзя объявлять участником модуля или интерфейса, чтобы быть `Shared`, но они неявно являются общими.  
  
## <a name="behavior"></a>Поведение  
  
-   **Хранилище.** Общая переменная или событие хранится в памяти только один раз, независимо от того, сколько экземпляров следует создать его класса или структуры. Аналогичным образом общая процедура или свойство содержит только один набор локальных переменных.  
  
-   **Доступ через переменную экземпляра.** Это можно осуществлять доступ к совместно используемому элементу, указав имя переменной, которая содержит экземпляр класса или структуры. Несмотря на то, что это обычно работает ожидаемым образом, компилятор выдает предупреждающее сообщение и осуществляет доступ с помощью имени класса или структуры, а не переменной.  
  
-   **Доступ через экземпляр выражения.** Если доступ к совместно используемому элементу через выражение, которое возвращает экземпляр его класса или структуры, компилятор осуществляет доступ через имя класса или структуры вместо вычисления выражения. Это приводит к непредвиденным результатам Если предполагалось использовать выражение для выполнения других действий, а также возврат экземпляра. Это показано в следующем примере.  
  
    ```vb
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     В приведенном выше примере компилятор выдает предупреждение, оба раза код обращается к общей переменной `total` через экземпляр. В каждом случае он осуществляет доступ непосредственно через класс `shareTotal` и не делает экземпляры. В случае предполагаемого вызова процедуры `returnClass`, это означает, что она даже не создает вызов `returnClass`, поэтому дополнительные действия для отображения «Вызывается функция returnClass()» не выполняется.  
  
 Модификатор `Shared` можно использовать в следующих контекстах:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Статические](../../../visual-basic/language-reference/modifiers/static.md)
- [Время существования в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
