---
title: "Shared (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Shared"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "элементы, общие"
  - "члены, общие"
  - "не общие"
  - "общие элементы"
  - "Shared - ключевое слово"
  - "общие члены"
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Shared (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что один или несколько объявленных элементов программирования связаны с классом или структурой целиком, а не с определенным экземпляром класса или структуры.  
  
## Заметки  
  
## Когда следует использовать Shared  
 Совместное использование членов класса или структуры делает ее доступной для каждого экземпляра, в отличие от *не являющихся общими* элементов, где каждый экземпляр хранит собственную копию.  Это полезно, например, если значение переменной используется во всем приложении.  Если объявить эту переменную как `Shared`, тогда все экземпляры имеют доступ к одному месту хранения, и если один экземпляр изменяет значение переменной, то все экземпляры получают доступ к обновленному значению.  
  
 Совместное использование не изменяет уровень доступа для члена.  Например, член класса может использоваться совместно и закрытым образом \(только в пределах класса\) или несовместно и открыто.  Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Правила  
  
-   **Контекст объявления.** Можно использовать зарезервированное слово `Shared` только на уровне модуля.  Это означает, что контекст объявления для элемента `Shared` должен быть классом или структурой и не может быть исходным файлом, пространством имен или процедурой.  
  
-   **Комбинированные модификаторы.** Не допускается указание в одном объявлении ключевого слова `Shared` совместно с [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md) или [Static](../../../visual-basic/language-reference/modifiers/static.md).  
  
-   **Доступ.** Доступ к совместно используемому элементу может осуществляться путем указания вместе с ним имени класса или структуры, но не имени переменной экземпляра класса или структуры.  Нет необходимости создавать экземпляр класса или структуры для доступа к их общим членам.  
  
     В следующем примере вызывается совместно используемая процедура <xref:System.Double.IsNaN%2A>, представленная структурой <xref:System.Double>.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **Неявное совместное использование данных.** Нельзя использовать модификатор `Shared` в [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md), но константы неявно являются общими.  Аналогично, нельзя объявлять член модуля или интерфейса как `Shared`, но они являются общими неявно.  
  
## Поведение  
  
-   **Хранилище.** Общая переменная или событие сохраняется в памяти только один раз независимо от того, сколько экземпляров класса или структуры создается.  Аналогично, общая процедура или свойство содержат только один набор локальных переменных.  
  
-   **Доступ через переменную экземпляра.** Доступ к совместно используемому элементу может осуществляться путем указания вместе с ним имени переменной, которая содержит экземпляр класса или структуры.  Хотя, обычно это работает как ожидается, компилятор создает предупреждающее сообщение, и доступ производится с помощью имени класса или структуры, а не переменной.  
  
-   **Доступ через экземпляр выражения.** Если доступ к общему элементу осуществляется через выражение, возвращающее экземпляр его класса или структуры, компилятор осуществляет доступ с помощью имени класса или структуры, а не вычисляет выражение.  Это приводит к непредвиденным результатам, если предполагалось использовать выражение для выполнения других действий или для возврата экземпляра.  Это показано в приведенном ниже примере.  
  
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
  
     В предыдущем примере компилятор создает предупреждение оба раза, когда код обращается к общей переменной `total` через экземпляр.  В каждом случае он осуществляет доступ непосредственно через класс `shareTotal` и не использует экземпляры.  В случае предполагаемого вызова процедуры `returnClass` это означает, что она даже не создает вызов `returnClass`, то есть не выполняются дополнительные действия для отображения "Функция returnClass\(\) вызвана".  
  
 Модификатор `Shared` можно использовать в следующих контекстах:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## См. также  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Static](../../../visual-basic/language-reference/modifiers/static.md)   
 [Время существования в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Процедуры](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)