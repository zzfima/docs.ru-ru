---
title: "/highentropyva (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/highentropyva"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/highentropyva compiler option [C#]"
  - "-highentropyva compiler option [C#]"
  - "highentropyva compiler option [C#]"
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
caps.latest.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 8
---
# /highentropyva (C# Compiler Options)
Параметр компилятора **\/highentropyva** сообщает ядру Windows, поддерживает ли указанный исполняемый файл ASLR с высокой энтропией.  
  
## Синтаксис  
  
```  
/highentropyva[+ | -]  
```  
  
## Аргументы  
 `+` &#124; `-`  
 Этот параметр указывает, что 64\-битный исполняемый файл или исполняемый файл, отмечается параметром компилятора [\/platform:anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md), поддерживает виртуальное адресное пространство с высокой энтропией.  Этот параметр отключен по умолчанию.  Используйте **\/highentropyva\+** или **\/highentropyva**, чтобы включить его.  
  
## Заметки  
 Параметр **\/highentropyva** позволяет совместимым версиям ядра Windows использовать более высокие степени энтропии во время смешивания структуры адресного пространства процесса как части ASLR.  Использование более высокие степеней энтропии означает, что большее количество адресов могут быть выделены областям памяти, например стекам и кучам.  В результате сложнее подобрать расположение определенной области памяти.  
  
 Если указан параметр компилятора **\/highentropyva**, то целевой исполняемый файл и все модули, от которых он зависит, должны иметь возможность обработать значения указателя, размер которых превышает 4 гигабайта \(GB\), если они выполняются как 64\-битный процесс.  
  
 Дополнительные сведения о технологии ASLR см. в разделе [Уменьшение уязвимостей программного обеспечения](http://go.microsoft.com/fwlink/?LinkId=226234).