---
title: "/moduleassemblyname (C# Compiler Option) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/moduleassemblyname"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "moduleassemblyname compiler option [C#]"
  - "/moduleassemblyname compiler option [C#]"
  - ".moduleassemblyname compiler option [C#]"
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /moduleassemblyname (C# Compiler Option)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Задает сборку, к неоткрытым типам которой может получить доступ netmodule.  
  
## Синтаксис  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## Аргументы  
 `assembly_name`  
 Имя сборки, к чьим неоткрытым типам может обращаться файл с расширением .netmodule.  
  
## Заметки  
 **\/moduleassemblyname** должен использоваться при построении файла .netmodule и, когда выполняются следующие условия:  
  
-   Для файла .netmodule требуется доступ к неоткрытым типам в существующей сборке.  
  
-   Известно имя сборки, в которой будет создан .netmodule.  
  
-   Существующая сборка предоставила дружественной сборке доступ к сборке, в которую будет встроен .netmodule.  
  
 Дополнительные сведения о построении .netmodule содержатся в [\/target:module \(Create Module to Add to Assembly\)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).  
  
 Дополнительные сведения о дружественных сборках см. в разделе [Дружественные сборки](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Этот параметр недоступен из среды разработки; он доступен только при компиляции из командной строки.  
  
 Этот параметр компилятора недоступен в среде разработки Visual Studio и не может быть изменен программным способом.  
  
## Пример  
 Следующий пример выполняет построение сборки с закрытым типом и предоставляем дружественной сборке доступ к сборке с именем csman\_an\_assembly.  
  
```  
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
  
## Пример  
 Этот пример строит .netmodule, который обращается к неоткрытому типу в сборке moduleassemblyname\_1.dll.  Узнав, что этот .netmodule будет встроен в сборку под названием csman\_an\_assembly, можно указать **\/moduleassemblyname**, позволяя .netmodule обращаться к неоткрытым типам в сборке, которой предоставлен доступ к дружественной сборке csman\_an\_assembly.  
  
```  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## Пример  
 Следующий код выполняет построение сборки csman\_an\_assembly, ссылаясь на ранее построенную сборку и .netmodule.  
  
```  
// csman_an_assembly.cs  
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
  **An\_Internal\_Class.Test под названием**   
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)