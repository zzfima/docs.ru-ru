---
title: Практическое руководство. Руководство по программированию на C#. Использование псевдонима глобального пространства имен
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: b163981d3cf6d56ab953757931b0b386a47263ff
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796288"
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
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)
- [:: Оператор](../../../csharp/language-reference/operators/namespace-alias-qualifier.md)
- [extern](../../../csharp/language-reference/keywords/extern.md)
