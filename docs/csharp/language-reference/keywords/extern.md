---
title: "extern (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- extern_CSharpKeyword
- extern
dev_langs:
- CSharp
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
caps.latest.revision: 26
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 61cde8c8f6b3d255be5f6040141542e3e8d1e8c7
ms.lasthandoff: 03/13/2017

---
# <a name="extern-c-reference"></a>extern (справочник по C#)
Модификатор `extern` используется для объявления метода с внешней реализацией. При применении служб взаимодействия для вызова неуправляемого кода модификатор `extern` обычно используется с атрибутом `DllImport`. В этом случае также необходимо объявить метод как `static` в соответствии со следующим примером:  
  
```  
[DllImport("avifil32.dll")]  
private static extern void AVIFileInit();  
```  
  
 Ключевое слово `extern` может также определять внешний псевдоним сборки, который позволяет ссылаться на разные версии одного компонента из одной сборки. Дополнительные сведения см. в разделе [Псевдоним extern](../../../csharp/language-reference/keywords/extern-alias.md).  
  
 Совместное использование модификаторов [abstract](../../../csharp/language-reference/keywords/abstract.md) и `extern` для изменения одного члена недопустимо. Использование модификатора `extern` означает, что метод реализуется вне кода C#, а применение модификатора `abstract` указывает на то, что в данном классе реализация метода не обеспечивается.  
  
 В C# ключевое слово extern имеет более ограниченное применение, чем в C++. Сравнительные характеристики использования этого ключевого слова в C# и в C++ см. в разделе "Использование extern для указания компоновки" Справочника по языку C++.  
  
## <a name="example"></a>Пример  
 **Пример 1.** В этом примере программа получает от пользователя строку и отображает ее в окне сообщения. В этой программе используется метод `MessageBox`, импортированный из библиотеки User32.dll.  
  
 [!code-cs[csrefKeywordsModifiers#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/extern_1.cs)]  
  
## <a name="example"></a>Пример  
 **Пример 2.** В этом примере показана программа C#, в которой вызывается библиотека C (собственная библиотека DLL).  
  
 1. Создайте следующий файл C и назовите его `cmdll.c`.  
  
```  
// cmdll.c  
// Compile with: /LD  
int __declspec(dllexport) SampleMethod(int i)  
{  
   return i*10;  
}  
```  
  
## <a name="example"></a>Пример  
 2. Откройте из каталога установки Visual Studio окно командной строки Visual Studio x64 (или x32) Native Tools и скомпилируйте файл `cmdll.c`, введя в командной строке **cl /LD cmdll.c**.  
  
 3. В том же каталоге создайте следующий файл C# и назовите его `cm.cs`.  
  
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
  
## <a name="example"></a>Пример  
 3. Откройте из каталога установки Visual Studio окно командной строки Visual Studio x64 (или x32) Native Tools и скомпилируйте файл `cm.cs`, введя:  
  
> **csc cm.cs** (для командной строки x64)   
>  —или—  
> **csc /platform:x86 cm.cs** (для командной строки x32)  
  
 При этом будет создан исполняемый файл `cm.exe`.  
  
 4. Запустите `cm.exe`. Метод `SampleMethod` передает значение 5 в файл DLL, который возвращает значение, умноженное на 10.  Программа выдает следующие результаты.  
  
```  
SampleMethod() returns 50.  
```  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)
