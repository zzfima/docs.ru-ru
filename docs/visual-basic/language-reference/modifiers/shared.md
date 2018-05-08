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
ms.openlocfilehash: b15dd08d69f372317b9140001e8072eeb66d44ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)
Указывает, что один или несколько объявленных программных элементов связаны с классом или структурой целиком, а не с определенным экземпляром класса или структуры.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="when-to-use-shared"></a>Когда следует использовать Shared  
 Совместное использование членов класса или структуры делает ее доступной для каждого экземпляра, а не *не совместно*, где каждый экземпляр хранит собственную копию. Это полезно, например, если значение переменной используется для всего приложения. Если объявить эту переменную как `Shared`, затем все экземпляры доступа место хранения и доступа, если один экземпляр изменяет значение переменной, все экземпляры обновленное значение.  
  
 Совместное использование не изменяет уровень доступа члена. Например, член класса можно использовать совместно и private (доступен только в пределах класса), или открытый, так и не используемые совместно. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** `Shared` можно использовать только на уровне модуля. Это означает, что контекст объявления для `Shared` элемент должен быть классом или структурой и не может быть исходным файлом, пространством имен или процедуры.  
  
-   **Комбинированные модификаторы.** Нельзя указать `Shared` вместе с [переопределяет](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), или [ Статические](../../../visual-basic/language-reference/modifiers/static.md) в одном объявлении.  
  
-   **Доступ к.** Доступ к совместно используемому элементу путем указания имени класса или структуры, не с именем переменной определенного экземпляра класса или структуры. Вы даже нет для создания экземпляра класса или структуры для доступа к его общие члены.  
  
     В следующем примере вызывается общую процедуру <xref:System.Double.IsNaN%2A> предоставляемые <xref:System.Double> структуры.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **Неявное совместное использование данных.** Нельзя использовать `Shared` модификатора [оператор Const](../../../visual-basic/language-reference/statements/const-statement.md), но константы неявно являются общими. Аналогичным образом, нельзя объявлять член модуля или интерфейса быть `Shared`, но они являются общими неявно.  
  
## <a name="behavior"></a>Поведение  
  
-   **хранилище.** Общая переменная или событие сохраняется в памяти только один раз, независимо от того, сколько экземпляров, создайте его класса или структуры. Аналогичным образом общая процедура или свойство содержат только один набор локальных переменных.  
  
-   **Доступ через переменную экземпляра.** Можно получить доступ к совместно используемому элементу, указав его с именем переменной, которая содержит экземпляр класса или структуры. Несмотря на то, что это обычно работает ожидаемым образом, компилятор выдает предупреждающее сообщение и доступ через имя класса или структуры, а не переменной.  
  
-   **Доступ через экземпляр выражения.** Если доступ к совместно используемому элементу осуществляется через выражение, возвращающее экземпляр его класса или структуры, компилятор осуществляет доступ с помощью имени класса или структуры, а не оценки выражения. Это приводит к непредвиденным результатам, если предполагалось использовать выражение для выполнения других действий, а также возврат экземпляра. Это показано в следующем примере.  
  
    ```  
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
  
     В предыдущем примере, компилятор создает предупреждение оба раза код обращается к общей переменной `total` через экземпляр. В каждом случае он осуществляет доступ непосредственно через класс `shareTotal` и не вносит в него экземпляры. В случае предполагаемого вызова процедуры `returnClass`, это означает, что она даже не создает вызов `returnClass`, поэтому дополнительные действия для отображения «Вызывается функция returnClass()» не выполняется.  
  
 Модификатор `Shared` можно использовать в следующих контекстах:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Статические](../../../visual-basic/language-reference/modifiers/static.md)  
 [Время существования в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
