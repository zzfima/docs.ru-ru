---
title: "MustInherit (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "MustInherit"
  - "vb.MustInherit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "абстрактные классы, MustInherit - класс"
  - "классы [Visual Basic], абстрактные"
  - "MustInherit - классы, MustInherit - ключевое слово"
  - "MustInherit - ключевое слово"
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# MustInherit (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает, что класс может использоваться только как базовый класс и что невозможно создать объект непосредственно из него.  
  
## Заметки  
 Назначение *базового класса* \(также называемого *абстрактным классом*\) — определение функций, общих для всех классов, производных от него.  Это предохраняет производные классы от необходимости переопределять общие элементы.  В некоторых случаях эта общая функциональная возможность недостаточно полна, чтобы сделать подходящий объект, и каждый производный класс определяет отсутствующие функциональные возможности.  В таком случае требуется много кода для создания объектов только из производных классов.  Для реализации этого необходимо применить `MustInherit` к базовому классу.  
  
 Другое применение `MustInherit` — это ограничение переменной до набора связанных классов.  Можно определить базовый класс и вывести все эти связанные классы из него.  Базовый класс не требует предоставления функциональных возможностей, общих для всех производных классов, но может служить фильтром для присвоения значений переменным.  Если код объявляет переменную как базовый класс, Visual Basic позволяет Вам присвоить ей только объект из одного из производных классов.  
  
 .NET Framework определяет несколько классов `MustInherit`, в том числе <xref:System.Array>, <xref:System.Enum> и <xref:System.ValueType>.  Класс <xref:System.ValueType> — пример базового класса, ограничивающего переменную.  Все типы значений являются производными от <xref:System.ValueType>.  Если объявить переменную как <xref:System.ValueType>, этой переменной можно назначить только типы значений.  
  
## Правила  
  
-   **Контекст объявления.** `MustInherit` можно использовать только в операторе `Class`.  
  
-   **Комбинированные модификаторы.** Нельзя в одном объявлении указывать `MustInherit` и `NotInheritable`.  
  
## Пример  
 Приведенный ниже пример иллюстрирует принудительное наследование и переопределение.  Базовый класс `shape` определяет переменную `acrossLine`.  Классы `circle` и `square` являются производными от `shape`.  Они наследуют определение `acrossLine`, но должны определять функцию `area`, так как этот расчет отличается для каждого вида фигуры.  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 Можно объявить `shape1` и `shape2` с типом `shape`.  Однако, невозможно создать объект из `shape`, так как он не имеет возможностей функции `area` и помечен `MustInherit`.  
  
 Так как они объявлены как `shape`, переменные `shape1` и `shape2` ограничены объектами из производных классов `circle` и `square`.  Visual Basic не позволяет назначать этим переменным какой\-либо другой объект, предоставляющий высокий уровень безопасности типов.  
  
## Использование  
 Модификатор `MustInherit` можно использовать в следующем контексте.  
  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## См. также  
 [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)   
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)   
 [Основы наследования](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)