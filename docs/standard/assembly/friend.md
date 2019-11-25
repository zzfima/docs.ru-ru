---
title: Дружественные сборки
ms.date: 08/20/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
dev_langs:
- csharp
- vb
ms.openlocfilehash: a74d4b74ead8492028a092e090f9281231802a87
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348167"
---
# <a name="friend-assemblies"></a>Дружественные сборки

*Дружественная сборка* — это сборка, которая может обращаться к [внутренним](../../csharp/language-reference/keywords/internal.md) (C#) или [дружественным](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) типам и членам другой сборки. Если сборка определяется как дружественная, помечать типы и члены как открытые для того, чтобы другие сборки могли получить к ним доступ, больше не требуется. Это особенно удобно в следующих ситуациях:

- Во время модульного теста, если тестовый код выполняется в отдельной сборке, но требует доступа к членам тестируемой сборки, помеченным как `internal` в C# или `Friend` в Visual Basic.

- При разработке библиотек классов, если дополнения к этой библиотеке содержатся в отдельных сборках, но требуют доступа к членам в существующих сборках, помеченным как `internal`в C# или `Friend` в Visual Basic.

## <a name="remarks"></a>Примечания

С помощью атрибута <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> можно определить одну или несколько дружественных сборок для указанной сборки. В следующем примере используется атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> в сборке *Assembly A*, а сборка *AssemblyB* указана в качестве дружественной. В результате сборка *AssemblyB* получает доступ ко всем типам и членам в сборке *Assembly A*, помеченным как `internal` в C# или `Friend` в Visual Basic.

> [!NOTE]
> При компиляции сборки, такой как *AssemblyB*, которая будет обращаться ко внутренним типам или членам другой сборки, такой как *Assembly A*, нужно явно указать имя выходного файла (*EXE* или *DLL*), используя параметр компилятора **-out**. Это необходимо потому, что компилятор еще не создал имя сборки, формируемой во время привязки к внешним ссылкам. Дополнительные сведения см. в разделе [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) или [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

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

```vb
Imports System.Runtime.CompilerServices
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

Доступ к типам и членам `internal` (C#) или `Friend` (Visual Basic) могут получить только те сборки, которые будут явно обозначены как дружественные. Например, если сборка *AssemblyB* является дружественной для сборки *Assembly A*, а сборка *Assembly C* ссылается на сборку *AssemblyB*, сборка *Assembly C* не получает доступ к типам `internal` (C#) или `Friend` (Visual Basic) в сборке *Assembly A*.

Компилятор выполняет некоторые основные проверки имени дружественной сборки, передаваемого в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Если сборка *Assembly A* объявляет *AssemblyB* как дружественную сборку, действуют следующие правила проверки:

- Если сборка *Assembly A* имеет строгое имя, сборка *AssemblyB* должна также иметь строгое имя. Имя дружественной сборки, передаваемое в атрибут, должно состоять из имени сборки и открытого ключа из ключа строгого имени, который используется для подписи сборки *AssemblyB*.

     Имя дружественной сборки, передаваемое в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, не может быть строгим именем сборки *AssemblyB*. Не следует включать версию сборки, язык и региональные параметры, архитектуру или маркер открытого ключа.

- Если сборка *Assembly A* не имеет строгого имени, имя дружественной сборки должно состоять только из имени сборки. Дополнительные сведения см. в разделе [Практическое руководство. Создание неподписанных дружественных сборок](create-unsigned-friend.md).

- Если сборка *AssemblyB* имеет строгое имя, нужно указать ключ строгого имени для сборки *AssemblyB*, используя параметр проекта или параметр компилятора командной строки `/keyfile`. Дополнительные сведения см. в разделе [Практическое руководство. Создание подписанных дружественных сборок](create-signed-friend.md).

 Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> также позволяет обеспечить общий доступ к типам, но имеет следующие отличия:

- Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> применяется к отдельному типу, тогда как дружественная сборка относится ко всей сборке.

- Если в сборке *Assembly A* существуют сотни типов, которые должны использоваться совместно со сборкой *AssemblyB*, к каждому из них необходимо добавить <xref:System.Security.Permissions.StrongNameIdentityPermission>. Если используется дружественная сборка, достаточно объявить дружественные отношения всего один раз.

- Если вы используете <xref:System.Security.Permissions.StrongNameIdentityPermission>, типы для общего доступа необходимо объявить как открытые. При использовании дружественной сборки общие типы объявляются как `internal` (C#) или `Friend` (Visual Basic).

Сведения о том, как получить доступ к типам и методам `internal` (C#) или `Friend` (Visual Basic) сборки из файла модуля (файла с расширением *NETMODULE*), см. в разделе [-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) или [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).

## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [Практическое руководство. Создание неподписанных дружественных сборок](create-unsigned-friend.md)
- [Практическое руководство. Создание подписанных дружественных сборок](create-signed-friend.md)
- [Сборки в .NET](index.md)
- [Руководство по программированию на C#](../../csharp/programming-guide/index.md)
- [Основные понятия программирования (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
