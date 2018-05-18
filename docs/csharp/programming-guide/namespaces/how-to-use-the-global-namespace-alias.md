---
title: Практическое руководство. Использование псевдонима глобального пространства имен (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: 74f51d18ddda1ae4706b78aaf713683d2e505d2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a>Практическое руководство. Использование псевдонима глобального пространства имен (Руководство по программированию на C#)
Возможность доступа к члену в глобальном [пространстве имен](../../../csharp/language-reference/keywords/namespace.md) полезна в тех случаях, когда член может быть скрыт другой сущностью с таким же именем.  
  
 Например, в следующем коде `Console` разрешается в `TestApp.Console` вместо типа `Console` в пространстве имен <xref:System>.  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 При использовании `System.Console` по-прежнему возникает ошибка, поскольку пространство имен `System` скрыто классом `TestApp.System`:  
  
 [!code-csharp[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 Тем не менее эту ошибку можно обойти с помощью `global::System.Console`, как показано ниже:  
  
 [!code-csharp[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 Если левый идентификатор равен `global`, поиск правого идентификатора начинается с глобального пространства имен. Например, следующее объявление ссылается на `TestApp` как на член глобального пространства имен.  
  
 [!code-csharp[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 Очевидно, создавать собственные пространства имен с названием `System` не рекомендуется, и вряд ли вам когда-нибудь попадется код, где это сделано. Тем не менее в крупных проектах существует вполне реальная вероятность того, что названия пространств имен будут в той или иной форме дублироваться. В таких ситуациях вы можете гарантировать использование корневого пространства имен, указав квалификатор пространства имен global.  
  
## <a name="example"></a>Пример  
 В этом примере пространство имен `System` используется для включения класса `TestClass`. Таким образом, следует использовать `global::System.Console` для ссылки на класс `System.Console`, который скрыт пространством имен `System`. Также используется псевдоним `colAlias` для ссылки на пространство имен `System.Collections`. Таким образом, экземпляр <xref:System.Collections.Hashtable?displayProperty=nameWithType> был создан с использованием этого псевдонима вместо пространства имен.  
  
 [!code-csharp[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
 **A 1**  
**B 2**  
**C 3**   
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)  
 [. Оператор](../../../csharp/language-reference/operators/member-access-operator.md)  
 [Оператор ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [extern](../../../csharp/language-reference/keywords/extern.md)
