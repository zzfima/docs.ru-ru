---
title: "Переменная объекта или переменная блока With не задано | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID91
dev_langs:
- VB
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 820ef0115a6a27d77f10f4e41d95576bbd79bfa3
ms.lasthandoff: 03/13/2017

---
# <a name="object-variable-or-with-block-variable-not-set"></a>Не задана переменная объекта или переменная блока With
Указан недопустимый объект переменной.   Эта ошибка может возникать по нескольким причинам:  
  
-   Переменная, объявленная без определения типа. Если переменная объявлена без указания типа, то по умолчанию введите `Object`.  
  
     Например, переменная, объявленная с `Dim x` будут иметь тип `Object;` переменная, объявленная с `Dim x As String` будут иметь тип `String`.  
  
    > [!TIP]
    >  `Option Strict` Инструкции запрещает неявной типизации, в результате `Object` типа. Если тип не указан, произойдет ошибка времени компиляции. В разделе [Option Strict оператор](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
-   Вы пытаетесь получить ссылку на объект, который имеет значение`Nothing`  
  
     .  
  
-   Была попытка доступа к элементу массива, который не был объявлен неправильно.  
  
     Например, массив объявлен как `products() As String` вызовет ошибку при попытке ссылки на элемент массива `products(3) = "Widget"`. Массив не содержит элементов и рассматривается как объект.  
  
-   Вы пытаетесь получить код доступа в `With...End With` блокировать до инициализации блока.   Объект `With...End With` блок необходимо инициализировать посредством выполнения `With` точки входа оператора.  
  
> [!NOTE]
>  В более ранних версиях Visual Basic или VBA Эта ошибка также была активирована путем присвоения значения переменной без использования `Set` ключевое слово (`x = "name"` вместо `Set x = "name"`). `Set` Ключевое слово больше не действительна в Visual Basic .net.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Задайте `Option Strict` в `On` , добавив следующий код в начало файла:  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  Если вы не хотите включить `Option Strict`, выполнить поиск кода для всех переменных, которые были заданы без типа (`Dim x` вместо `Dim x As String`) и добавьте нужный тип в объявлении.  
  
3.  Убедитесь, что не ссылки на объектную переменную, которая имеет значение `Nothing`.  Найдите в коде для ключевого слова `Nothing`и измените код так, что объект не `Nothing` до после создания ссылки на его.  
  
4.  Убедитесь, что все переменные массива измеряются до доступа к ним. При создании массива можно либо назначить измерения (`Dim x(5) As String` вместо `Dim x() As String`), или использовать `ReDim` ключевое слово для задания измерения массива перед сначала к нему.  
  
5.  Убедитесь, что ваш `With` блок инициализируется посредством выполнения `With` точки входа оператора.  
  
## <a name="see-also"></a>См. также  
 [Объявление переменных объектов](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Оператор reDim](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
