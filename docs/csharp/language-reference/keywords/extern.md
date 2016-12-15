---
title: "extern (справочник по C#) | Microsoft Docs"
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
  - "extern_CSharpKeyword"
  - "extern"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "DllImport - атрибут"
  - "extern - ключевое слово [C#]"
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# extern (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Модификатор `extern` используется для объявления метода с внешней реализацией.  При применении служб взаимодействия для вызова неуправляемого кода модификатор `extern` обычно используется с атрибутом `DllImport`.  В этом случае также необходимо объявить метод как `static` в соответствии со следующим примером:  
  
```  
[DllImport("avifil32.dll")]  
private static extern void AVIFileInit();  
```  
  
 Ключевое слово `extern` может также определять внешний псевдоним сборки, который позволяет ссылаться на разные версии одного компонента из одной сборки.  Дополнительные сведения см. в разделе [Псевдоним extern](../../../csharp/language-reference/keywords/extern-alias.md).  
  
 Совместное использование модификаторов [abstract](../../../csharp/language-reference/keywords/abstract.md) и `extern` для изменения одного члена недопустимо.  Использование модификатора `extern` означает, что метод реализуется вне кода C\#, а применение модификатора `abstract` указывает на то, что в данном классе реализация метода не обеспечивается.  
  
 В C\# ключевое слово extern имеет более ограниченное применение, чем в C\+\+.  Сравнительные характеристики использования этого ключевого слова в C\# и в C\+\+ см. в разделе "Использование extern для указания компоновки" Справочника по языку C\+\+.  
  
## Пример  
 **Пример 1.** В этом примере программа получает от пользователя строку и отображает ее в окне сообщения.  В этой программе используется метод `MessageBox`, импортированный из библиотеки User32.dll.  
  
 [!code-cs[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]  
  
## Пример  
 **Пример 2.** В этом примере показана программа C\#, в которой вызывается библиотека C \(собственная библиотека DLL\).  
  
 1.  Создайте следующий файл C и назовите его `cmdll.c`.  
  
```  
// cmdll.c  
// Compile with: /LD  
int __declspec(dllexport) SampleMethod(int i)  
{  
   return i*10;  
}  
```  
  
## Пример  
 2.  Откройте из каталога установки Visual Studio окно командной строки Visual Studio x64 \(или x32\) Native Tools и скомпилируйте файл `cmdll.c`, введя в командной строке **cl \/LD cmdll.c**.  
  
 3.  В том же каталоге создайте следующий файл C\# и назовите его `cm.cs`.  
  
```  
// cm.cs  
using System;  
using System.Runtime.InteropServices;  
public class MainClass   
{  
   [DllImport("Cmdll.dll")]  
   public static extern int SampleMethod(int x);  
  
   static void Main()   
   {  
      Console.WriteLine("SampleMethod() returns {0}.", SampleMethod(5));  
   }  
}  
```  
  
## Пример  
 3.  Откройте из каталога установки Visual Studio окно командной строки Visual Studio x64 \(или x32\) Native Tools и скомпилируйте файл `cm.cs`, введя:  
  
> **csc cm.cs** \(для командной строки x64\)   
>  —или—  
> **csc \/platform:x86 cm.cs** \(для командной строки x32\)  
  
 При этом будет создан исполняемый файл `cm.exe`.  
  
 4.  Запустите `cm.exe`.  Метод `SampleMethod` передает значение 5 в файл DLL, который возвращает значение, умноженное на 10. Программа выдает следующий результат:  
  
```  
SampleMethod() returns 50.  
```  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)