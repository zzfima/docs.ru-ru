---
title: "-moduleassemblyname (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /moduleassemblyname
dev_langs:
- CSharp
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2522609aa41ad944b37a8882c1cc56cd5967b330
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="moduleassemblyname-c-compiler-option"></a>/moduleassemblyname (параметры компилятора C#)
Указывает сборку, к неоткрытым типам которой может обращаться .netmodule.  
  
## <a name="syntax"></a>Синтаксис  
  
```console  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Аргументы  
 `assembly_name`  
 Имя сборки, к неоткрытым типам которой может обращаться .netmodule.  
  
## <a name="remarks"></a>Примечания  
 Параметр **/moduleassemblyname** должен использоваться при построении .netmodule и выполнении следующий условий:  
  
-   .netmodule требуется доступ к неоткрытым типам в существующей сборке.  
  
-   Известно имя сборки, в которой будет создан .netmodule.  
  
-   Существующая сборка предоставила дружественной сборке доступ к сборке, в которую будет встроен .netmodule.  
  
 Дополнительные сведения о построении файлов .netmodule см. в разделе [/target:module (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).  
  
 Дополнительные сведения см. в разделе [Дружественные сборки](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).  
  
 Этот параметр недоступен в среде разработки и может использоваться только при компиляции из командной строки.  
  
 Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.  
  
## <a name="example"></a>Пример  
 В этом примере выполняется построение сборки частного типа, которой предоставляется дружественный доступ к сборке csman_an_assembly.  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: /target:library  
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
 Этот пример строит .netmodule, который обращается к неоткрытому типу в сборке moduleassemblyname_1.dll. Мы знаем, что .netmodule будет встроен в сборку csman_an_assembly, поэтому можем задать **/moduleassemblyname**, чтобы позволить .netmodule обращаться к неоткрытым типам в сборке, которой предоставлен доступ к дружественной сборке csman_an_assembly.  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
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
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
 **Вызывается An_Internal_Class.Test**   
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

