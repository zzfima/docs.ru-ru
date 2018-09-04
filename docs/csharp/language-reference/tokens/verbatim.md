---
title: '@ (справочник по C#)'
ms.date: 02/09/2017
f1_keywords:
- '@_CSharpKeyword'
- '@'
helpviewer_keywords:
- '@ special character [C#]'
- '@ language element [C#]'
ms.assetid: 89bc7e53-85f5-478a-866d-1cca003c4e8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7dbab5a743b4f9fed759210e8410cd6e3459efac
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43562235"
---
# <a name="-c-reference"></a>@ (справочник по C#)

Специальный символ `@` является буквальным идентификатором. Его можно применять в следующих случаях.

1. Чтобы использовать ключевые слова C# в качестве идентификаторов. Символ `@` предшествует элементу кода, который компилятор должен интерпретировать как идентификатор, а не ключевое слово C#. В следующем примере символ `@` используется для определения идентификатора `for`, используемого в цикле `for`.

   [!code-csharp[verbatim1](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#1)]

1. Чтобы указать, что строковый литерал следует интерпретировать буквально. Символ `@` в этом экземпляре определяет *буквальный строковый литерал*. Простые escape-последовательности (например, `"\\"` для обратной косой черты), шестнадцатеричные escape-последовательности (например, `"\x0041"` для прописной буквы A) и escape-последовательность Юникода (например, `"\u0041"` для прописной буквы A) интерпретируются буквально. Только escape-последовательность кавычки (`""`) не интерпретируется буквально; она создает одинарную кавычку. Кроме того, в случае [интерполированной строки](interpolated.md) verbatim escape-последовательность фигурной скобки (`{{` и `}}`) интерпретируется буквально; они создают одиночную фигурную скобку. В следующем примере определяется два идентичных пути к файлам: один с помощью обычного строкового литерала, а другой — с помощью буквального строкового литерала. Это один из наиболее распространенных способов использования буквальных строковых литералов.

   [!code-csharp[verbatim2](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#2)]

   В следующем примере показан результат определения обычного строкового литерала и буквального строкового литерала, содержащий идентичные последовательности символов.

   [!code-csharp[verbatim3](../../../../samples/snippets/csharp/language-reference/keywords/verbatim1.cs#3)]

1. Чтобы позволить компилятору различать атрибуты в случае конфликта имен. Атрибут — это тип, производный от <xref:System.Attribute>. Имя его типа, как правило, содержит суффикс **Attribute**, несмотря на то, что компилятор не выполняет это соглашение. Затем на атрибут можно ссылаться в коде либо по его полному имени типа (например, `[InfoAttribute]`), либо по сокращенному имени (например, `[Info]`). Однако если два сокращенных имени типов совпадают и одно имя типа содержит суффикс **Attribute**, а другое — нет, возникает конфликт имен. Например, приведенный ниже код не может быть скомпилирован, так как компилятору не удается определить, какой атрибут — `Info` или `InfoAttribute` — применен к классу `Example`.

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

   [!code-csharp[verbatim4](../../../../samples/snippets/csharp/language-reference/keywords/verbatim4.cs#1)]

## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Специальные символы в C#](../../../csharp/language-reference/tokens/index.md)
