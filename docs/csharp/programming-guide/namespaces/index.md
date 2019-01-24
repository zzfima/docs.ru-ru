---
title: 'Руководство по программированию на C#. Пространства имен'
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
  - 'C# language, namespaces'
  - 'namespaces [C#]'
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
---
# <a name="namespaces-c-programming-guide"></a>Пространства имен (Руководство по программированию в C#)

Пространства имен часто используются в программировании на C# двумя способами. Первый способ — платформа .NET Framework использует пространства имен для упорядочения множества ее классов следующим образом:  
  
[!code-csharp[csProgGuide#22](../inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
`System` является пространством имен, а `Console` — это класс в нем. Можно использовать ключевое слово `using`, и тогда полное имя не потребуется. См. следующий пример:  
  
[!code-csharp[csProgGuide#1](../inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
[!code-csharp[csProgGuide#25](../inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
См. дополнительные сведения о [директиве using](../../language-reference/keywords/using-directive.md).  
  
Второй способ — объявление собственных пространств имен поможет вам контролировать область имен классов и методов в более крупных проектах. Используйте ключевое слово [namespace](../../language-reference/keywords/namespace.md), чтобы объявить пространство имен, как показано в следующем примере:  
  
[!code-csharp[csProgGuideNamespaces#6](codesnippet/CSharp/index_4.cs)]

Имя пространства имен должно быть допустимым [именем идентификатора](../inside-a-program/identifier-names.md) C#.

## <a name="namespaces-overview"></a>Обзор пространств имен  

Пространства имен имеют следующие свойства:  
  
- Они помогают упорядочивать проекты с большим объемом кода.  
- Они разделяются оператором `.`.  
- Директива `using` позволяет не указывать название пространства имен для каждого класса.  
- Пространство имен `global` является корневым: `global::System` всегда будет ссылаться на пространство имен <xref:System> в .NET.  

## <a name="c-language-specification"></a>Спецификация языка C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Использование пространств имен](using-namespaces.md)
- [Практическое руководство. Использование псевдонима глобального пространства имен](how-to-use-the-global-namespace-alias.md)
- [Практическое руководство. Использование пространства имен My](how-to-use-the-my-namespace.md)
- [Руководство по программированию на C#](../index.md)
- [Имена идентификаторов](../inside-a-program/identifier-names.md)
- [Ключевые слова, используемые для пространств имен](../../language-reference/keywords/namespace-keywords.md)
- [Директива using](../../language-reference/keywords/using-directive.md)
- [:: Оператор](../../language-reference/operators/namespace-alias-qualifer.md)
- [. Оператор](../../language-reference/operators/member-access-operator.md)
