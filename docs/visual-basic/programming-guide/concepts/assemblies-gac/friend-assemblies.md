---
title: "Дружественные сборки (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c6e01ae91b9d5d875bb618993cd9eda82db59399
ms.lasthandoff: 03/13/2017

---
# <a name="friend-assemblies-visual-basic"></a>Дружественные сборки (Visual Basic)
Объект *дружественной сборки* — это сборка, можно получить доступ к другой сборке [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) типы и члены. Если вы сборка определена как дружественная сборка, необходимо больше не помечать типы и члены как открытые, чтобы они доступны в других сборках. Это особенно удобно в следующих случаях:  
  
-   Во время модульного тестирования, когда код теста выполняется в отдельной сборке, но требует доступ к членам в тестируемой сборке, которые помечены как `Friend`.  
  
-   Если разрабатывается библиотека классов, и дополнения к библиотеке содержатся в отдельных сборках, но требуют доступа к членам в существующих сборках, которые помечены как `Friend`.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибутом опознания дружественных сборок для данной сборки.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> В следующем примере используется <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>в сборке A и задающий сборку `AssemblyB` как дружественную сборку.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Это позволяет сборке `AssemblyB` доступ ко всем типам и членам в сборке, которые помечены как `Friend`.  
  
> [!NOTE]
>  При компиляции сборки (сборка `AssemblyB`) для доступа к внутренним типам и членам другой сборки (сборка *A*), необходимо явно указать имя выходного файла (.exe или .dll) с помощью **/out** параметр компилятора. Это необходимо, потому что компилятор еще не создал имя сборки, который создается во время его привязки к внешним ссылкам. Дополнительные сведения см. в разделе [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
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
  
 Только сборки, которые явным образом указаны как дружественные можно получить доступ к `Friend` типы и члены. Например, если сборка B является дружественной для сборки A и сборка C ссылается на сборку B, C не имеет доступа к `Friend` типы в сборке A.  
  
 Компилятор выполняет некоторые основные проверки имя дружественной сборки, передаваемый <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Если сборка *A* объявляет *B* как дружественную сборку, правила проверки, следующим образом:  
  
-   Если сборка *A* имеет строгое имя сборки *B* также должна иметь строгое имя. Имя дружественной сборки, передаваемое атрибут должен состоять из имени сборки и открытого ключа строгого имени ключа, который используется для подписи сборки *B*.  
  
     Имя дружественной сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут не может быть строгое имя сборки *B*: не включайте версии сборки, языка и региональных параметров, архитектуры или маркера открытого ключа.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
-   Если сборка *A* не имеет строгого имени, имя дружественной сборки должно состоять из имени сборки. Дополнительные сведения см. в разделе [Практическое руководство: создание неподписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).  
  
-   Если сборка *B* имеет строгое имя, необходимо указать ключ строгого имени для сборки *B* с помощью параметра проекта или командной строки `/keyfile` параметр компилятора. Дополнительные сведения см. в разделе [Практическое руководство: Создание подписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).  
  
 <xref:System.Security.Permissions.StrongNameIdentityPermission>Класс также предоставляет возможность совместного использования типов, со следующими отличиями:</xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
-   <xref:System.Security.Permissions.StrongNameIdentityPermission>применяется к отдельному типу, а Дружественная сборка применяется ко всей сборке.</xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
-   Если существуют сотни типы в сборке *A* , вы хотите совместно использовать со сборкой *B*, необходимо добавить <xref:System.Security.Permissions.StrongNameIdentityPermission>для всех приложений.</xref:System.Security.Permissions.StrongNameIdentityPermission> Если используется Дружественная сборка, достаточно один раз объявить дружественные отношения.  
  
-   При использовании <xref:System.Security.Permissions.StrongNameIdentityPermission>, вы хотите поделиться типы должны быть объявлены как открытые.</xref:System.Security.Permissions.StrongNameIdentityPermission> При использовании дружественной сборки общие типы объявляются как `Friend`.  
  
 Сведения о том, как обращаться к сборке `Friend` типы и методы из файла модуля (файл с расширением .netmodule), в разделе [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 <xref:System.Security.Permissions.StrongNameIdentityPermission></xref:System.Security.Permissions.StrongNameIdentityPermission>   
 [Практическое руководство: создание неподписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)   
 [Практическое руководство: Создание подписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)   
 [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)
