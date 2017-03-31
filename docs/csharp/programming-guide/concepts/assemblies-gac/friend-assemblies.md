---
title: "Дружественные сборки (C#) | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ca01b9e91de08f3bdf53cd0572a3e1d1af0cf0af
ms.lasthandoff: 03/13/2017

---
# <a name="friend-assemblies-c"></a>Дружественные сборки (C#)
*Дружественная сборка* — это сборка, которая может обращаться к [внутренним](../../../../csharp/language-reference/keywords/internal.md) типам и членам другой сборки. Если сборка определяется как дружественная, помечать типы и члены как открытые для того, чтобы другие сборки могли получить к ним доступ, больше не требуется. Это особенно удобно в следующих ситуациях:  
  
-   Во время модульного теста, если тестовый код выполняется в отдельной сборке, но требует доступа к членам тестируемой сборки, помеченным как `internal`.  
  
-   При разработке библиотек классов, если дополнения к этой библиотеке содержатся в отдельных сборках, но требуют доступа к членам в существующих сборках, помеченным как `internal`.  
  
## <a name="remarks"></a>Примечания  
 Для обозначения одной или нескольких сборок как дружественных для заданной сборки можно использовать атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. В следующем примере атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется в сборке А и обозначает сборку `AssemblyB` как дружественную. В результате сборка `AssemblyB` получает доступ ко всем типам и членам в сборке А, помеченным как `internal`.  
  
> [!NOTE]
>  При компиляции сборки (сборки `AssemblyB`), которая будет обращаться ко внутренним типам или членам другой сборки (сборки *А*), необходимо прямо указать имя выходного файла (EXE или DLL), используя параметр компилятора **/out**. Это необходимо потому, что компилятор еще не создал имя сборки, формируемой во время привязки к внешним ссылкам. Дополнительные сведения см. в разделе [/out (C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).  
  
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
  
 Доступ к типам и членам `internal` могут получить только те сборки, которые будут прямо обозначены как дружественные. Например, если сборка B является дружественной для сборки A, а сборка C ссылается на сборку B, сборка C не получает доступ к типам `internal` в A.  
  
 Компилятор выполняет определенную базовую проверку имени дружественной сборки, которое передается в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Если сборка *A* объявляет *B* как дружественную сборку, действуют следующие правила проверки:  
  
-   Если сборка *A* имеет строгое имя, сборка *B* должна также иметь строгое имя. Имя дружественной сборки, передаваемое в атрибут, должно состоять из имени сборки и открытого ключа из ключа строгого имени, который используется для подписи сборки *B*.  
  
     Имя дружественной сборки, передаваемое в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, не может быть строгим именем сборки *B*, поэтому включать в него версию сборки, язык и региональные параметры, архитектуру или маркер открытого ключа не следует.  
  
-   Если сборка *A* не имеет строгого имени, имя дружественной сборки должно состоять только из имени сборки. Дополнительные сведения см. в разделе [Практическое руководство. Создание неподписанных дружественных сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).  
  
-   Если сборка *B* имеет строгое имя, необходимо указать ключ строгого имени для сборки *B*, используя параметр проекта или параметр компилятора командной строки `/keyfile`. Дополнительные сведения см. в разделе [Практическое руководство. Создание подписанных дружественных сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).  
  
 Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> позволяет также совместно использовать типы, но со следующими отличиями:  
  
-   <xref:System.Security.Permissions.StrongNameIdentityPermission> применяется к отдельному типу, в то время как дружественная сборка применяется ко всей сборке.  
  
-   Если в сборке *A* существуют сотни типов, которые должны использоваться совместно со сборкой *B*, к каждому из них необходимо добавить <xref:System.Security.Permissions.StrongNameIdentityPermission>. Если используется дружественная сборка, достаточно объявить дружественные отношения всего один раз.  
  
-   При использовании <xref:System.Security.Permissions.StrongNameIdentityPermission> типы, к которым планируется предоставить общий доступ, должны быть объявлены открытыми. При использовании дружественной сборки общие типы объявляются как `internal`.  
  
 Сведения о том, как получить доступ к типам и методам сборки `internal` из файла модуля (файла с расширением NETMODULE), см. в разделе [/moduleassemblyname (C#)](../../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 <xref:System.Security.Permissions.StrongNameIdentityPermission>   
 [Практическое руководство. Создание неподписанных дружественных сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)   
 [Практическое руководство. Создание подписанных дружественных сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)   
 [Сборки и глобальный кэш сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)   
 [Руководство по программированию на C#](../../../../csharp/programming-guide/index.md)
