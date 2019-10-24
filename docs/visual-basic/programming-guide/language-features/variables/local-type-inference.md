---
title: Вывод локального типа (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: 2b239e17ba7fa0b6a6b08d52f4394541eaa08b28
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775723"
---
# <a name="local-type-inference-visual-basic"></a>Вывод локального типа (Visual Basic)

Компилятор Visual Basic использует *Определение типа* для определения типов данных локальных переменных, объявленных без предложения `As`. Компилятор выводит тип переменной из типа выражения инициализации. Это позволяет объявлять переменные без явного указания типа, как показано в следующем примере. В результате объявления и `num1`, и `num2` строго типизированы как целые числа.

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> Если вы не хотите, чтобы `num2` в предыдущем примере вводились как `Integer`, можно указать другой тип с помощью объявления, например `Dim num3 As Object = 3` или `Dim num4 As Double = 3`.

> [!NOTE]
> Определение типа может использоваться только для нестатических локальных переменных. его нельзя использовать для определения типа полей, свойств или функций класса.

Локальное определение типа применяется на уровне процедуры. Его нельзя использовать для объявления переменных на уровне модуля (внутри класса, структуры, модуля или интерфейса, но не внутри процедуры или блока). Если `num2` в предыдущем примере являлось полем класса, а не локальной переменной в процедуре, это объявление вызовет ошибку с `Option Strict` и классифицирует `num2` как `Object` с `Option Strict` Off. Аналогичным образом, локальное определение типа не применяется к переменным уровня процедуры, объявленным как `Static`.

## <a name="type-inference-vs-late-binding"></a>Определение типа и позднее связывание

Код, использующий вывод типа, напоминает код, основанный на позднем связывании. Однако вывод типа строго вводит переменную вместо того, чтобы покинуть ее как `Object`. Компилятор использует инициализатор переменной для определения типа переменной во время компиляции для создания кода с ранней привязкой. В предыдущем примере `num2`, как `num1`, типизирован как `Integer`.

Поведение переменных с ранней привязкой отличается от поведения переменных с поздним связыванием, для которых тип известен только во время выполнения. Знание типа на раннем этапе позволяет компилятору определить проблемы перед выполнением, выделить память точно и выполнить другие оптимизации. Раннее связывание также включает Visual Basic интегрированную среду разработки (IDE) для предоставления справки IntelliSense об элементах объекта. Раннее связывание также предпочтительно для повышения производительности. Это связано с тем, что все данные, хранящиеся в переменной с поздним связыванием, должны быть упакованы как тип `Object` и доступ к элементам типа во время выполнения замедляет выполнение программы.

## <a name="examples"></a>Примеры

Вывод типа происходит, когда локальная переменная объявлена без предложения `As` и не инициализирована. Компилятор использует тип присвоенного начального значения в качестве типа переменной. Например, каждая из следующих строк кода объявляет переменную типа `String`.

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

В следующем коде показаны два эквивалентных способа создания массива целых чисел.

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

Для определения типа управляющей переменной цикла удобно использовать определение типа. В следующем коде компилятор выводит, что `number` является `Integer`, поскольку `someNumbers2` из предыдущего примера является массивом целых чисел.

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

Определение локального типа можно использовать в инструкциях `Using` для определения типа имени ресурса, как показано в следующем примере.

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

Тип переменной также может выводиться из возвращаемых значений функций, как показано в следующем примере. Как `pList1`, так `pList2` являются массивами процессов, так как `Process.GetProcesses` возвращает массив процессов.

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a>Параметр Infer

`Option Infer` позволяет указать, разрешено ли определение локального типа в конкретном файле. Чтобы включить или заблокировать параметр, введите одну из следующих инструкций в начале файла.

`Option Infer On`

`Option Infer Off`

Если не указать значение для `Option Infer` в коде, компилятор по умолчанию будет `Option Infer On`.

Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.

Дополнительные сведения см. в статьях [выборка инструкций](../../../../visual-basic/language-reference/statements/option-infer-statement.md) и [компиляции в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).

## <a name="see-also"></a>См. также

- [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Оператор For...Next](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [-optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
