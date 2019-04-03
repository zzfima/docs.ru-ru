---
title: Практическое руководство. Доступ к членам объекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 2b7e600a23ed326fe3e914957b4e698bc34c6135
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819659"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Практическое руководство. Доступ к членам объекта (Visual Basic)
При наличии объектную переменную, которая ссылается на объект, часто требуется для работы с членами этого объекта, например методы, свойства, поля и события. Например, когда вы создадите новый <xref:System.Windows.Forms.Form> объекта, может потребоваться задать его <xref:System.Windows.Forms.Control.Text%2A> свойства или вызов его <xref:System.Windows.Forms.Control.Focus%2A> метод.  
  
## <a name="accessing-members"></a>Доступ к членам  
 Доступ к членам объекта осуществляется через переменную, которая ссылается на него.  
  
#### <a name="to-access-members-of-an-object"></a>Для доступа к членам объекта  
  
-   Оператор доступа к членам (`.`) между именем переменной объекта и имя члена.  
  
    ```  
    currentText = newForm.Text  
    ```  
  
     Если член является [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), нет необходимости переменной для доступа к нему.  
  
## <a name="accessing-members-of-an-object-of-known-type"></a>Доступ к членам объекта известного типа  
 Если вы знаете тип объекта во время компиляции, можно использовать *раннее связывание* переменной, которая ссылается на него.  
  
#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Для доступа к членам объекта, для которого вы знаете тип во время компиляции  
  
1.  Объявите переменную объекта типа объекта, который требуется присвоить переменной.  
  
    ```  
    Dim extraForm As System.Windows.Forms.Form  
    ```  
  
     С помощью `Option Strict On`, можно назначить только <xref:System.Windows.Forms.Form> объектов (или объекты типа, производного от <xref:System.Windows.Forms.Form>) для `extraForm`. Если вы определили класса или структуры с помощью расширяющего `CType` преобразование в <xref:System.Windows.Forms.Form>, можно также назначить класс или структуру `extraForm`.  
  
2.  Оператор доступа к членам (`.`) между именем переменной объекта и имя члена.  
  
    ```  
    extraForm.Show()  
    ```  
  
     Вам доступны все методы и свойства, относящиеся к <xref:System.Windows.Forms.Form> класса, независимо от того, что `Option Strict` параметр.  
  
## <a name="accessing-members-of-an-object-of-unknown-type"></a>Доступ к членам объекта неизвестного типа  
 Если вы не знаете тип объекта во время компиляции, необходимо использовать *позднее связывание* для любой переменной, которая ссылается на него.  
  
#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Для доступа к членам объекта, для которого вы не знаете тип во время компиляции  
  
1.  Объявите переменную объекта с [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Объявление переменной как `Object` совпадает со значением его объявление как <xref:System.Object?displayProperty=nameWithType>.)  
  
    ```  
    Dim someControl As Object  
    ```  
  
     С помощью `Option Strict On`, доступны только члены, определенные для <xref:System.Object> класса.  
  
2.  Оператор доступа к членам (`.`) между именем переменной объекта и имя члена.  
  
    ```  
    someControl.GetType()  
    ```  
  
     Чтобы иметь возможность доступа к членам любого объекта, можно присвоить переменной объекта, необходимо задать `Option Strict Off`. При этом компилятор не может гарантировать, что данный элемент предоставляется с помощью объекта, можно присвоить переменной. Если объект не предоставляет членом попытки обращения к, <xref:System.MemberAccessException> возникает исключение.  
  
## <a name="see-also"></a>См. также

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
