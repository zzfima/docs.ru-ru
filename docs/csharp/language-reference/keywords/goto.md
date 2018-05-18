---
title: goto (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: 2dd70a30b885dcdae9637b02e8c34ac39f4879fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="goto-c-reference"></a>goto (Справочник по C#)
Оператор `goto` передает управление программой непосредственно оператору с меткой.  
  
 Оператор `goto` часто используется для передачи управления определенной метке смены регистра или метке по умолчанию в операторе `switch`.  
  
 `goto` Этот оператор также удобно использовать для выхода из глубоко вложенных циклов.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `goto` в операторе [switch](../../../csharp/language-reference/keywords/switch.md).  
  
 [!code-csharp[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование `goto` для выхода из вложенных циклов.  
  
 [!code-csharp[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Оператор goto](/cpp/cpp/goto-statement-cpp)  
 [Операторы перехода](../../../csharp/language-reference/keywords/jump-statements.md)
