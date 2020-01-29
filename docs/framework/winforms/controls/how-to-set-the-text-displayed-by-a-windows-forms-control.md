---
title: Установка текста, отображаемого элементом управления
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: eb02cbc3b335b0d5856f786b21d1d202cf444211
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738423"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>Как задать текст, отображаемый элементом управления Windows Forms

Windows Forms элементы управления обычно отображают некоторый текст, связанный с основной функцией элемента управления. Например, элемент управления <xref:System.Windows.Forms.Button> обычно отображает заголовок, указывающий, какое действие будет выполнено при нажатии кнопки. С помощью свойства <xref:System.Windows.Forms.Control.Text%2A> можно задавать или получать текст для всех элементов управления. Шрифт можно менять с помощью свойства <xref:System.Windows.Forms.Control.Font%2A>.

Можно также задать текст с помощью [конструктора](#designer).

## <a name="programmatic"></a>Программ

1. Присвойте свойству <xref:System.Windows.Forms.Control.Text%2A> строку.

   Чтобы создать подчеркнутый ключ доступа, включает амперсанд (&) перед буквой, которая будет клавишей доступа.

2. Присвойте свойству <xref:System.Windows.Forms.Control.Font%2A> объект типа <xref:System.Drawing.Font>.

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > Для отображения в элементах пользовательского интерфейса, например пунктах меню, специальных символов, которые обычно интерпретируются в них по-другому, можно использовать escape-символ. Например, следующая строка кода задает текст пункта меню для чтения "& теперь для чего-то совершенно другого":

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a>Конструктор

1. В окне **Свойства** в Visual Studio задайте для свойства **Text** элемента управления соответствующую строку.

   Чтобы создать подчеркнутую клавишу, она включает амперсанд (&) перед буквой, которая будет клавишей быстрого вызова.

2. В окне **Свойства** нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio](./media/visual-studio-ellipsis-button.png)) рядом со свойством **Font** .

   В диалоговом окне стандартный шрифт выберите шрифт, стиль шрифта, размер, эффекты (например, зачеркивание или подчеркивание) и нужный сценарий.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md)
- [Практическое руководство. Обработка события нажатия кнопки в Windows Forms](how-to-respond-to-windows-forms-button-clicks.md)
