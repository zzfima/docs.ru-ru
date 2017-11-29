---
title: "Оператор With... End With (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.With
helpviewer_keywords:
- With keyword [Visual Basic]
- loop structures [Visual Basic], and With...End With statements
- execution [Visual Basic], on object
- instructions, repeating
- With...End With statements [Visual Basic]
- With statement [Visual Basic]
- With statement [Visual Basic], nesting
- objects [Visual Basic], accessing
- With block
- End keyword [Visual Basic], With...End With statements
ms.assetid: 340d5fbb-4f43-48ec-a024-80843c137817
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aa1f416e1bfdf6cdb51b098c0e2bd5e9912cb309
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="withend-with-statement-visual-basic"></a>Оператор With... End With (Visual Basic)
Выполняет последовательность операторов, которые многократно ссылаются на единственный объект или структуру, чтобы операторы могли использовать упрощенный синтаксис доступ к членам объекта или структуры.  При использовании структуры можно только считывать значения членов или вызвать методы. При попытке присвоения значений членам структуры, используемым в операторе `With...End With`, возникает ошибка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
With objectExpression  
    [ statements ]  
End With  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`objectExpression`|Обязательный. Выражение, результатом которого является объект. Выражение может быть произвольно сложным и вычисляется только один раз. Результатом выражения могут быть данные любого типа, включая простейшие типы.|  
|`statements`|Необязательно. Один или несколько операторов между `With` и `End With`, которые могут ссылаться на члены объекта, создаваемого при вычислении выражения `objectExpression`.|  
|`End With`|Обязательный. Завершает определение блока `With`.|  
  
## <a name="remarks"></a>Примечания  
 С помощью `With...End With` можно выполнять последовательность операторов с указанным объектом без необходимости многократного указания имени объекта. В блоке операторов `With` члены объекта можно указывать начиная с точки, как если бы перед ней стоял объект оператора `With`.  
  
 Например, чтобы изменить несколько свойств одного объекта, поместите операторы присваивания свойств внутрь блока `With...End With` и укажите объект лишь один раз, а не по одному разу для каждого свойства.  
  
 Если код обращается к одному и тому же объекту в нескольких операторах, оператор `With` обеспечивает следующие преимущества:  
  
-   Не требуется многократно вычислять сложное выражение или присваивать результат временной переменной, чтобы несколько раз сослаться на членов объекта.  
  
-   За счет исключения повторяющихся определяющих выражений код становится более понятным.  
  
 Тип данных у `objectExpression` может быть любым типом класса или структуры или даже простейшим типом Visual Basic (например `Integer`).  При результат вычисления выражения `objectExpression` не является объектом, можно только считывать значения его членов или вызвать методы. При попытке присвоения значений членам структуры, используемым в операторе `With...End With`, возникает ошибка.  Это та же самая ошибка, которая возникает, если сразу после вызова метода, возвращающего структуру, попытаться обратиться к члену результата функции и присвоить ему значение, например `GetAPoint().x = 1`.  Проблема в обоих случаях заключается в том, что структура существует только в стеке вызовов — в таких ситуациях не существует способа записи измененного члена структуры в некоторое расположение таким образом, чтобы весь остальной код программы мог видеть это изменение.  
  
 Выражение `objectExpression` вычисляется один раз при входе в блок. Переназначение выражения `objectExpression` изнутри блока `With` невозможно.  
  
 Внутри блока `With` к методам и свойствам только указанного объекта можно обращаться без их полного описания. Можно использовать методы и свойства других объектов, однако необходимо полностью указывать их имена.  
  
 Оператор `With...End With` можно разместить внутри другого такого оператора. Вложенные операторы `With...End With` могут быть сложны для понимания, если указываемые объекты не очевидны из контекста. Необходимо указывать полную ссылку на объект, находящийся во внешнем блоке `With`, при ссылке на него из внутреннего блока `With`.  
  
 Переходы внутрь блока операторов `With` из другой части программы запрещены.  
  
 Если блок не содержит цикла, операторы выполняются только один раз. Возможно вложение структур управления различных типов. Дополнительные сведения см. в разделе [вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  Ключевое слово `With` можно также использовать в инициализаторах объектов. Дополнительные сведения и примеры см. в разделе [инициализаторы объектов: именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) и [анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
>   
>  Если блок `With` используется исключительно для инициализации свойств или полей только что созданного экземпляра объекта, рекомендуется использовать для этой цели инициализатор объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере в каждом блоке `With` выполняется несколько операторов для одного объекта.  
  
 [!code-vb[VbVbalrWithStatement#2](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/with-end-with-statement_1.vb)]  
  
## <a name="example"></a>Пример  
 В следующем примере показаны вложенные операторы `With…End With`: Во вложенном операторе `With` этот синтаксис относится к внутреннему объекту.  
  
 [!code-vb[VbVbalrWithStatement#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/with-end-with-statement_2.vb)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic.List%601>  
 [Вложенные структуры управления](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
