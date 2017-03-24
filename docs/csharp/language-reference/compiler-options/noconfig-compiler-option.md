---
title: "/noconfig (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/noconfig"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/noconfig compiler option [C#]"
  - "csc.rsp"
  - "-noconfig compiler option [C#]"
  - "noconfig compiler option [C#]"
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# /noconfig (C# Compiler Options)
Параметр **\/noconfig** дает компилятору команду не компилировать с использованием файла csc.rsp, который находится в том же каталоге, что и файл csc.exe и загружается из него.  
  
## Синтаксис  
  
```  
/noconfig  
```  
  
## Заметки  
 Файл csc.rsp ссылается на все сборки, поставляемые с платформой .NET Framework.  Фактические ссылки, которые присутствуют в среде разработки Visual Studio .NET, зависят от типа проекта.  
  
 Можно изменить файл csc.rsp и указать дополнительные параметры компилятора, которые должны быть включены в каждую компиляцию из командной строки с csc.exe \(за исключением параметра **\/noconfig**\).  
  
 Компилятор обрабатывает параметры, которые передаются команде **csc** последними.  Таким образом любой параметр в командной строке переопределяет настройки того же параметра в файле csc.rsp.  
  
 Чтобы компилятор не искал и не использовал параметры в файле csc.rsp, укажите **\/noconfig**.  
  
 Этот параметр компилятора недоступен в среде разработки Visual Studio и не может быть изменен программным способом.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)