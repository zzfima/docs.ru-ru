---
title: Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms
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
ms.openlocfilehash: 887aa5ec9b97770903cd87459d6df5adc3f7ddf0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666155"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="f3bb2-102">Практическое руководство. Установка текста, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3bb2-102">How to: Set the text displayed by a Windows Forms control</span></span>

<span data-ttu-id="f3bb2-103">Windows Forms элементы управления обычно отображают некоторый текст, связанный с основной функцией элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f3bb2-103">Windows Forms controls usually display some text that's related to the primary function of the control.</span></span> <span data-ttu-id="f3bb2-104">Например, <xref:System.Windows.Forms.Button> элемент управления обычно отображает заголовок, указывающий, какое действие будет выполнено при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="f3bb2-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed if the button is clicked.</span></span> <span data-ttu-id="f3bb2-105">С помощью свойства <xref:System.Windows.Forms.Control.Text%2A> можно задавать или получать текст для всех элементов управления.</span><span class="sxs-lookup"><span data-stu-id="f3bb2-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="f3bb2-106">Шрифт можно менять с помощью свойства <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3bb2-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>

<span data-ttu-id="f3bb2-107">Можно также задать текст с помощью [конструктора](#designer).</span><span class="sxs-lookup"><span data-stu-id="f3bb2-107">You can also set the text by using the [designer](#designer).</span></span>

## <a name="programmatic"></a><span data-ttu-id="f3bb2-108">Программный</span><span class="sxs-lookup"><span data-stu-id="f3bb2-108">Programmatic</span></span>

1. <span data-ttu-id="f3bb2-109">Присвойте свойству <xref:System.Windows.Forms.Control.Text%2A> строку.</span><span class="sxs-lookup"><span data-stu-id="f3bb2-109">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>

   <span data-ttu-id="f3bb2-110">Чтобы создать подчеркнутый ключ доступа, включает амперсанд (&) перед буквой, которая будет клавишей доступа.</span><span class="sxs-lookup"><span data-stu-id="f3bb2-110">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>

2. <span data-ttu-id="f3bb2-111">Присвойте свойству <xref:System.Windows.Forms.Control.Font%2A> объект типа <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="f3bb2-111">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>

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
    > <span data-ttu-id="f3bb2-112">Для отображения в элементах пользовательского интерфейса, например пунктах меню, специальных символов, которые обычно интерпретируются в них по-другому, можно использовать escape-символ.</span><span class="sxs-lookup"><span data-stu-id="f3bb2-112">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="f3bb2-113">Например, следующая строка кода задает текст пункта меню для чтения "& теперь для чего-то совершенно другого":</span><span class="sxs-lookup"><span data-stu-id="f3bb2-113">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a><span data-ttu-id="f3bb2-114">Designer</span><span class="sxs-lookup"><span data-stu-id="f3bb2-114">Designer</span></span>

1. <span data-ttu-id="f3bb2-115">В окне **Свойства** в Visual Studio задайте для свойства **Text** элемента управления соответствующую строку.</span><span class="sxs-lookup"><span data-stu-id="f3bb2-115">In the **Properties** window in Visual Studio, set the **Text** property of the control to an appropriate string.</span></span>

   <span data-ttu-id="f3bb2-116">Чтобы создать подчеркнутую клавишу, она включает амперсанд (&) перед буквой, которая будет клавишей быстрого вызова.</span><span class="sxs-lookup"><span data-stu-id="f3bb2-116">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>

2. <span data-ttu-id="f3bb2-117">В окне **Свойства** нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio](./media/visual-studio-ellipsis-button.png)) рядом со свойством **Font** .</span><span class="sxs-lookup"><span data-stu-id="f3bb2-117">In the **Properties** window, select the ellipsis button (![Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) next to the **Font** property.</span></span>

   <span data-ttu-id="f3bb2-118">В диалоговом окне стандартный шрифт выберите шрифт, стиль шрифта, размер, эффекты (например, зачеркивание или подчеркивание) и нужный сценарий.</span><span class="sxs-lookup"><span data-stu-id="f3bb2-118">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3bb2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f3bb2-119">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f3bb2-120">Практическое руководство. Создание ключей доступа для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3bb2-120">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)
- [<span data-ttu-id="f3bb2-121">Практическое руководство. Реакция на нажатие кнопки Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3bb2-121">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
