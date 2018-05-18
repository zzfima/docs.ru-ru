---
title: -moduleassemblyname (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
ms.openlocfilehash: 2c6467434b56d624c42aaf54219959228e068ffa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-moduleassemblyname-c-compiler-option"></a>-moduleassemblyname (параметры компилятора C#)
Указывает сборку, к неоткрытым типам которой может обращаться .netmodule.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Аргументы  
 `assembly_name`  
 Имя сборки, к неоткрытым типам которой может обращаться .netmodule.  
  
## <a name="remarks"></a>Примечания  
 Параметр **-moduleassemblyname** нужно использовать при сборке модуля NETMODULE и выполнении следующий условий:  
  
-   .netmodule требуется доступ к неоткрытым типам в существующей сборке.  
  
-   Известно имя сборки, в которой будет создан .netmodule.  
  
-   Существующая сборка предоставила дружественной сборке доступ к сборке, в которую будет встроен .netmodule.  
  
 Дополнительные сведения о сборке NETMODULE см. в разделе [-target:module (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).  
  
 Дополнительные сведения см. в разделе [Дружественные сборки](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).  
  
 Этот параметр недоступен в среде разработки и может использоваться только при компиляции из командной строки.  
  
 Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.  
  
## <a name="example"></a>Пример  
 В этом примере выполняется построение сборки частного типа, которой предоставляется дружественный доступ к сборке csman_an_assembly.  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: -target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class   
{  
    public void Test()   
    {   
        Console.WriteLine("An_Internal_Class.Test called");   
    }  
}  
```  
  
## <a name="example"></a>Пример  
 Этот пример строит .netmodule, который обращается к неоткрытому типу в сборке moduleassemblyname_1.dll. Мы знаем, что модуль NETMODULE будет встроен в сборку csman_an_assembly, поэтому можем задать **-moduleassemblyname**, чтобы позволить NETMODULE обращаться к неоткрытым типам в сборке, которой предоставлен доступ к дружественной сборке csman_an_assembly.  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: -moduleassemblyname:csman_an_assembly -target:module -reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере кода выполнено построение сборки csman_an_assembly со ссылками на ранее построенную сборку и .netmodule.  
  
```csharp  
// csman_an_assembly.cs  
// compile with: -addmodule:moduleassemblyname_2.netmodule -reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
 **Вызывается An_Internal_Class.Test**  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)
