---
title: Создание ключей доступа для элементов управления
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: 7f6b0a5838cacfc1189fba819a54b3423d567ea0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731168"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>Руководство. Создание ключей доступа для элементов управления Windows Forms

*Клавиша доступа* — это подчеркнутый символ в тексте меню, пункте меню или метка элемента управления, например кнопка. С помощью ключа доступа пользователь может «нажать» кнопку, нажав клавишу Alt в сочетании с предопределенной клавишей доступа. Например, если кнопка запускает процедуру печати формы, и, следовательно, ее свойство `Text` имеет значение «Print», то добавление амперсанда перед буквой «P» приводит к тому, что буква «P» будет подчеркнута в тексте кнопки во время выполнения. Пользователь может выполнить команду, связанную с кнопкой, нажав клавиши ALT + P.

Элементы управления, которые не могут получать фокус, не могут иметь ключи доступа.

## <a name="programmatic"></a>Программный

Задайте для свойства `Text` строку, содержащую амперсанд (&) перед буквой, которая будет ярлыком.

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

```cpp
// Set the letter "P" as an access key.
button1->Text = "&Print";
```

> [!NOTE]
> Чтобы использовать амперсанд в заголовке без создания ключа доступа, включите два амперсанда (& &). В заголовке отображается один амперсанд, а символы не подчеркиваются.

## <a name="designer"></a>Конструктор

В окне **Свойства** Visual Studio присвойте свойству **Text** значение String, включающее амперсанд (' & ') перед буквой, которая будет клавишей доступа. Например, чтобы задать букву "P" в качестве клавиши доступа, введите **& Print**.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Button>
- [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
