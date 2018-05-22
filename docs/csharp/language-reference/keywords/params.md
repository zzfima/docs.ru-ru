---
title: params (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: d7e0094d0f60aa201ae7229983f3e4b9764d2cbc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="params-c-reference"></a>params (справочник по C#)
С помощью ключевого слова `params` можно указать [параметр метода](../../../csharp/language-reference/keywords/method-parameters.md), принимающий переменное число аргументов.  
  
 Можно отправить список аргументов типа, указанного в объявлении параметра, с разделителями-запятыми, или массив аргументов указанного типа. Можно также не отправлять аргументы. Если аргументы не отправляются, длина списка `params` равна нулю.  
  
 В объявлении метода после ключевого слова `params` дополнительные параметры не допускаются, и в объявлении метода допускается только одно ключевое слово `params`.  
  
## <a name="example"></a>Пример  
 В следующем примере показаны различные способы оправки аргументов параметру `params`.  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Параметры методов](../../../csharp/language-reference/keywords/method-parameters.md)
