---
title: Практическое руководство. Доступ к членам объекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- members [Visual Basic], accessing
- object variables [Visual Basic], accessing members
ms.assetid: a0072514-6a79-4dd6-8d03-ca8c13e61ddc
ms.openlocfilehash: 882046b829ade2da7c10b3db4c0d6c9ca9f3d579
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630833"
---
# <a name="how-to-access-members-of-an-object-visual-basic"></a>Практическое руководство. Доступ к членам объекта (Visual Basic)

При наличии переменной объекта, ссылающейся на объект, часто требуется работать с элементами этого объекта, такими как его методы, свойства, поля и события. Например, после создания нового <xref:System.Windows.Forms.Form> объекта может потребоваться задать его <xref:System.Windows.Forms.Control.Text%2A> свойство или вызвать его <xref:System.Windows.Forms.Control.Focus%2A> метод.

## <a name="accessing-members"></a>Доступ к членам

Доступ к членам объекта осуществляется через переменную, ссылающуюся на него.

#### <a name="to-access-members-of-an-object"></a>Получение доступа к членам объекта

- Используйте оператор доступа к членам (`.`) между именем объектной переменной и именем члена.

    ```vb
    currentText = newForm.Text
    ```

    Если член является [общим](../../../../visual-basic/language-reference/modifiers/shared.md), для доступа к нему не требуется переменная.

## <a name="accessing-members-of-an-object-of-known-type"></a>Доступ к членам объекта известного типа

Если тип объекта известно во время компиляции, можно использовать раннее связывание для переменной, ссылающейся на нее.

#### <a name="to-access-members-of-an-object-for-which-you-know-the-type-at-compile-time"></a>Доступ к членам объекта, тип которых вы узнаете во время компиляции

1. Объявите переменную объекта для типа объекта, который необходимо назначить переменной.

    ```vb
    Dim extraForm As System.Windows.Forms.Form
    ```

    С `Option Strict On`помощью можно назначать только <xref:System.Windows.Forms.Form> объекты (или объекты `extraForm`типа, производного от <xref:System.Windows.Forms.Form>). Если вы определили класс или структуру с расширяющимся `CType` преобразованием в <xref:System.Windows.Forms.Form>, можно также присвоить `extraForm`этому классу или структуре значение.

2. Используйте оператор доступа к членам (`.`) между именем объектной переменной и именем члена.

    ```vb
    extraForm.Show()
    ```

    Можно получить доступ ко всем методам и свойствам, относящимся к <xref:System.Windows.Forms.Form> классу, независимо от `Option Strict` значения параметра.

## <a name="accessing-members-of-an-object-of-unknown-type"></a>Доступ к членам объекта неизвестного типа

Если тип объекта не знается во время компиляции, необходимо использовать *позднее связывание* для любой переменной, ссылающейся на нее.

#### <a name="to-access-members-of-an-object-for-which-you-do-not-know-the-type-at-compile-time"></a>Доступ к членам объекта, тип которых не знается во время компиляции

1. Объявите переменную объекта для [типа данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md). (Объявление переменной как `Object` совпадает с ее объявлением как <xref:System.Object?displayProperty=nameWithType>.)

    ```vb
    Dim someControl As Object
    ```

    С `Option Strict On`помощью можно получить доступ только к тем элементам, которые определены <xref:System.Object> в классе.

2. Используйте оператор доступа к членам (`.`) между именем объектной переменной и именем члена.

    ```vb
    someControl.GetType()
    ```

    Чтобы иметь возможность доступа к членам любого объекта, назначаемого переменной объекта, необходимо задать `Option Strict Off`. При этом компилятор не может гарантировать, что данный элемент предоставляется объектом, назначаемым переменной. Если объект не предоставляет член, к которому вы пытаетесь получить доступ, <xref:System.MemberAccessException> возникает исключение.

## <a name="see-also"></a>См. также

- <xref:System.Object>
- <xref:System.Windows.Forms.Form>
- <xref:System.MemberAccessException>
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
