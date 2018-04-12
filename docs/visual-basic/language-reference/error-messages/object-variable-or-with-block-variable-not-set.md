---
title: Не задана переменная объекта или переменная блока With
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e1f587e194acf744b6ec9b8f1bede3acef7b753
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Не задана переменная объекта или переменная блока With
Указан недопустимый объектной переменной.   Эта ошибка может возникать по нескольким причинам:  
  
-   Переменная была объявлена без указания типа. Если переменная объявлена без указания типа, то по умолчанию к типу `Object`.  
  
     Например, переменная, объявленная с `Dim x` будет иметь тип `Object;` переменная, объявленная с `Dim x As String` будет иметь тип `String`.  
  
    > [!TIP]
    >  `Option Strict` Инструкции запрещает неявное типизирование, в результате `Object` типа. Если параметр типа, возникнет ошибка времени компиляции. В разделе [Option Strict-оператор](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
-   Вы пытаетесь ссылаться на объект, который равен`Nothing`  
  
     .  
  
-   Вы пытаетесь получить доступ к элементу массива, который не был объявлен неправильно.  
  
     Например, массив объявлен как `products() As String` приведет к возникновению ошибки при попытке ссылки на элемент массива `products(3) = "Widget"`. Массив не содержит элементов и обрабатываются как объект.  
  
-   Вы пытаетесь получить доступ код внутри `With...End With` блокируются прежде, чем блок был инициализирован.   Объект `With...End With` блока должны инициализироваться, выполнив `With` точки входа оператора.  
  
> [!NOTE]
>  В более ранних версиях Visual Basic или VBA ошибки также была запущена при присвоении значения переменной без использования `Set` ключевое слово (`x = "name"` вместо `Set x = "name"`). `Set` Ключевое слово больше не действительна в Visual Basic .net.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Задать `Option Strict` для `On` , добавив следующий код в начало файла:  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  Если вы не хотите включить `Option Strict`, найдите в коде всех переменных, которые были заданы без типа (`Dim x` вместо `Dim x As String`) и добавьте к объявлению нужному типу.  
  
3.  Убедитесь, что не ссылается на объектную переменную, которая настроена для `Nothing`.  Найдите в коде для ключевого слова `Nothing`и изменить код таким образом, чтобы объект не задано значение `Nothing` до после создания ссылки на его.  
  
4.  Убедитесь, что все переменные массива измеряются перед обращением к их. При создании массива можно либо назначить измерения (`Dim x(5) As String` вместо `Dim x() As String`), или используйте `ReDim` ключевое слово для задания измерения массива перед сначала к нему.  
  
5.  Убедитесь, что ваш `With` блок инициализируется путем выполнения `With` точки входа оператора.  
  
## <a name="see-also"></a>См. также  
 [Объявление объектной переменной](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
