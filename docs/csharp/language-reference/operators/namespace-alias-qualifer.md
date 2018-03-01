---
title: "Оператор :: (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6b4f1683e1250ed745e15ced88203ca942c75ff8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a>Оператор :: (Справочник по C#)
Квалификатор псевдонима пространства имен (`::`) служит для поиска идентификаторов. Он всегда размещается между двумя идентификаторами, как показано в следующем примере.  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  
  
## <a name="remarks"></a>Примечания  
 Квалификатор псевдонима пространства имен может быть `global`. Он вызывает поиск в глобальном пространстве имен, а не в пространстве имен с псевдонимом.  
  
## <a name="for-more-information"></a>Дополнительные сведения  
 Пример использования оператора `::` см. в следующем разделе:  
  
-   [Практическое руководство. Использование псевдонима глобального пространства имен](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
 [Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [. Оператор](../../../csharp/language-reference/operators/member-access-operator.md)  
 [Псевдоним extern](../../../csharp/language-reference/keywords/extern-alias.md)
