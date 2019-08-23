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
ms.openlocfilehash: 01c441576cb4247933c053f2043296733f99fdeb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965425"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
Указывает, что переменная или свойство может быть прочитано, но не записано.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="rules"></a>Правила  
  
- **Контекст объявления.** `ReadOnly` можно использовать только на уровне модуля. Это означает, что контекст объявления для `ReadOnly` элемента должен быть классом, структурой или модулем и не может быть исходным файлом, пространством имен или процедурой.  
  
- **Комбинированные модификаторы.** Нельзя указывать `ReadOnly` вместе с `Static` в одном объявлении.  
  
- **Присвоение значения.** Код, использующий свойство, `ReadOnly` не может задать его значение. Но код, имеющий доступ к базовому хранилищу, может назначить или изменить значение в любое время.  
  
     Значение `ReadOnly` переменной можно присвоить только в ее объявлении или в конструкторе класса или структуры, в которой он определен.  
  
## <a name="when-to-use-a-readonly-variable"></a>Когда следует использовать переменную только для чтения  
 Существуют ситуации, в которых нельзя использовать [оператор Const](../../../visual-basic/language-reference/statements/const-statement.md) для объявления и присваивания постоянного значения. Например, `Const` инструкция может не принять тип данных, который необходимо назначить, или не удастся вычислить значение во время компиляции с помощью константного выражения. Возможно, вы даже не узнаете значение во время компиляции. В таких случаях можно использовать `ReadOnly` переменную для хранения постоянного значения.  
  
> [!IMPORTANT]
> Если тип данных переменной является ссылочным типом, например массивом или экземпляром класса, его члены можно изменить, даже если сама переменная имеет `ReadOnly`значение. Это показано в следующем примере.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 При инициализации массив, на `characterArray()` который указывает, содержит "x", "y" и "z". Так как переменная `characterArray` является `ReadOnly`, ее значение нельзя изменить после инициализации, то есть нельзя присвоить ему новый массив. Однако можно изменить значения одного или нескольких элементов массива. После вызова процедуры `changeArrayElement`массив, на который указывает, `characterArray()` содержит "x", "M" и "z".  
  
 Обратите внимание, что это похоже на объявление параметра процедуры как [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), что не позволяет процедуре изменять сам аргумент вызова, но позволяет ему изменять его члены.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется `ReadOnly` свойство для даты найма сотрудника. Класс сохраняет значение свойства внутри в виде `Private` переменной, и только код внутри класса может изменить это значение. Однако свойство имеет `Public`значение, а любой код, который может получить доступ к классу, может считать свойство.  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 Модификатор `ReadOnly` можно использовать в следующих контекстах:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>См. также

- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
