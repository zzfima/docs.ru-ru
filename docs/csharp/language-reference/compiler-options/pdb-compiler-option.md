---
title: "/pdb (C# Compiler Options) | Microsoft Docs"
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
  - "/pdb"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-pdb compiler option [C#]"
  - "pdb compiler option [C#]"
  - "/pdb compiler option [C#]"
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /pdb (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Параметр компилятора **\/pdb** указывает имя и расположение файла символов отладки.  
  
## Синтаксис  
  
```  
/pdb:filename  
```  
  
## Аргументы  
 `filename`  
 Имя и расположение файла символов отладки.  
  
## Заметки  
 После указания [\/debug \(Emit Debugging Information\)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) компилятор создаст PDB\-файл в том же каталоге, в котором будут созданы выходной файл \(с расширением EXE или DLL\), с тем же самым именем, что и у выходного файла.  
  
 Параметр **\/pdb** позволяет указать расположение и имя файла с расширением PDB, отличное от заданного по умолчанию.  
  
 Этот параметр не может быть установлен в среде разработки Visual Studio и его нельзя изменить программным способом.  
  
## Пример  
 Скомпилируйте файл `t.cs` и создайте PDB\-файл с именем tt.pdb:  
  
```  
csc /debug /pdb:tt t.cs  
```  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)