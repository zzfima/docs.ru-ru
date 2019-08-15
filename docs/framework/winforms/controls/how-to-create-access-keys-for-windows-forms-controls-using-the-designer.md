---
title: Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 01bed04483702ba2e62162b675aa1138bc1b0e01
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039519"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms с помощью конструктора
*Клавиша доступа* — это подчеркнутый символ в тексте меню, пункте меню или метка элемента управления, например кнопка. Он позволяет пользователю "нажать" кнопку, нажав клавишу ALT в сочетании с предопределенной клавишей доступа. Например, если кнопка запускает процедуру печати формы, и, следовательно, ее `Text` свойство имеет значение "Print", добавление амперсанда (&) перед буквой "p" приводит к тому, что буква "p" будет подчеркнута в тексте кнопки во время выполнения. Пользователь может выполнить команду, связанную с кнопкой, нажав клавиши ALT + P. Нельзя использовать ключ доступа для элемента управления, который не может получить фокус.

## <a name="to-create-an-access-key-for-a-control"></a>Создание ключа доступа для элемента управления

1. В окне **Свойства** задайте `Text` для свойства строку, содержащую амперсанд (&) перед буквой, которая будет клавишей доступа. Например, чтобы задать букву "P" в качестве клавиши доступа, введите **& печати** в сетку.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.Button>
- [Практическое руководство. Реакция на нажатие кнопки Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
- [Практическое руководство. Установка текста, отображаемого элементом управления Windows Forms](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
