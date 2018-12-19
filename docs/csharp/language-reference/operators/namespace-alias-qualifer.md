---
title: ':: Оператор. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2e456be075f3487676228244e0119ff46ed9a538
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243482"
---
# <a name="-operator-c-reference"></a>:: Оператор (ссылка C#)
Квалификатор псевдонима пространства имен (`::`) служит для поиска идентификаторов. Он всегда размещается между двумя идентификаторами, как показано в следующем примере.  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  

Оператор `::` также может использоваться с *директивой псевдонима using*:

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a>Примечания  
 Квалификатор псевдонима пространства имен может быть `global`. Он вызывает поиск в глобальном пространстве имен, а не в пространстве имен с псевдонимом.  
  
## <a name="for-more-information"></a>Дополнительные сведения  
 Пример использования оператора `::` см. в следующем разделе:  
  
-   [Практическое руководство. Использование псевдонима глобального пространства имен](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
- [Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [. Оператор](../../../csharp/language-reference/operators/member-access-operator.md)  
- [Псевдоним extern](../../../csharp/language-reference/keywords/extern-alias.md)
