---
title: "Разделяемые методы (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.PartialMethod"
  - "PartialMethod"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "пользовательская логика в коде [Visual Basic]"
  - "вставка пользовательской логики в код"
  - "методы [Visual Basic], частично выполненные методы"
  - "частично выполненные методы [Visual Basic]"
  - "разделяемые, методы [Visual Basic]"
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Разделяемые методы (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Разделяемые методы позволяют разработчикам использовать другую логику в коде.  Обычно код является частью класса, созданного разработчиком.  Разделяемые методы определяются в разделяемом классе, созданном генератором кода, и они обычно используются для предоставления уведомлений о том, что объект был изменен.  Они позволяют разработчику указать пользовательское поведение в ответ на изменение.  
  
 Конструктор генератора кода определяет только сигнатуру метода и один или несколько вызовов метода.  Разработчики могут затем предоставить реализации метода при необходимости изменения поведения созданного кода.  Если реализации не указаны, вызовы методов удаляются компилятором, что позволяет сократить потери производительности.  
  
## Объявление  
 Созданный код помечает определение разделяемого метода, вставляя ключевое слово `Partial` в начале строки сигнатуры.  
  
```vb#  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 Определение должно удовлетворять следующим условиям:  
  
-   Метод должен иметь тип `Sub`, а не `Function`.  
  
-   Тело метода необходимо оставить пустым.  
  
-   Модификатор доступа должны иметь тип `Private`.  
  
## Реализация  
 В основном реализация состоит из заполнения тела разделяемого метода.  Реализация находится обычно в отдельном разделяемом классе из определения и создается разработчиком, который стремится расширить созданный код.  
  
```vb#  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 Вариант предыдущего примера точно дублирует сигнатуру в объявлении, но возможны также другие варианты.  В частности, могут быть добавлены другие модификаторы, например `Overloads` или `Overrides`.  Разрешается использование только одного модификатора `Overrides`.  Дополнительные сведения о модификаторах метода см. в разделе [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## Применение  
 Вызовите разделяемый метод таким же образом, как вызывается любая другая процедура `Sub`.  Если метод был реализован, вычисляются аргументы и выполняется тело метода.  Однако следует помнить, что реализация разделяемого метода необязательна.  Если метод не реализован, то вызывать его не эффективно, и выражения, передаваемые как аргументы в метод, не вычисляются.  
  
## Пример  
 В файле Product.Designer.vb определите класс `Product`, имеющий свойство `Quantity`.  
  
 [!code-vb[VbVbalrPartialMeths#4](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/partial-methods_1.vb)]  
  
 В файле Product.vb создайте реализацию для `QuantityChanged`.  
  
 [!code-vb[VbVbalrPartialMeths#5](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/partial-methods_2.vb)]  
  
 Наконец, в методе Main проекта объявите экземпляр `Product` и укажите начальное значение для его свойства `Quantity`.  
  
 [!code-vb[VbVbalrPartialMeths#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/partial-methods_3.vb)]  
  
 Появится окно, которое выводит сообщение:  
  
 `Quantity was changed to 100`  
  
## См. также  
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Подпрограммы](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Необязательные параметры](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)   
 [Создание кода в LINQ to SQL](../Topic/Code%20Generation%20in%20LINQ%20to%20SQL.md)   
 [Добавление бизнес\-логики с помощью разделяемых методов](../Topic/Adding%20Business%20Logic%20By%20Using%20Partial%20Methods.md)