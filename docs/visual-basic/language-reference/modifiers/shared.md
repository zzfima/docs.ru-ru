---
title: Shared
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
ms.openlocfilehash: 98fa25d2283408dfb80e82fbc620a1b284e5c530
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349117"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)
Указывает, что один или несколько объявленных программных элементов связаны с классом или структурой в большом объеме, а не с конкретным экземпляром класса или структуры.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="when-to-use-shared"></a>Когда следует использовать Shared  
 Совместное использование члена класса или структуры делает его доступным для каждого экземпляра, а не для *совместного использования*, где каждый экземпляр хранит собственную копию. Это полезно, например, если значение переменной применяется ко всему приложению. Если объявить эту переменную для `Shared`, то все экземпляры будут обращаться к тому же месту хранения, и если один экземпляр изменит значение переменной, то все экземпляры получают доступ к обновленному значению.  
  
 Совместное использование не изменяет уровень доступа элемента. Например, член класса может быть общим и частным (доступным только в пределах класса), а также не является общим и общим. Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
- **Контекст объявления.** `Shared` можно использовать только на уровне модуля. Это означает, что контекст объявления для элемента `Shared` должен быть классом или структурой и не может быть исходным файлом, пространством имен или процедурой.  
  
- **Комбинированные модификаторы.** В одном объявлении нельзя указывать `Shared` вместе с [переопределениями](../../../visual-basic/language-reference/modifiers/overrides.md), [переопределяемыми](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)или [static](../../../visual-basic/language-reference/modifiers/static.md) .  
  
- **Данному.** Доступ к общему элементу осуществляется путем указания его имени класса или структуры, а не имени переменной определенного экземпляра его класса или структуры. Вам даже не нужно создавать экземпляр класса или структуры для доступа к его общим членам.  
  
     В следующем примере вызывается общая процедура <xref:System.Double.IsNaN%2A> предоставляемой структурой <xref:System.Double>.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
- **Неявный общий доступ.** Нельзя использовать модификатор `Shared` в [операторе const](../../../visual-basic/language-reference/statements/const-statement.md), но константы неявно являются общими. Аналогичным образом нельзя объявить член модуля или интерфейса для `Shared`, но они являются неявно общими.  
  
## <a name="behavior"></a>Поведение  
  
- **Объема.** Общая переменная или событие хранится в памяти только один раз, независимо от того, сколько экземпляров вы создаете его класс или структуру. Аналогично, Общая процедура или свойство содержит только один набор локальных переменных.  
  
- **Доступ через переменную экземпляра.** Доступ к общему элементу можно получить, добавив в него имя переменной, содержащей конкретный экземпляр его класса или структуры. Несмотря на то, что обычно работает, как и ожидалось, компилятор создает предупреждающее сообщение и предоставляет доступ через имя класса или структуры вместо переменной.  
  
- **Доступ через выражение экземпляра.** При доступе к общему элементу с помощью выражения, возвращающего экземпляр класса или структуры, компилятор делает доступ через имя класса или структуры вместо вычисления выражения. Это приводит к непредвиденным результатам, если выражение предназначено для выполнения других действий, а также для возврата экземпляра. Это показано в следующем примере.  
  
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
  
     В предыдущем примере компилятор выдает предупреждающее сообщение в обоих случаях, когда код обращается к общей переменной `total` через экземпляр. В каждом случае доступ осуществляется напрямую через класс `shareTotal` и не используется ни один экземпляр. В случае предполагаемого вызова процедуры `returnClass`это означает, что он даже не создает вызов `returnClass`, поэтому дополнительное действие отображения "Function Ретурнкласс ()" не выполняется.  
  
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
