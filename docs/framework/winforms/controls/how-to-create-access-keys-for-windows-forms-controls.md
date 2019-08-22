---
title: Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms
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
ms.openlocfilehash: ccec8bba9e01cbaa7bfef841af68a0fcaa720b90
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658376"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="15802-102">Практическое руководство. Создание ключей доступа для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15802-102">How to: Create access keys for Windows Forms controls</span></span>

<span data-ttu-id="15802-103">*Клавиша доступа* — это подчеркнутый символ в тексте меню, пункте меню или метка элемента управления, например кнопка.</span><span class="sxs-lookup"><span data-stu-id="15802-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="15802-104">С помощью ключа доступа пользователь может «нажать» кнопку, нажав клавишу Alt в сочетании с предопределенной клавишей доступа.</span><span class="sxs-lookup"><span data-stu-id="15802-104">With an access key, the user can "click" a button by pressing the Alt key in combination with the predefined access key.</span></span> <span data-ttu-id="15802-105">Например, если кнопка запускает процедуру печати формы, и, следовательно, ее `Text` свойство имеет значение "Print", добавление амперсанда перед буквой "p" приводит к тому, что буква "p" будет подчеркнута в тексте кнопки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="15802-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="15802-106">Пользователь может выполнить команду, связанную с кнопкой, нажав клавиши ALT + P.</span><span class="sxs-lookup"><span data-stu-id="15802-106">The user can run the command associated with the button by pressing Alt+P.</span></span>

<span data-ttu-id="15802-107">Элементы управления, которые не могут получать фокус, не могут иметь ключи доступа.</span><span class="sxs-lookup"><span data-stu-id="15802-107">Controls that cannot receive focus can't have access keys.</span></span>

## <a name="programmatic"></a><span data-ttu-id="15802-108">Программный</span><span class="sxs-lookup"><span data-stu-id="15802-108">Programmatic</span></span>

<span data-ttu-id="15802-109">Задайте для `Text` свойства строку, содержащую амперсанд (&) перед буквой, которая будет ярлыком.</span><span class="sxs-lookup"><span data-stu-id="15802-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>

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
> <span data-ttu-id="15802-110">Чтобы использовать амперсанд в заголовке без создания ключа доступа, включите два амперсанда (& &).</span><span class="sxs-lookup"><span data-stu-id="15802-110">To use an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="15802-111">В заголовке отображается один амперсанд, а символы не подчеркиваются.</span><span class="sxs-lookup"><span data-stu-id="15802-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>

## <a name="designer"></a><span data-ttu-id="15802-112">Designer</span><span class="sxs-lookup"><span data-stu-id="15802-112">Designer</span></span>

<span data-ttu-id="15802-113">В окне **Свойства** Visual Studio присвойте свойству **Text** значение String, включающее амперсанд (' & ') перед буквой, которая будет клавишей доступа.</span><span class="sxs-lookup"><span data-stu-id="15802-113">In the **Properties** window of Visual Studio, set the **Text** property to a string that includes an ampersand ('&') before the letter that will be the access key.</span></span> <span data-ttu-id="15802-114">Например, чтобы задать букву "P" в качестве клавиши доступа, введите **& Print**.</span><span class="sxs-lookup"><span data-stu-id="15802-114">For example, to set the letter "P" as the access key, enter **&Print**.</span></span>

## <a name="see-also"></a><span data-ttu-id="15802-115">См. также</span><span class="sxs-lookup"><span data-stu-id="15802-115">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="15802-116">Практическое руководство. Реакция на нажатие кнопки Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15802-116">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="15802-117">Практическое руководство. Установка текста, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15802-117">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="15802-118">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15802-118">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
