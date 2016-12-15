---
title: "/delaysign (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/delaysign"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-delaysign compiler option [C#]"
  - "delaysign compiler option [C#]"
  - "/delaysign compiler option [C#]"
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /delaysign (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При использовании этого параметра компилятор резервирует место в выходном файле, в которое позднее можно поместить цифровую подпись.  
  
## Синтаксис  
  
```  
/delaysign[ + | - ]  
```  
  
## Аргументы  
 `+` &#124; `-`  
 Используйте **\/delaysign\-**, если требуется полностью подписанная сборка.  Если необходимо только поместить открытый ключ в сборку, используйте параметр **\/delaysign\+**.  Значение по умолчанию — **\/delaysign\-**.  
  
## Заметки  
 Параметр **\/delaysign** не учитывается при компиляции, если он не используется с параметром [\/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) или [\/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).  
  
 При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест \(метаданные сборки\) и подписывает хэш закрытым ключом.  Итоговая цифровая подпись хранится в файле, содержащем манифест.  При использовании отложенной подписи компилятор не вычисляет и не сохраняет подпись, а резервирует место в файле для дальнейшего добавления подписи в сборку.  
  
 Например, чтобы поместить сборку в глобальный кэш для тестирования, используйте параметр **\/delaysign\+**.  После тестирования можно полностью подписать сборку, поместив в нее закрытый ключ с помощью [компоновщика сборок](../Topic/Al.exe%20\(Assembly%20Linker\).md).  
  
 Дополнительные сведения см. в разделах [Создание и использование сборок со строгими именами](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) и [Отложенная подпись сборки](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Измените свойство **Только отложенная подпись**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)