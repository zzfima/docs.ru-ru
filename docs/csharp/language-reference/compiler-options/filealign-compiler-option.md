---
title: "/filealign (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/filealign"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/alignment compiler option [C#]"
  - "filealign compiler option [C#]"
  - "-filealign compiler option [C#]"
  - "/sections compiler option [C#]"
  - "alignment compiler option [C#]"
  - "sections compiler option [C#]"
  - "-sections compiler option [C#]"
  - "/filealign compiler option [C#]"
  - "file sharing [C#]"
  - "-alignment compiler option [C#]"
  - "section alignment [C#]"
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# /filealign (C# Compiler Options)
Параметр **\/filealign** позволяет задать размер разделов выходного файла.  
  
## Синтаксис  
  
```  
/filealign:number  
```  
  
## Аргументы  
 `number`  
 Значение, определяющее размер разделов выходного файла.  Допустимые значения: 512, 1024, 2048, 4096 и 8192.  Эти значения задаются в байтах.  
  
## Заметки  
 Каждый раздел выравнивается по границе, кратной значению **\/filealign**.  Фиксированного значения по умолчанию нет.  Если параметр **\/filealign** не указан, среда CLR выбирает значение по умолчанию во время компиляции.  
  
 Путем определения размера раздела можно повлиять на размер выходного файла.  Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.  
  
 Для просмотра информации о разделах выходного файла воспользуйтесь служебной программой [DUMPBIN](/visual-cpp/build/reference/dumpbin-options).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Выберите страницу свойств **Построение**.  
  
3.  Нажмите кнопку **Дополнительно**.  
  
4.  Измените свойство **Выравнивание файлов**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.  
  
## См. также  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/ru-ru/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)