---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: e2957bf49292dfcafab8e78f4b997247c34ad279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599916"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Указывает, что переменная или свойство можно считывать, но не записываются.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** `ReadOnly` можно использовать только на уровне модуля. Это означает, что контекст объявления для `ReadOnly` элемент должен быть классом, структурой или модуля и не может быть исходным файлом, пространством имен или процедуры.  
  
-   **Комбинированные модификаторы.** Нельзя указать `ReadOnly` вместе с `Static` в одном объявлении.  
  
-   **Присвоение значения.** Использование кода `ReadOnly` свойство нельзя задать для него значение. Однако код, который имеет доступ к базовое хранилище можно назначить или изменить значение в любое время.  
  
     Можно присвоить значение `ReadOnly` переменной только при объявлении или в конструкторе класса или структуры, в котором он определен.  
  
## <a name="when-to-use-a-readonly-variable"></a>Когда следует использовать переменную только для чтения  
 Существуют ситуации, в которых нельзя использовать [оператор Const](../../../visual-basic/language-reference/statements/const-statement.md) объявления и присвоить постоянное значение. Например `Const` инструкция может не поддерживать тип данных, который вы хотите назначить или не может быть возможность вычисления значения во время компиляции с помощью константного выражения. Вам может быть даже неизвестно значение во время компиляции. В этих случаях можно использовать `ReadOnly` переменной для хранения постоянное значение.  
  
> [!IMPORTANT]
>  Если тип данных переменной является ссылочным типом, например, массив или экземпляр класса его члены могут быть изменены, даже если сама переменная `ReadOnly`. Это показано в следующем примере.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 При инициализации массива, на который указывает `characterArray()` содержит «x», «y» и «z». Так как переменная `characterArray` — `ReadOnly`, его значение нельзя изменить после инициализации;, нельзя назначить новый массив. Тем не менее можно изменить значения одного или нескольких элементов массива. После вызова процедуры `changeArrayElement`, массив, на который указывает `characterArray()` содержит «x», «M» и «z».  
  
 Обратите внимание, что это похоже на объявление параметра процедуры [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), который запрещает процедуре изменять аргумент вызова, но позволяет менять его члены.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `ReadOnly` свойство даты найма сотрудника. Класс хранит значение свойства, внутренне как `Private` переменной и только код внутри класса можно изменить это значение. Однако свойство `Public`, и любой код, который можно получить доступ к классу можно получить значение свойства.  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 Модификатор `ReadOnly` можно использовать в следующих контекстах:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>См. также  
 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
