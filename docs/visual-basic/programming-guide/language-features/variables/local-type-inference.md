---
title: "Вывод локального типа (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- local type inference
- vb.TypeInfer
dev_langs:
- VB
helpviewer_keywords:
- Option Infer statement
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
caps.latest.revision: 43
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2bb673ce871b8e875f62c373404a849c139ab598
ms.lasthandoff: 03/13/2017

---
# <a name="local-type-inference-visual-basic"></a>Вывод локального типа (Visual Basic)
Компилятор Visual Basic использует *вывод типа* для определения типов данных локальных переменных, объявленных без `As` предложения. Компилятор выводит тип переменной из типа выражения инициализации. Это позволяет объявлять переменные без явного указания типа, как показано в следующем примере. В результате объявлений оба `num1` и `num2` являются строго типизированными как целые числа.  
  
 [!code-vb[VbVbalrTypeInference&#1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]  
  
> [!NOTE]
>  Если вы не хотите `num2` в предыдущем примере была введена как `Integer`, можно указать другой тип с помощью такого объявления, как `Dim num3 As Object = 3` или `Dim num4 As Double = 3`.  
  
 Вывод локального типа происходит на уровне процедуры. Он не может использоваться для объявления переменных на уровне модуля (в рамках класса, структуры, модуля или интерфейса, но не внутри процедуры или блока). Если `num2` в предыдущем примере была полем класса вместо локальной переменной в процедуре, объявление привело бы к ошибке с `Option Strict` и было бы классифицировать `num2` как `Object` с `Option Strict` off. Аналогично, вывод локального типа не применяется к процедуре переменные, объявленные как `Static`.  
  
## <a name="type-inference-vs-late-binding"></a>Определение типа или. Позднее связывание  
 Код, который использует выведение типа напоминает код, основанный на позднем связывании. Тем не менее, выведение типа строго типизирует переменные вместо оставлять их в качестве `Object`. Компилятор использует инициализатор переменной для определения типа переменной во время компиляции для создания кода с ранней привязкой. В предыдущем примере `num2`, например `num1`, типизируется как `Integer`.  
  
 Поведение переменных с ранней привязкой отличается от переменных с поздней привязкой, для которых тип известен только во время выполнения. Знание типа заранее позволяет компилятору выявить проблемы до выполнения, точно выделить память и выполнять другие виды оптимизации. Раннее связывание также позволяет Visual Basic интегрированной среде разработки (IDE) предоставлять справку IntelliSense об элементах объекта. Раннее связывание также является предпочтительным для повышения производительности. Это потому, что все данные, хранящиеся в переменной с поздней привязкой должны быть упакованы как тип `Object`, и доступ к членам типа во время выполнения делает программу медленнее.  
  
## <a name="examples"></a>Примеры  
 Вывод типа происходит, когда локальная переменная объявлена без `As` предложения и инициализации. Компилятор использует тип присвоенного начального значения как тип переменной. Например, каждый следующий код объявляет переменную типа `String`.  
  
 [!code-vb[VbVbalrTypeInference&#2;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]  
  
 В следующем коде показано два эквивалентных способа создания массива целых чисел.  
  
 [!code-vb[VbVbalrTypeInference&#3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]  
  
 Удобно использовать вывод типа для определения типа переменной цикла. В следующем коде компилятор выводит, что `number` — `Integer` из-за `someNumbers2` из предыдущего примера является массивом целых чисел.  
  
 [!code-vb[VbVbalrTypeInference&#4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]  
  
 Вывод локального типа могут использоваться в `Using` инструкции, чтобы установить тип имени ресурса, как показано в следующем примере.  
  
 [!code-vb[VbVbalrTypeInference&#7;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]  
  
 Тип переменной также может выводиться из возвращаемых значений функции, как показано в следующем примере. Оба `pList1` и `pList2` являются массивами процессов, так как `Process.GetProcesses` возвращает массив процессов.  
  
 [!code-vb[VbVbalrTypeInference&#5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]  
  
## <a name="option-infer"></a>Option Infer  
 `Option Infer`позволяет указать, разрешено ли вывод локального типа в конкретном файле. Чтобы включить или заблокировать параметр, введите одну из следующих инструкций в начале файла.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 Если не указать значение для `Option Infer` в коде, компилятор по умолчанию является `Option Infer On`. В проектах, обновленных из [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)] или более ранних версиях компилятора по умолчанию — `Option Infer Off`.  
  
 Если значение, заданное для `Option Infer` в файле, конфликтует со значением, заданным в среде разработки или в командной строке, приоритет имеет значение в файле.  
  
 Дополнительные сведения см. в разделе [Option Infer оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md) и [компиляция, конструктор проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="restrictions"></a>Ограничения  
 Определение типа может использоваться только для нестатических локальных переменных; он не может использоваться для определения типа полей класса, свойств или функций.  
  
## <a name="see-also"></a>См. также  
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)   
 [Для каждого... Следующий оператор](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Для... Следующий оператор](../../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [/ optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
