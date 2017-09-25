---
title: "params (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- params_CSharpKeyword
- params
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5999911b96d17c710096e74c8f3da65223e778fc
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="params-c-reference"></a>params (справочник по C#)
С помощью ключевого слова `params` можно указать [параметр метода](../../../csharp/language-reference/keywords/method-parameters.md), принимающий переменное число аргументов.  
  
 Можно отправить список аргументов типа, указанного в объявлении параметра, с разделителями-запятыми, или массив аргументов указанного типа. Можно также не отправлять аргументы. Если аргументы не отправляются, длина списка `params` равна нулю.  
  
 В объявлении метода после ключевого слова `params` дополнительные параметры не допускаются, и в объявлении метода допускается только одно ключевое слово `params`.  
  
## <a name="example"></a>Пример  
 В следующем примере показаны различные способы оправки аргументов параметру `params`.  
  
 [!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Параметры методов](../../../csharp/language-reference/keywords/method-parameters.md)

