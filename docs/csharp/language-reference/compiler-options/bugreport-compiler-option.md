---
title: "/bugreport (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/bugreport"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/bugreport compiler option [C#]"
  - "-bugreport compiler option [C#]"
  - "bugreport compiler option [C#]"
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# /bugreport (C# Compiler Options)
Указывает, что сведения об отладке следует поместить в файл для последующего анализа.  
  
## Синтаксис  
  
```  
/bugreport:file  
```  
  
## Аргументы  
 `file`  
 Имя файла, который требуется включить в отчет об ошибке.  
  
## Заметки  
 Параметр **\/bugreport** указывает, что в `file` должны содержаться следующие сведения.  
  
-   Копия всех исходных файлов, участвующих в компиляции.  
  
-   Список использованных при компиляции параметров компилятора.  
  
-   Сведения о версии компилятора, времени выполнения и операционной системе.  
  
-   Указанные сборки и модули, сохраненные как шестнадцатеричные цифры, исключая сборки, входящие в комплект поставки платформы .NET Framework и SDK.  
  
-   Скомпилированный код \(при его наличии\).  
  
-   Описание проблемы, которое будет запрошено.  
  
-   Описание предполагаемого способа разрешения проблемы, которое будет запрошено.  
  
 Если этот параметр используется с **\/errorreport:prompt** или **\/errorreport:send**, то сведения в файле будут отправлены в корпорацию Майкрософт.  
  
 Поскольку все файлы исходного кода помещаются в файл `file`, можно попытаться воспроизвести предполагаемую ошибку в максимально короткой программе.  
  
 Этот параметр компилятора недоступен в среде разработки Visual Studio и не может быть изменен программным способом.  
  
 Обратите внимание, что содержимое созданного файла представляет исходный код, который может привести к непреднамеренному разглашению сведений.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [\/errorreport \(Set Error Reporting Behavior\)](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)