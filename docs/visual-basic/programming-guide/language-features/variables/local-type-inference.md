---
title: "Вывод локального типа (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "local type inference"
  - "vb.TypeInfer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "явно введенные локальные переменные [Visual Basic]"
  - "вывод [Visual Basic]"
  - "вывод локального типа [Visual Basic]"
  - "Option Infer - оператор"
  - "вывод типа [Visual Basic]"
  - "переменные [Visual Basic], определение типа"
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
caps.latest.revision: 43
caps.handback.revision: 43
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Вывод локального типа (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Компилятор Visual Basic использует *определение типа* для определения типов данных локальных переменных, объявляемых без предложения `As`.  Компилятор выводит тип переменной из типа инициализированного выражения.  Это позволяет объявлять переменные без явного формулирования типа, как показано в следующем примере. В результате объявлений переменные `num1` и `num2` строго типизированы как целые числа.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]  
  
> [!NOTE]
>  Если вы не хотите, чтобы `num2` в предыдущем примере была введена как `Integer`, можно указать другой тип с помощью такого объявления, как `Dim num3 As Object = 3` или `Dim num4 As Double = 3`.  
  
 Вывод локального типа происходит на уровне процедуры.  Его нельзя использовать для объявления переменных на уровне модуля \(в рамках класса, структуры, модуля или интерфейса, но не в рамках процедуры или блока\).  Если бы `num2` в предыдущем примере была полем класса, а не локальной переменной в процедуре, объявление привело бы к ошибке с `Option Strict` "on" и классифицировало бы `num2` как `Object` с `Option Strict` "off".  Аналогично, вывод локального типа не применяется к переменным уровня процедур, объявленных как `Static`.  
  
## Определение типа илипозднее связывание  
 Код, который использует выведение типа напоминает код, основанный на позднем связывании.  Тем не менее, выведение типа строго типизирует переменные вместо того, чтобы оставлять их в качестве `Object`.  Компилятор использует инициализатор переменной для определения типа переменной во время компиляции для создания кода с ранней привязкой.  В предыдущем примере `num2`, как и `num1`, объявляется как тип `Integer`.  
  
 Поведение переменных с ранней привязкой отличается от поведения переменных с поздней привязкой, для которых тип известен только во время выполнения.  Знание типа заранее позволяет компилятору выявить проблемы до выполнения, точно выделить память и выполнить другие действия по оптимизации.  Раннее связывание также позволяет интегрированной среде разработки Visual Basic \(IDE\) предоставлять справку IntelliSense об элементах объекта.  Раннее связывание также является предпочтительным с точки зрения производительности.  Это объясняется тем, что все данные, хранящиеся в переменной с поздней привязкой, должны быть упакованы как тип `Object` и доступ к элементам типа во время выполнения делает программу медленнее.  
  
## Примеры  
 Вывод типа происходит, когда локальная переменная объявлена без предложения `As` и инициализирована.  Компилятор использует тип присвоенного начального значения в качестве типа переменной.  Например, все следующие строки кода объявляют переменную типа `String`.  
  
 [!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]  
  
 Следующий код демонстрирует два эквивалентных способа создания массива целых чисел.  
  
 [!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]  
  
 Вывод типа удобно использовать для определения типа переменной управления циклом.  В следующем коде компилятор выводит, что `number` относится к типу `Integer`, поскольку `someNumbers2` из предыдущего примера является массивом целых чисел.  
  
 [!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]  
  
 Выведение локального типа можно использовать в инструкциях `Using`, чтобы установить тип имени ресурса, как показано в следующем примере.  
  
 [!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]  
  
 Тип переменной также может быть выведен из возвращаемых значений функции, как показано в следующем примере.  И `pList1`, и `pList2` являются массивами процессов, потому что `Process.GetProcesses` возвращает массив процессов.  
  
 [!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]  
  
## Option Infer  
 `Option Infer` позволяет определить, разрешено ли вывод локального типа в заданном файле.  Чтобы включить или заблокировать параметр, введите одну из следующих инструкций в начале файла.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 Если не задать значение для параметра `Option Infer` в коде, по умолчанию в компиляторе используется значение `Option Infer On`.  В проектах, обновленных с [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)] или более ранних версий, по умолчанию в компиляторе используется значение `Option Infer Off`.  
  
 Если значение, заданное `Option Infer` в файле, конфликтует со значением, заданным в IDE или в командной строке, то значение в файле имеет приоритет.  
  
 Дополнительные сведения см. в разделах [Option Infer \- оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md) и [Страница "Компиляция" в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic).  
  
## Ограничения  
 Выведение типа может использоваться только для нестатических локальных переменных; оно не может использоваться для определения типа полей класса, свойств или функций.  
  
## См. также  
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Раннее и позднее связывание](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Оператор For...Next](../../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Option Infer \- оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [\/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)