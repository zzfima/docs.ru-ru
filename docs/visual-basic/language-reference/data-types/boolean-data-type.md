---
title: "Тип данных Boolean (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.FALSE"
  - "vb.TRUE"
  - "vb.Boolean"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "boolean - тип данных"
  - "логические значения, False - ключевое слово"
  - "логические значения, True - ключевое слово"
  - "False - ключевое слово [Visual Basic]"
  - "True - ключевое слово [Visual Basic]"
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Тип данных Boolean (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Содержит значения, которые могут быть только `True` или `False`.  Ключевые слова `True` и `False` соответствуют двум состояниям переменных `Boolean`.  
  
## Заметки  
 Используйте тип данных [Boolean Data Type \(Visual Basic\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) для хранения значений двух состояний, например true\/false, yes\/no или on\/off.  
  
 По умолчанию для атрибута `Boolean` используется значение `False`.  
  
 `Boolean` значения не хранятся в виде чисел, и хранимые значения не предназначены для того чтобы быть эквивалентными числам.  Никогда не следует писать код, который основывается на эквивалентных числовых значениях для `True` и `False`.  Везде, где это возможно, следует ограничивать применение переменных с типом `Boolean` логическими значениями, для которых этот тип специально предназначен.  
  
## Преобразования типов  
 Когда Visual Basic преобразует значения числовых типов данных в `Boolean`, 0 становится `False`, а все остальные значения — `True`.  Когда Visual Basic преобразует значения `Boolean` в числовые типы, `False` становится 0, а `True` становится \-1.  
  
 При преобразовании значений `Boolean` в числовые типы данных имейте в виду, что методы преобразования платформы .NET Framework не всегда производят тот же результат, что и ключевые слова преобразования Visual Basic.  Это происходит потому, что преобразование Visual Basic сохраняет поведение, совместимое с предыдущими версиями.  Дополнительные сведения содержатся в разделе "Логический тип неточно преобразовывается в числовой тип" [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## Советы по программированию  
  
-   **Отрицательные числа.** `Boolean` не является числовым типом и не может представлять отрицательное значение.  В любом случае не следует использовать переменные типа `Boolean` для хранения числовых значений.  
  
-   **Символы типа.** Тип `Boolean` не имеет символов типа литерала или символов типа идентификатора.  
  
-   **Тип Framework.**. В .NET Framework данный тип соответствует структуре <xref:System.Boolean?displayProperty=fullName>.  
  
## Пример  
 В следующем примере, `runningVB` является переменной `Boolean`, в которой хранятся простые параметры "Да\/Нет".  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## См. также  
 <xref:System.Boolean?displayProperty=fullName>   
 [Типы данных](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Сводка по преобразованию](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Эффективное использование типов данных](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Устранение неполадок, связанных с типами данных](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Функция CType](../../../visual-basic/language-reference/functions/ctype-function.md)