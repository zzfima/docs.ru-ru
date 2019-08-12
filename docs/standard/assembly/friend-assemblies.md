---
title: Дружественные сборки (C#)
ms.date: 03/03/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
ms.openlocfilehash: 770eb70a5350d7d26e03cb4e605b442100da2a53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "68671199"
---
# <a name="friend-assemblies"></a>Дружественные сборки

*Дружественная сборка* — это сборка, которая может обращаться к [внутренним](../../csharp/language-reference/keywords/internal.md) (в C#, [дружественным](../../visual-basic/language-reference/modifiers/friend.md) в Visual Basic) типам и членам другой сборки. Если сборка определяется как дружественная, помечать типы и члены как открытые для того, чтобы другие сборки могли получить к ним доступ, больше не требуется. Это особенно удобно в следующих ситуациях:

- Во время модульного теста, если тестовый код выполняется в отдельной сборке, но требует доступа к членам тестируемой сборки, помеченным как `internal` в C# или `Friend` в Visual Basic.

- При разработке библиотек классов, если дополнения к этой библиотеке содержатся в отдельных сборках, но требуют доступа к членам в существующих сборках, помеченным как `internal`в C# или `Friend` в Visual Basic.

## <a name="remarks"></a>Примечания

С помощью атрибута <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> можно определить одну или несколько дружественных сборок для указанной сборки. В следующем примере используется атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> в сборке A, а сборка `AssemblyB` указывается в качестве дружественной. В результате сборка `AssemblyB` получает доступ ко всем типам и членам в сборке А, помеченным как `internal` в C# или `Friend` в Visual Basic.

> [!NOTE]
> При компиляции сборки (сборки `AssemblyB`), которая будет обращаться ко внутренним типам или членам другой сборки (сборки *А*), необходимо прямо указать имя выходного файла (EXE или DLL), используя параметр компилятора **/out**. Это необходимо потому, что компилятор еще не создал имя сборки, формируемой во время привязки к внешним ссылкам. Дополнительные сведения см. в разделах [/out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) или [/out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

```csharp
using System.Runtime.CompilerServices;
using System;

[assembly: InternalsVisibleTo("AssemblyB")]

// The class is internal by default.
class FriendClass
{
    public void Test()
    {
        Console.WriteLine("Sample Class");
    }
}

// Public class that has an internal method.
public class ClassWithFriendMethod
{
    internal void Test()
    {
        Console.WriteLine("Sample Method");
    }

}
```

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

```vb
Imports System.Runtime.CompilerServices
Imports System
<Assembly: InternalsVisibleTo("AssemblyB")>

' Friend class.
Friend Class FriendClass
    Public Sub Test()
        Console.WriteLine("Sample Class")
    End Sub
End Class

' Public class with a Friend method.
Public Class ClassWithFriendMethod
    Friend Sub Test()
        Console.WriteLine("Sample Method")
    End Sub
End Class
```

---

Доступ к типам и членам `internal` (в C#, `Friend` в Visual Basic) могут получить только те сборки, которые будут прямо обозначены как дружественные. Например, если сборка B является дружественной для сборки A, а сборка C ссылается на сборку B, сборка C не получает доступ к типам `internal` (в C#, `Friend` в Visual Basic) в A.

Компилятор выполняет некоторые основные проверки имени дружественной сборки, передаваемого в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Если сборка *A* объявляет *B* как дружественную сборку, действуют следующие правила проверки:

- Если сборка *A* имеет строгое имя, сборка *B* должна также иметь строгое имя. Имя дружественной сборки, передаваемое в атрибут, должно состоять из имени сборки и открытого ключа из ключа строгого имени, который используется для подписи сборки *B*.

     Имя дружественной сборки, передаваемое в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, не может быть строгим именем сборки *B*, поэтому включать в него версию сборки, язык и региональные параметры, архитектуру или маркер открытого ключа не следует.

- Если сборка *A* не имеет строгого имени, имя дружественной сборки должно состоять только из имени сборки. Дополнительные сведения см. в разделе [Практическое руководство. Создание неподписанных дружественных сборок (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) или [Практическое руководство. Создание неподписанных дружественных сборок (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).

- Если сборка *B* имеет строгое имя, необходимо указать ключ строгого имени для сборки *B*, используя параметр проекта или параметр компилятора командной строки `/keyfile`. Дополнительные сведения см. в разделе [Практическое руководство. Создание подписанных дружественных сборок (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) или [Практическое руководство. Создание подписанных дружественных сборок (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).

 Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> также позволяет обеспечить общий доступ к типам, но имеет следующие отличия:

- Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> применяется к отдельному типу, тогда как дружественная сборка относится ко всей сборке.

- Если в сборке *A* существуют сотни типов, которые должны использоваться совместно со сборкой *B*, к каждому из них необходимо добавить <xref:System.Security.Permissions.StrongNameIdentityPermission>. Если используется дружественная сборка, достаточно объявить дружественные отношения всего один раз.

- Если вы используете <xref:System.Security.Permissions.StrongNameIdentityPermission>, типы для общего доступа необходимо объявить как открытые. При использовании дружественной сборки общие типы объявляются как `internal` (в C#, `Friend` в Visual Basic).

Сведения о том, как получить доступ к типам и методам сборки `internal` (в C#, `Friend` в Visual Basic) из файла модуля (файла с расширением NETMODULE), см. в разделе [/moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) или [/moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).

## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [Практическое руководство. Создание неподписанных дружественных сборок (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [Практическое руководство. Создание неподписанных дружественных сборок (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [Практическое руководство. Создание подписанных дружественных сборок в C#](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [Практическое руководство. Создание подписанных дружественных сборок (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [Сборки в .NET](index.md)
- [Руководство по программированию на C#](../../csharp/programming-guide/index.md)
- [Основные понятия программирования](../../visual-basic/programming-guide/concepts/index.md)
