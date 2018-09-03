---
title: Контекстное ключевое слово global (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: 837245e31a9a795aa2f13cfc6c33fefb6402801d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43401078"
---
# <a name="global-c-reference"></a>global (Справочник по C#)

Контекстное слово `global`, указанное перед [оператором ::](../operators/namespace-alias-qualifer.md), ссылается на глобальное пространство имен, которое используется по умолчанию в любых программах на языке C# и в других случаях не именуется отдельно. Дополнительные сведения см. в разделе [Практическое руководство. Использование псевдонима глобального пространства имен](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).

## <a name="example"></a>Пример

В следующем примере показано, как использовать контекстное ключевое слово `global`, чтобы указать, что класс `TestApp` определен в глобальном пространстве имен:

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a>См. также

- [Пространства имен](../../programming-guide/namespaces/index.md)