---
title: "@ (справочник по C#)"
ms.date: 2017-02-09
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '@_CSharpKeyword'
- '@'
dev_langs:
- CSharp
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 08e3da6aaeee037d7272ea8cddc4382a436b683b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="-c-reference"></a>@ (справочник по C#)

Специальный символ `@` является буквальным идентификатором. Его можно применять в следующих случаях.

1. Чтобы использовать ключевые слова C# в качестве идентификаторов. Символ `@` предшествует элементу кода, который компилятор должен интерпретировать как идентификатор, а не ключевое слово C#. В следующем примере символ `@` используется для определения идентификатора `for`, используемого в цикле `for`.

   [!code-cs[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. Чтобы указать, что строковый литерал следует интерпретировать буквально. Символ `@` в этом экземпляре определяет *буквальный строковый литерал*. Простые escape-последовательности (например, `"\\"` для обратной косой черты), шестнадцатеричные escape-последовательности (например, `"\x0041"` для прописной буквы A) и escape-последовательность Юникода (например, `"\u0041"` для прописной буквы A) интерпретируются буквально. Только escape-последовательность кавычки (`""`) не интерпретируется буквально; она создает одинарную кавычку. В следующем примере определяется два идентичных пути к файлам: один с помощью обычного строкового литерала, а другой — с помощью буквального строкового литерала. Это один из наиболее распространенных способов использования буквальных строковых литералов.

   [!code-cs[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   В следующем примере показан результат определения обычного строкового литерала и буквального строкового литерала, содержащий идентичные последовательности символов.

   [!code-cs[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. Чтобы позволить компилятору различать атрибуты в случае конфликта имен. Атрибут — это тип, производный от @System.Attribute. Имя его типа, как правило, содержит суффикс **Attribute**, несмотря на то, что компилятор не выполняет это соглашение. Затем на атрибут можно ссылаться в коде либо по его полному имени типа (например, `[InfoAttribute]`), либо по сокращенному имени (например, `[Info]`). Однако если два сокращенных имени типов совпадают и одно имя типа содержит суффикс **Attribute**, а другое — нет, возникает конфликт имен. Например, следующий код не может быть скомпилирован, поскольку компилятору не удается определить, какой атрибут — `Info` или `InfoAttribute` — применен к методу `Main`.

   ```csharp
   using System;

   [AttributeUsage(AttributeTargets.Class)]
   public class Info : Attribute
   {
      private string information;
      
      public Info(string info)
      {
          information = info;
      }
   }

   [AttributeUsage(AttributeTargets.Method)]
   public class InfoAttribute : Attribute
   {
      private string information;
      
      public InfoAttribute(string info)
      {
          information = info;
      }
   }

   [Info("A simple executable.")]
   public class Example
   {
      [InfoAttribute("The entry point.")]
      public static void Main()
      {
      }
   }
   ```  

   Если для определения атрибута `Info` используется буквальный идентификатор, код компилируется успешно.

   [!code-cs[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]

## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Специальные символы C#](../../../csharp/language-reference/tokens/index.md)

