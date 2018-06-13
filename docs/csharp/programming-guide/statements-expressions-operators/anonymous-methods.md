---
title: Анонимные методы (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous methods [C#]
- methods [C#], anonymous
- delegates [C#], anonymous methods
ms.assetid: a62441fa-f0a3-4acb-9aa6-93762a635275
ms.openlocfilehash: 7f6c596dcc73cdfb335071f57aab18e836ceaae8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338426"
---
# <a name="anonymous-methods-c-programming-guide"></a>Анонимные методы (Руководство по программированию в C#)
В версиях языка C# до 2.0 объявить [делегат](../../../csharp/language-reference/keywords/delegate.md) можно было только с помощью [именованных методов](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md). В версии C# 2.0 были представлены анонимные методы, в версии C# 3.0 и более поздних замененные лямбда-выражениями, которые теперь рекомендуется использовать для написания встроенного кода. Тем не менее сведения об анонимных методах из этого раздела также относятся и к лямбда-выражениям. В одном случае анонимные методы реализуют функциональные возможности, недоступные при использовании лямбда-выражений. При использовании анонимных методов можно опустить список параметров. Это значит, что анонимный метод может быть преобразован в делегаты с различными сигнатурами. При работе с лямбда-выражениями это невозможно. Дополнительные сведения о лямбда-выражениях см. в разделе [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Создавая анонимные методы, вы фактически передаете блок кода в качестве параметра делегата. Вот два примера.  
  
 [!code-csharp[csProgGuideDelegates#6](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_1.cs)]  
  
 [!code-csharp[csProgGuideDelegates#5](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_2.cs)]  
  
 Использование анонимных методов позволяет сократить время на написание кода для создания экземпляров делегатов, поскольку в этом случае не требуется создавать отдельный метод.  
  
 Например, можно указать блок кода вместо делегата в том случае, когда создание отдельного метода выглядит излишним. В качестве примера можно привести создание нового потока. Этот класс создает поток и также может содержать код, который выполняется потоком, причем для этого не требуется добавлять дополнительный метод делегата.  
  
 [!code-csharp[csProgGuideDelegates#7](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_3.cs)]  
  
## <a name="remarks"></a>Примечания  
 Областью действия параметров анонимного метода является *блок анонимного метода*.  
  
 Использование инструкций перехода, таких как [goto](../../../csharp/language-reference/keywords/goto.md), [break](../../../csharp/language-reference/keywords/break.md) или [continue](../../../csharp/language-reference/keywords/continue.md), внутри блока анонимного метода является ошибкой в том случае, если цель перехода располагается за пределами блока. Также ошибкой будет использование инструкции перехода, такой как `goto`, `break` или `continue`, вне блока анонимного метода, если цель перехода располагается внутри этого блока.  
  
 Локальные переменные и параметры, область действия которых включает объявление анонимного метода, называются *внешними* переменными анонимного метода. Например, в следующем фрагменте кода `n` является внешней переменной:  
  
 [!code-csharp[csProgGuideDelegates#8](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_4.cs)]  
  
 Ссылка на внешнюю переменную `n` при создании делегата считается *захваченной*. В отличие от локальных переменных, время существования захваченной переменной длится до тех пор, пока делегаты, ссылающиеся на анонимные методы, могут участвовать в сборке мусора.  
  
 Анонимный метод не может обратиться к параметрам [in](../../../csharp/language-reference/keywords/in.md), [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) во внешней области действия.  
  
 Также невозможен доступ к небезопасному коду из *блока анонимного метода*.  
  
 Анонимные методы нельзя использовать в левой части оператора [is](../../../csharp/language-reference/keywords/is.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показаны два способа создания экземпляра делегата:  
  
-   Связывание делегата с анонимным методом.  
  
-   Связывание делегата с именованным методом (`DoWork`).  
  
 В обоих случаях при вызове делегата отображается сообщение.  
  
 [!code-csharp[csProgGuideDelegates#4](../../../csharp/programming-guide/delegates/codesnippet/CSharp/anonymous-methods_5.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)  
 [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [Делегаты с именованными методами и делегаты с анонимными методами](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)
