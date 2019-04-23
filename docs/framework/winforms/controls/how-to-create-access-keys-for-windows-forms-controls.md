---
title: Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms
ms.date: 03/30/2017
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
ms.openlocfilehash: e6c829553163359301bad2cd896fc43562ee8069
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334462"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="80d4a-102">Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80d4a-102">How to: Create Access Keys for Windows Forms Controls</span></span>
<span data-ttu-id="80d4a-103">*Ключ доступа* , подчеркивается в тексте элемента меню, пункт меню или метка элемента управления, такого как кнопка.</span><span class="sxs-lookup"><span data-stu-id="80d4a-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="80d4a-104">С помощью ключа доступа пользователь может «щелкните» кнопки с помощью клавиши ALT и клавишу с буквой.</span><span class="sxs-lookup"><span data-stu-id="80d4a-104">With an access key, the user can "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="80d4a-105">Например, если кнопка запускает процесс печати формы и поэтому его `Text` свойство имеет значение «Print», добавив амперсанд перед буквой «P» приводит к буква «P» будет подчеркнут в тексте кнопки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="80d4a-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="80d4a-106">Пользователь может выполнять команда, связанная с кнопкой, нажав клавиши ALT + P.</span><span class="sxs-lookup"><span data-stu-id="80d4a-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="80d4a-107">Не может иметь ключ доступа для элемента управления, который не может получить фокус.</span><span class="sxs-lookup"><span data-stu-id="80d4a-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="80d4a-108">Чтобы создать ключ доступа для элемента управления</span><span class="sxs-lookup"><span data-stu-id="80d4a-108">To create an access key for a control</span></span>  
  
1. <span data-ttu-id="80d4a-109">Задайте `Text` свойство на строку, которая включает знак амперсанда (&) перед буквой, которая будет использоваться в сочетании клавиш.</span><span class="sxs-lookup"><span data-stu-id="80d4a-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>  
  
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
    >  <span data-ttu-id="80d4a-110">Чтобы включить знак амперсанда в захвате без создания ключа доступа, добавьте два амперсанда (& &).</span><span class="sxs-lookup"><span data-stu-id="80d4a-110">To include an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="80d4a-111">Один знак амперсанда отображается в заголовке, и никакие символы не будут подчеркнуты.</span><span class="sxs-lookup"><span data-stu-id="80d4a-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80d4a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="80d4a-112">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="80d4a-113">Практическое руководство. Ответ на нажатие кнопки Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80d4a-113">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="80d4a-114">Практическое руководство. Задать текст, отображаемый элементом управления форм Windows</span><span class="sxs-lookup"><span data-stu-id="80d4a-114">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="80d4a-115">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80d4a-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
