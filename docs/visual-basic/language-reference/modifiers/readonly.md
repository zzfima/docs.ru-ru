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
ms.openlocfilehash: 1a486d0fadce8135fe01d9eecd611081c986bfae
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647690"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Указывает, что переменная или свойство можно читать, но не записываются.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="rules"></a>Правила  
  
- **Контекст объявления.** `ReadOnly` можно использовать только на уровне модуля. Это означает, что контекст объявления для `ReadOnly` элемент должен быть класс, структура или модуль и не может быть исходный файл, пространство имен или процедуры.  
  
- **Комбинированные модификаторы.** Нельзя указать `ReadOnly` вместе с `Static` в одном объявлении.  
  
- **Присвоение значения.** Использование кода `ReadOnly` свойство невозможно задать его значение. Но код, который имеет доступ в базовом хранилище можно назначить или изменить значение в любое время.  
  
     Можно присвоить значение `ReadOnly` переменной только при объявлении или в конструкторе класса или структуры, в котором он определен.  
  
## <a name="when-to-use-a-readonly-variable"></a>Когда следует использовать переменную только для чтения  
 Существуют ситуации, в которых нельзя использовать [оператор Const](../../../visual-basic/language-reference/statements/const-statement.md) объявить переменную и присвоить значение константы. Например `Const` инструкция может не поддерживать тип данных, который вы хотите назначить, или вы не может для вычисления значения во время компиляции с константным выражением. Вам могут даже не знать значение во время компиляции. В таких случаях можно использовать `ReadOnly` переменной для хранения значение константы.  
  
> [!IMPORTANT]
>  Если тип данных переменной является ссылочным типом, например, массив или экземпляр класса, можно изменить его члены, даже если сама переменная `ReadOnly`. Это показано в следующем примере.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 При инициализации массива, на которые указывают `characterArray()` содержит «x», «y» и «z». Так как переменная `characterArray` — `ReadOnly`, его значение нельзя изменить после инициализации; это, нельзя назначить новый массив. Тем не менее можно изменить значения одного или нескольких элементов массива. После вызова процедуры `changeArrayElement`, массив, на которые указывают `characterArray()` содержит «x», «M» и «z».  
  
 Обратите внимание, что это похоже на объявление параметра процедуры [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), который запрещает изменять аргумент вызова процедуры, но позволяет менять ее членов.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `ReadOnly` свойство для даты, на котором сотрудник был принят на работу. Класс хранит значение свойства как внутренне `Private` переменной, а только код внутри класса, это значение можно изменить. Тем не менее, свойство является `Public`, и любой код, который можно получить доступ к классу можно считать свойство.  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 Модификатор `ReadOnly` можно использовать в следующих контекстах:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>См. также

- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
