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
ms.openlocfilehash: f4edc879af9539a40269336bed97fe206920992a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706752"
---
# <a name="local-type-inference-visual-basic"></a>Вывод локального типа (Visual Basic)
Компилятор Visual Basic использует *вывод типа* для определения типов данных локальных переменных, объявленных без `As` предложение. Компилятор выводит тип переменной из типа выражения инициализации. Это позволяет объявлять переменные без явного указания типа, как показано в следующем примере. В результате объявлений оба `num1` и `num2` являются строго типизированными как целые числа.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]  
 
> [!NOTE]
>  Если вы не хотите `num2` в предыдущем примере была введена как `Integer`, можно указать другой тип, используя объявление, подобное `Dim num3 As Object = 3` или `Dim num4 As Double = 3`.  

> [!NOTE]
>  Определение типа может использоваться только для нестатических локальных переменных; он не может использоваться для определения типа поля класса, свойства или функции.
 
 Вывод локального типа применяется на уровне процедуры. Он не может использоваться для объявления переменных на уровне модуля (в пределах класса, структуры, модуля или интерфейса, но не внутри процедуры или блока). Если `num2` в предыдущем примере были полем класса, а не локальную переменную в процедуре, объявление приведет к ошибке с `Option Strict` и было бы классифицировать `num2` как `Object` с `Option Strict` off. Аналогичным образом, вывод локального типа не применяется к процедуре уровня переменные, объявленные как `Static`.  
  
## <a name="type-inference-vs-late-binding"></a>Определение типа или. Позднее связывание  
 Код, который использует выведение типа напоминает код, который полагается на динамическое связывание. Тем не менее, выведение типа строго типизирует переменной не оставляйте его как `Object`. Компилятор использует инициализатор переменной для определения типа переменной во время компиляции для создания кода с ранним связыванием. В предыдущем примере `num2`, например `num1`, типизируется как `Integer`.  
  
 Поведение переменных с ранним связыванием отличается от переменных с поздним связыванием, для которых тип известен только во время выполнения. Знание типа заранее позволяет компилятору определить проблемы до выполнения, точно выделить память и выполнять другие виды оптимизации. Раннее связывание позволяет Visual Basic интегрированной среде разработки (IDE) для предоставления IntelliSense справки о членах класса объекта. Раннее связывание также является предпочтительным для производительности. Это обусловлено тем, все данные, хранящиеся в переменной с поздним связыванием, которые должны быть упакованы как тип `Object`, и доступ к членам типа во время выполнения делает программу медленнее.  
  
## <a name="examples"></a>Примеры  
 Вывод типа происходит, когда локальная переменная объявлена без `As` предложение и инициализируется. Компилятор использует тип присвоенного начального значения как тип переменной. Например, каждый из следующих строк кода объявляется переменная типа `String`.  
  
 [!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]  
  
 В следующем коде показано два равнозначных способа создать массив целых чисел.  
  
 [!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]  
  
 Удобно использовать определение типа для определения типа переменной цикла. В следующем коде, компилятор выводит, что `number` — `Integer` поскольку `someNumbers2` из предыдущего примера представляет собой массив целых чисел.  
  
 [!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]  
  
 Вывод локального типа могут использоваться в `Using` инструкции, чтобы установить тип имени ресурса, как показано в следующем примере.  
  
 [!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]  
  
 Также удается определить тип переменной из возвращаемого значения функции, как показано в следующем примере. Оба `pList1` и `pList2` представляют собой массивы процессов, так как `Process.GetProcesses` возвращает массив из процессов.  
  
 [!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]  
  
## <a name="option-infer"></a>Option Infer  
 `Option Infer` позволяет указать, разрешено ли вывод локального типа в файле. Чтобы включить или заблокировать параметр, введите одну из следующих инструкций в начале файла.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 Если не указать значение для `Option Infer` в коде, компилятор по умолчанию используется `Option Infer On`. В проектах, обновленных из [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] или более ранних версиях компилятора по умолчанию является `Option Infer Off`.  
  
 Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.  
  
 Дополнительные сведения см. в разделе [оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) и [компиляция, конструктор проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>См. также
- [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Оператор For...Next](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
