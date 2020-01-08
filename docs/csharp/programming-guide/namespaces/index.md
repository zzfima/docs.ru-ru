---
title: Руководство по программированию на C#. Пространства имен
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 8a03baffc17da07ccab14c89dc9f99be2fc5ba1a
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635214"
---
# <a name="namespaces-c-programming-guide"></a>Пространства имен (Руководство по программированию в C#)

Пространства имен часто используются в программировании на C# двумя способами. Первый способ — платформа .NET Framework использует пространства имен для упорядочения множества ее классов следующим образом:  
  
 [!code-csharp[csProgGuide#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#22)]  
  
`System` является пространством имен, а `Console` — это класс в нем. Можно использовать ключевое слово `using`, и тогда полное имя не потребуется. См. следующий пример:  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuide#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#25)]  
  
См. дополнительные сведения о [директиве using](../../language-reference/keywords/using-directive.md).  
  
Второй способ — объявление собственных пространств имен поможет вам контролировать область имен классов и методов в более крупных проектах. Используйте ключевое слово [namespace](../../language-reference/keywords/namespace.md), чтобы объявить пространство имен, как показано в следующем примере:  
  
 [!code-csharp[csProgGuideNamespaces#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#6)]

Имя пространства имен должно быть допустимым [именем идентификатора](../inside-a-program/identifier-names.md) C#.

## <a name="namespaces-overview"></a>Обзор пространств имен  

Пространства имен имеют следующие свойства:  
  
- Они помогают упорядочивать проекты с большим объемом кода.  
- Они разделяются оператором `.`.  
- Директива `using` позволяет не указывать название пространства имен для каждого класса.  
- Пространство имен `global` является корневым: `global::System` всегда будет ссылаться на пространство имен <xref:System> в .NET.  

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в статье [Пространства имен](~/_csharplang/spec/namespaces.md) в разделе [Предварительная спецификация C# 6.0](~/_csharplang/spec/introduction.md).
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Использование пространств имен](using-namespaces.md)
- [Практическое руководство. Использование пространства имен My](how-to-use-the-my-namespace.md)
- [Имена идентификаторов](../inside-a-program/identifier-names.md)
- [Директива using](../../language-reference/keywords/using-directive.md)
- [:: Оператор](../../language-reference/operators/namespace-alias-qualifier.md)
