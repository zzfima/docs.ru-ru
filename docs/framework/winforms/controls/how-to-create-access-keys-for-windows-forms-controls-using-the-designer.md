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
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="7e6b1-102">Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="7e6b1-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="7e6b1-103">*Клавиша доступа* — это подчеркнутый символ в тексте меню, пункте меню или метка элемента управления, например кнопка.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="7e6b1-104">Он позволяет пользователю "нажать" кнопку, нажав клавишу ALT в сочетании с предопределенной клавишей доступа.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="7e6b1-105">Например, если кнопка запускает процедуру печати формы, и, следовательно, ее `Text` свойство имеет значение "Print", добавление амперсанда (&) перед буквой "p" приводит к тому, что буква "p" будет подчеркнута в тексте кнопки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="7e6b1-106">Пользователь может выполнить команду, связанную с кнопкой, нажав клавиши ALT + P.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="7e6b1-107">Нельзя использовать ключ доступа для элемента управления, который не может получить фокус.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-107">You cannot have an access key for a control that cannot receive focus.</span></span>

## <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="7e6b1-108">Создание ключа доступа для элемента управления</span><span class="sxs-lookup"><span data-stu-id="7e6b1-108">To create an access key for a control</span></span>

1. <span data-ttu-id="7e6b1-109">В окне **Свойства** задайте `Text` для свойства строку, содержащую амперсанд (&) перед буквой, которая будет клавишей доступа.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-109">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="7e6b1-110">Например, чтобы задать букву "P" в качестве клавиши доступа, введите **& печати** в сетку.</span><span class="sxs-lookup"><span data-stu-id="7e6b1-110">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>

## <a name="see-also"></a><span data-ttu-id="7e6b1-111">См. также</span><span class="sxs-lookup"><span data-stu-id="7e6b1-111">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="7e6b1-112">Практическое руководство. Реакция на нажатие кнопки Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7e6b1-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="7e6b1-113">Практическое руководство. Установка текста, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7e6b1-113">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="7e6b1-114">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7e6b1-114">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
