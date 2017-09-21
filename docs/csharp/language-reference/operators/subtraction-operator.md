---
title: "- Оператор (ссылка C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- -_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7fabdab8593ff4d721b352b59a45f51721f53eb4
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="--operator-c-reference"></a>Оператор — (справочник по C#)
Оператор `-` может функционировать как унарный или как бинарный оператор.  
  
## <a name="remarks"></a>Примечания  
 Унарные операторы `-` предварительно определены для всех числовых типов. Результатом использования унарного оператора `-` для числового типа является числовое отрицание операнда.  
  
 Бинарные операторы `-`, предопределенные для всех числовых типов и типов перечисления, обеспечивают вычитание второго операнда из первого.  
  
 Для типов делегатов также используется бинарный оператор `-`, который выполняет удаление делегатов.  
  
 Пользовательские типы могут перегружать унарный оператор `-` и бинарный оператор `-`. Дополнительные сведения см. в разделе [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md).  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#40](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)

