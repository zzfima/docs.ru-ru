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
ms.openlocfilehash: 900a955173c28c7b86fce73e418561ed437719c4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216929"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="72892-102">Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="72892-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="72892-103">*Ключ доступа* , подчеркивается в тексте элемента меню, пункт меню или метка элемента управления, такого как кнопка.</span><span class="sxs-lookup"><span data-stu-id="72892-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="72892-104">Он позволяет пользователю «click» кнопки с помощью клавиши ALT и клавишу с буквой.</span><span class="sxs-lookup"><span data-stu-id="72892-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="72892-105">Например, если кнопка запускает процесс печати формы и поэтому его `Text` свойство имеет значение «Print», добавив символ амперсанда (&) перед буквой «P» буква «P» быть подчеркнуты в тексте кнопки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="72892-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="72892-106">Пользователь может выполнять команда, связанная с кнопкой, нажав клавиши ALT + P.</span><span class="sxs-lookup"><span data-stu-id="72892-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="72892-107">Не может иметь ключ доступа для элемента управления, который не может получить фокус.</span><span class="sxs-lookup"><span data-stu-id="72892-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72892-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="72892-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="72892-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="72892-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="72892-110">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="72892-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="72892-111">Чтобы создать ключ доступа для элемента управления</span><span class="sxs-lookup"><span data-stu-id="72892-111">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="72892-112">В **свойства** окне `Text` свойство на строку, которая включает знак амперсанда (&) перед буквой, которая будет использоваться ключ доступа.</span><span class="sxs-lookup"><span data-stu-id="72892-112">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="72892-113">Например, чтобы задать буква «P» как клавиша доступа, введите **& Печать** в сетку.</span><span class="sxs-lookup"><span data-stu-id="72892-113">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72892-114">См. также</span><span class="sxs-lookup"><span data-stu-id="72892-114">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="72892-115">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72892-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="72892-116">Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72892-116">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="72892-117">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="72892-117">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
