---
title: Справочник по C#. Модификатор extern
ms.date: 07/20/2015
f1_keywords:
- extern_CSharpKeyword
- extern
helpviewer_keywords:
- DllImport attribute
- extern keyword [C#]
ms.assetid: 9c3f02c4-51b8-4d80-9cb2-f2b6e1ae15c7
ms.openlocfilehash: c121d810e64b5fa27f105f814253c0752e028a95
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713529"
---
# <a name="extern-c-reference"></a>extern (справочник по C#)

Модификатор `extern` используется для объявления метода с внешней реализацией. При применении служб взаимодействия для вызова неуправляемого кода модификатор `extern` обычно используется с атрибутом `DllImport`. В этом случае также необходимо объявить метод как `static` в соответствии со следующим примером:

```csharp
[DllImport("avifil32.dll")]
private static extern void AVIFileInit();
```

Ключевое слово `extern` может также определять внешний псевдоним сборки, который позволяет ссылаться на разные версии одного компонента из одной сборки. Дополнительные сведения см. в разделе [Псевдоним extern](extern-alias.md).

Совместное использование модификаторов [abstract](abstract.md) и `extern` для изменения одного члена недопустимо. Использование модификатора `extern` означает, что метод реализуется вне кода C#, а применение модификатора `abstract` указывает на то, что в данном классе реализация метода не обеспечивается.

В C# ключевое слово extern имеет более ограниченное применение, чем в C++. Сравнительные характеристики использования этого ключевого слова в C# и в C++ см. в разделе "Использование extern для указания компоновки" Справочника по языку C++.

## <a name="example-1"></a>Пример 1

В этом примере программа получает от пользователя строку и отображает ее в окне сообщения. В этой программе используется метод `MessageBox`, импортированный из библиотеки User32.dll.

[!code-csharp[csrefKeywordsModifiers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#8)]

## <a name="example-2"></a>Пример 2

В этом примере показана программа C#, в которой вызывается библиотека C (собственная библиотека DLL).

1. Создайте следующий файл C и назовите его `cmdll.c`.

    ```c
    // cmdll.c
    // Compile with: -LD
    int __declspec(dllexport) SampleMethod(int i)
    {
      return i*10;
    }
    ```

2. Откройте из каталога установки Visual Studio окно командной строки Visual Studio x64 (или x32) Native Tools и скомпилируйте файл `cmdll.c`, введя в командной строке **cl -LD cmdll.c**.

3. В том же каталоге создайте следующий файл C# и назовите его `cm.cs`.

    ```csharp
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

4. Откройте из каталога установки Visual Studio окно командной строки Visual Studio x64 (или x32) Native Tools и скомпилируйте файл `cm.cs`, введя:

    > **csc cm.cs** (для командной строки x64) — или — **csc -platform:x86 cm.cs** (для командной строки x32)

    При этом будет создан исполняемый файл `cm.exe`.

5. Запустите `cm.exe`. Метод `SampleMethod` передает значение 5 в файл DLL, который возвращает значение, умноженное на 10.  Программа выдает следующие результаты.

    ```output
    SampleMethod() returns 50.
    ```

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=nameWithType>
- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](index.md)
- [Модификаторы](index.md)
