---
title: Руководство по программированию на C#. Комментарии к XML-документации
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: c40f8ee189733aa1ae58f8e46c3b7cce005ad9d7
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204734"
---
# <a name="xml-documentation-comments-c-programming-guide"></a>Комментарии к XML-документации (Руководство по программированию на C#)
В Visual C# можно создавать документацию для кода путем включения XML-элементов в специальные поля комментариев (начинающиеся с трех символов косой черты) в исходном коде непосредственно перед блоком кода, к которому относятся комментарии. Например:  
  
```csharp  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 При выполнении компиляции с параметром [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) компилятор осуществляет поиск всех тегов XML в исходном коде и создает XML-файл документации. Для создания окончательной документации на основе сгенерированного компилятором файла можно создать пользовательское средство или применить такие средства, как [DocFX](https://dotnet.github.io/docfx/) или [Sandcastle](https://github.com/EWSoftware/SHFB).  
  
 Для ссылки на XML-элементы (например, если функция обрабатывает определенные XML-элементы, которые требуется включить в комментарии XML-документации) можно использовать стандартный механизм заключения в скобки (`<` и `>`).  Для ссылки на универсальные идентификаторы в элементах ссылок кода (`cref`) можно использовать escape-символы (например, `cref="List&lt;T&gt;"`) или фигурные скобки (`cref="List{T}"`).  В особом случае компилятор анализирует фигурные скобки, как угловые, чтобы при ссылке на универсальные идентификаторы сделать комментарий документации менее громоздким.  
  
> [!NOTE]
>  Комментарии XML-документации не являются метаданными. Они не включаются в скомпилированную сборку, и поэтому не доступны посредством отражения.  
  
## <a name="in-this-section"></a>В этом разделе  
  
-   [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [Обработка XML-файла](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [Разделители для тегов документации](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [Практическое руководство. Использование XML-документации](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a>Связанные разделы  
 Дополнительные сведения:  
  
-   [/doc (обработка комментариев документации)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
