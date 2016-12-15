---
title: "Не удается выпустить сборку: &lt;сообщениеОбОшибке&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30145"
  - "bc30145"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30145"
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Не удается выпустить сборку: &lt;сообщениеОбОшибке&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] вызывает компоновщик сборок \(Al.exe, который также называется Alink\) для создания сборки с манифестом, при этом компоновщик сообщает об ошибке на этапе предварительного выпуска процедуры создания сборки.  
  
 **Идентификатор ошибки:** BC30145  
  
### Исправление ошибки  
  
1.  Изучите приведенное сообщение об ошибке и обратитесь к разделу [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/ru-ru/7f125d49-0a03-47a6-9ba9-d61a679a7d4b), содержащему дополнительные пояснения и рекомендации.  
  
2.  Попробуйте подписать сборку вручную, используя [Al.exe \(компоновщик сборок\)](../Topic/Al.exe%20\(Assembly%20Linker\).md) или [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md).  
  
3.  Если ошибка не устранена, соберите сведения об условиях ее возникновения и уведомите службу технической поддержки Майкрософт.  
  
### Подпись сборки вручную  
  
1.  Воспользуйтесь [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md), чтобы создать файл пары открытого и закрытого ключей.  
  
     Этот файл имеет расширение .SNK.  
  
2.  Удалите из проекта ссылку COM, вызывающую ошибку.  
  
3.  В меню **Пуск** Windows последовательно выберите **Программы**, **Microsoft Visual Studio 2008**, **Инструменты Visual Studio**, после чего выберите пункт **Командная строка Visual Studio 2008**.  
  
4.  Перейдите в каталог, куда хотите поместить программу\-оболочку сборки.  
  
5.  Введите следующий код.  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     Ниже приведен пример кода, который вы можете ввести.  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     Используйте двойные кавычки \("\), если путь или файл содержат пробелы.  
  
6.  В [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] добавьте в созданный файл ссылку на сборку .NET.  
  
## См. также  
 [Al.exe \(компоновщик сборок\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/ru-ru/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)   
 [Практическое руководство. Создание пары открытого и закрытого ключей](../Topic/How%20to:%20Create%20a%20Public-Private%20Key%20Pair.md)   
 [Обращайтесь к нам](/visual-studio/ide/talk-to-us)