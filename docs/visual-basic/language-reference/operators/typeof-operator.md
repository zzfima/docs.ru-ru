---
title: "Оператор TypeOf (Visual Basic) | Microsoft Docs"
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
  - "TypeOf"
  - "vb.TypeOf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "операторы сравнения"
  - "совместимые типы данных"
  - "типы данных [Visual Basic], совместимый"
  - "TypeOf - оператор [Visual Basic]"
  - "TypeOf...Is - выражение"
  - "типы [Visual Basic], совместимый"
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Оператор TypeOf (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Сравнивает переменную ссылки на объект с типом данных.  
  
## Синтаксис  
  
```  
  
result = TypeOf objectexpression Is typename  
```  
  
```  
  
result = TypeOf objectexpression IsNot typename  
```  
  
## Части  
 `result`  
 Возвращено.  Значение `Boolean`.  
  
 `objectexpression`  
 Обязательный.  Любое выражение, результатом которого является тип ссылки.  
  
 `typename`  
 Обязательный.  Любое имя типа данных.  
  
## Заметки  
 Оператор `TypeOf` определяет, совместим ли тип времени выполнения `objectexpression` с `typename`.  Совместимость зависит от категории типа `typename`.  В следующей таблице показано, как определяется совместимость.  
  
|Категория типа `typename`|Критерий совместимости|  
|-------------------------------|----------------------------|  
|Класс|`objectexpression` типа `typename` или наследует от `typename`|  
|Структура|`objectexpression` типа `typename`|  
|Интерфейс|`objectexpression` реализует `typename` или наследует от класса, реализующего `typename`|  
  
 Если тип времени выполнения `objectexpression` удовлетворяет критерию совместимости, `result` является `True`.  В противном случае `result` является `False`.  Если `objectexpression` имеет значение null, то `TypeOf`...`Is` возвращает `False`, а ...`IsNot` возвращает `True`.  
  
 `TypeOf` всегда используется с ключевым словом `Is` для создания выражения `TypeOf`...`Is` или с ключевым словом `IsNot` для создания выражения `TypeOf`...`IsNot`.  
  
## Пример  
 В следующем примере выражение `TypeOf`...`Is` используется для проверки на совместимость типов двух переменных ссылок на объекты с различными типами данных.  
  
 [!code-vb[VbVbalrOperators#39](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/typeof-operator_1.vb)]  
  
 Переменная `refInteger` имеет тип времени выполнения `Integer`.  Она совместима с `Integer`, но не с `Double`.  Переменная `refForm` имеет тип времени выполнения <xref:System.Windows.Forms.Form>.  Она совместима с <xref:System.Windows.Forms.Form>, так как это ее тип, с <xref:System.Windows.Forms.Control>, так как <xref:System.Windows.Forms.Form> наследует от <xref:System.Windows.Forms.Control>, и с <xref:System.ComponentModel.IComponent>, так как <xref:System.Windows.Forms.Form> наследует от <xref:System.ComponentModel.Component>, который реализует <xref:System.ComponentModel.IComponent>.  Однако `refForm` несовместима с <xref:System.Windows.Forms.Label>.  
  
## См. также  
 [Оператор Is](../../../visual-basic/language-reference/operators/is-operator.md)   
 [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Операторы сравнения в Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)