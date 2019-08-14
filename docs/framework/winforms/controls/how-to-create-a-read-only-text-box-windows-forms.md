---
title: Практическое руководство. Создание текстового поля, доступного только для чтения (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 18d2f5ed2530957487ac25c3eb6240f8bc50a938
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971946"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Практическое руководство. Создание текстового поля, доступного только для чтения (Windows Forms)

Можно преобразовать редактируемое Windows Forms текстовое поле в элемент управления только для чтения. Например, текстовое поле может отображать значение, которое обычно редактируется, но может не быть в данный момент из-за состояния приложения.

## <a name="to-create-a-read-only-text-box"></a>Создание текстового поля, доступного только для чтения

1. Присвойте <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> свойству <xref:System.Windows.Forms.TextBox> элемента управления значение `true`. Если свойство имеет значение `true`, пользователи по-прежнему могут прокручивать и выделять текст в текстовом поле, не разрешая изменения. Команда **копирования** работает в текстовом поле, но команды вырезания и **вставки** не используются.

    > [!NOTE]
    > <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Свойство влияет только на взаимодействие с пользователем во время выполнения. Вы по-прежнему можете изменить содержимое текстового поля программно во время выполнения <xref:System.Windows.Forms.TextBox.Text%2A> , изменив свойство текстового поля.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.TextBox>
- [Общие сведения об элементе управления TextBox](textbox-control-overview-windows-forms.md)
- [Практическое руководство. Управление точкой вставки в элементе управления TextBox Windows Forms](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Практическое руководство. Создание текстового поля пароля с помощью элемента управления TextBox Windows Forms](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Практическое руководство. Заключить кавычки в строку](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Практическое руководство. Выделение текста в элементе управления TextBox Windows Forms](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Практическое руководство. Просмотр нескольких строк в элементе управления TextBox Windows Forms](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [Элемент управления TextBox](textbox-control-windows-forms.md)
