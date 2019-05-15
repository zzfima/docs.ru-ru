---
title: Практическое руководство. Руководство по программированию на C#. Использование псевдонима глобального пространства имен
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: 6d3e0740a472f74116712e737e49f86d4202dea5
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452801"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a>Практическое руководство. Руководство по программированию на C#. Использование псевдонима глобального пространства имен
Возможность доступа к члену в глобальном [пространстве имен](../../../csharp/language-reference/keywords/namespace.md) полезна в тех случаях, когда член может быть скрыт другой сущностью с таким же именем.  
  
 Например, в следующем коде `Console` разрешается в `TestApp.Console` вместо типа `Console` в пространстве имен <xref:System>.  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuideNamespaces#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#1)]  
  
 При использовании `System.Console` по-прежнему возникает ошибка, поскольку пространство имен `System` скрыто классом `TestApp.System`:  
  
 [!code-csharp[csProgGuideNamespaces#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#2)]  
  
 Тем не менее эту ошибку можно обойти с помощью `global::System.Console`, как показано ниже:  
  
 [!code-csharp[csProgGuideNamespaces#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#3)]  
  
 Если левый идентификатор равен `global`, поиск правого идентификатора начинается с глобального пространства имен. Например, следующее объявление ссылается на `TestApp` как на член глобального пространства имен.  
  
 [!code-csharp[csProgGuideNamespaces#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#4)]  
  
 Очевидно, создавать собственные пространства имен с названием `System` не рекомендуется, и вряд ли вам когда-нибудь попадется код, где это сделано. Тем не менее в крупных проектах существует вполне реальная вероятность того, что названия пространств имен будут в той или иной форме дублироваться. В таких ситуациях вы можете гарантировать использование корневого пространства имен, указав квалификатор пространства имен global.  
  
## <a name="example"></a>Пример  
 В этом примере пространство имен `System` используется для включения класса `TestClass`. Таким образом, следует использовать `global::System.Console` для ссылки на класс `System.Console`, который скрыт пространством имен `System`. Также используется псевдоним `colAlias` для ссылки на пространство имен `System.Collections`. Таким образом, экземпляр <xref:System.Collections.Hashtable?displayProperty=nameWithType> был создан с использованием этого псевдонима вместо пространства имен.  
  
 [!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]  
  
**A 1**
**B 2**
**C 3**

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)
- [:: Оператор](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)
- [extern](../../../csharp/language-reference/keywords/extern.md)
