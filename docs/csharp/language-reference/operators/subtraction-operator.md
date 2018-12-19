---
title: '- Оператор. Справочник по C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 5a467e8383d7510260ad3044976601deca7cafdb
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242234"
---
# <a name="--operator-c-reference"></a>Оператор — (справочник по C#)
Оператор `-` может функционировать как унарный или как бинарный оператор.  
  
## <a name="remarks"></a>Примечания  
 Унарные операторы `-` предварительно определены для всех числовых типов. Результатом использования унарного оператора `-` для числового типа является числовое отрицание операнда.  
  
 Бинарные операторы `-`, предопределенные для всех числовых типов и типов перечисления, обеспечивают вычитание второго операнда из первого.  
  
 Для типов делегатов также используется бинарный оператор `-`, который выполняет удаление делегатов.  
  
 Пользовательские типы могут перегружать унарный оператор `-` и бинарный оператор `-`. Дополнительные сведения см. в разделе [operator (справочник по C#)](../../../csharp/language-reference/keywords/operator.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#40](../../../csharp/language-reference/operators/codesnippet/CSharp/subtraction-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
