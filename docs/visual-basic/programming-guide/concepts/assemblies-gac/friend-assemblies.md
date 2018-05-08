---
title: Дружественные сборки (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
ms.openlocfilehash: 91bc33f33c4fc34c6e0f3ae197ecd2b876161de3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="friend-assemblies-visual-basic"></a>Дружественные сборки (Visual Basic)
Объект *дружественной сборки* — это сборка, можно получить доступ к другой сборке [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) типы и члены. Если сборка определяется как дружественная, помечать типы и члены как открытые для того, чтобы другие сборки могли получить к ним доступ, больше не требуется. Это особенно удобно в следующих ситуациях:  
  
-   Во время модульного тестирования, если тестовый код выполняется отдельной сборке, но требует доступ к членам в тестируемой сборке, которые помечены как `Friend`.  
  
-   Если вы разрабатываете библиотеку классов, и дополнения к библиотеке содержатся в отдельных сборках, но требуют доступа к членам в существующих сборках, которые помечены как `Friend`.  
  
## <a name="remarks"></a>Примечания  
 С помощью атрибута <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> можно определить одну или несколько дружественных сборок для указанной сборки. В следующем примере используется атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> в сборке A, а сборка `AssemblyB` указывается в качестве дружественной. В результате сборка `AssemblyB` получает доступ ко всем типам и членам в сборке А, помеченным как `Friend`.  
  
> [!NOTE]
>  При компиляции сборки (сборки `AssemblyB`), которая будет обращаться ко внутренним типам или членам другой сборки (сборки *А*), необходимо прямо указать имя выходного файла (EXE или DLL), используя параметр компилятора **/out**. Это необходимо потому, что компилятор еще не создал имя сборки, формируемой во время привязки к внешним ссылкам. Дополнительные сведения см. в разделе [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
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
  
 Доступ к типам и членам `Friend` могут получить только те сборки, которые будут прямо обозначены как дружественные. Например, если сборка B является дружественной для сборки A, а сборка C ссылается на сборку B, сборка C не получает доступ к типам `Friend` в A.  
  
 Компилятор выполняет некоторые основные проверки имени дружественной сборки, передаваемого в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Если сборка *A* объявляет *B* как дружественную сборку, действуют следующие правила проверки:  
  
-   Если сборка *A* имеет строгое имя, сборка *B* должна также иметь строгое имя. Имя дружественной сборки, передаваемое в атрибут, должно состоять из имени сборки и открытого ключа из ключа строгого имени, который используется для подписи сборки *B*.  
  
     Имя дружественной сборки, передаваемое в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, не может быть строгим именем сборки *B*, поэтому включать в него версию сборки, язык и региональные параметры, архитектуру или маркер открытого ключа не следует.  
  
-   Если сборка *A* не имеет строгого имени, имя дружественной сборки должно состоять только из имени сборки. Дополнительные сведения см. в разделе [как: создание неподписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).  
  
-   Если сборка *B* имеет строгое имя, необходимо указать ключ строгого имени для сборки *B*, используя параметр проекта или параметр компилятора командной строки `/keyfile`. Дополнительные сведения см. в разделе [как: создать подпись дружественные сборки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).  
  
 Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> также позволяет обеспечить общий доступ к типам, но имеет следующие отличия:  
  
-   Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> применяется к отдельному типу, тогда как дружественная сборка относится ко всей сборке.  
  
-   Если в сборке *A* существуют сотни типов, которые должны использоваться совместно со сборкой *B*, к каждому из них необходимо добавить <xref:System.Security.Permissions.StrongNameIdentityPermission>. Если используется дружественная сборка, достаточно объявить дружественные отношения всего один раз.  
  
-   Если вы используете <xref:System.Security.Permissions.StrongNameIdentityPermission>, типы для общего доступа необходимо объявить как открытые. При использовании дружественной сборки общие типы объявляются как `Friend`.  
  
 Сведения о том, как обращаться к сборке `Friend` типы и методы из файла модуля (файл с расширением NETMODULE-файл), в разделе [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 <xref:System.Security.Permissions.StrongNameIdentityPermission>  
 [Как: создание неподписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [Как: Создание подписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)
