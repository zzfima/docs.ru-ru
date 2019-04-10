---
title: Не задана переменная объекта или переменная блока With
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: b2c0c47b359e218111c1629ea574303a6d663046
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297932"
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Не задана переменная объекта или переменная блока With
Указан недопустимый объектной переменной.   Эта ошибка может возникать по нескольким причинам:  
  
-   Переменная, объявленная без определения типа. Если переменная объявлена без указания типа, по умолчанию к типу `Object`.  
  
     Например, переменная, объявленная с `Dim x` будут иметь тип `Object;` переменная, объявленная с `Dim x As String` будут иметь тип `String`.  
  
    > [!TIP]
    >  `Option Strict` Оператора для предотвращения неявная типизация, которая приводит к `Object` типа. Если не указан тип, возникнет ошибка времени компиляции. См. в разделе [Option Strict-оператор](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
-   Вы пытаетесь получить ссылку на объект, которое было задано для `Nothing`  
  
     .  
  
-   Вы пытаетесь получить доступ к элементу массива, который не был объявлен неправильно.  
  
     Например, массив, объявленный как `products() As String` приведет к возникновению ошибки при попытке ссылки на элемент массива `products(3) = "Widget"`. Массив не содержит элементов и рассматривается как объект.  
  
-   Вы пытаетесь получить доступ кода внутри `With...End With` блокировать до инициализации блока.   Объект `With...End With` блока должен быть инициализирован, выполнив `With` точки входа оператора.  
  
> [!NOTE]
>  В более ранних версиях Visual Basic или VBA Эта ошибка также было активировано путем присвоения значения переменной без использования `Set` ключевое слово (`x = "name"` вместо `Set x = "name"`). `Set` Слово больше не является допустимым в Visual Basic .net.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Задайте `Option Strict` для `On` , добавив следующий код в начало файла:  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2. Если вы не хотите включить `Option Strict`, найдите в коде всех переменных, которые были заданы без типа (`Dim x` вместо `Dim x As String`) и добавьте тип, предназначенный для объявления.  
  
3. Убедитесь, что вы не ссылаетесь на переменную объекта, было присвоено `Nothing`.  Поиск по коду для ключевого слова `Nothing`и изменить код таким образом, чтобы объект не задано значение `Nothing` до после создания ссылки на его.  
  
4. Убедитесь, что все переменные массива измеряются, прежде чем доступ к ним. При создании массива можно либо назначить измерения (`Dim x(5) As String` вместо `Dim x() As String`), или использовать `ReDim` ключевое слово, чтобы задать измерений массива, прежде чем вы впервые обращаетесь.  
  
5. Убедитесь, что ваш `With` блок инициализируется посредством выполнения `With` точки входа оператора.  
  
## <a name="see-also"></a>См. также

- [Объявление объектной переменной](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Оператор ReDim](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
