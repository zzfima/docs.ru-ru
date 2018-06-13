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
ms.openlocfilehash: 023973e7fa4ab1e8b802d8c7cd8abef8201ed720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532555"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a><span data-ttu-id="909a9-102">Практическое руководство. Определение клавиш доступа для элементов управления Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="909a9-102">How to: Create Access Keys for Windows Forms Controls Using the Designer</span></span>
<span data-ttu-id="909a9-103">*Ключ доступа* — это подчеркнутый символ в тексте меню, пункт меню или метки элемента управления, например кнопки.</span><span class="sxs-lookup"><span data-stu-id="909a9-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="909a9-104">Он позволяет пользователю «нажмите кнопку» с помощью клавиши ALT и клавишу с буквой.</span><span class="sxs-lookup"><span data-stu-id="909a9-104">It enables the user to "click" a button by pressing the ALT key in combination with the predefined access key.</span></span> <span data-ttu-id="909a9-105">Например, если кнопка запускает процесс печати формы и, следовательно, его `Text` свойство имеет значение «Print», добавив амперсанд (&) перед буквой «P» буква «P» подчеркнуть в тексте кнопки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="909a9-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand (&) before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="909a9-106">Пользователь может запускать команды, связанные с кнопкой, нажав сочетание клавиш ALT + P.</span><span class="sxs-lookup"><span data-stu-id="909a9-106">The user can run the command associated with the button by pressing ALT+P.</span></span> <span data-ttu-id="909a9-107">Не может иметь клавишу доступа для элемента управления, который не может получить фокус.</span><span class="sxs-lookup"><span data-stu-id="909a9-107">You cannot have an access key for a control that cannot receive focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="909a9-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="909a9-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="909a9-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="909a9-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="909a9-110">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="909a9-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-an-access-key-for-a-control"></a><span data-ttu-id="909a9-111">Чтобы создать сочетание клавиш для элемента управления</span><span class="sxs-lookup"><span data-stu-id="909a9-111">To create an access key for a control</span></span>  
  
1.  <span data-ttu-id="909a9-112">В **свойства** задайте `Text` свойства в строку, содержащую знак амперсанда (&) перед буквой, которая будет использоваться в сочетании клавиш.</span><span class="sxs-lookup"><span data-stu-id="909a9-112">In the **Properties** window, set the `Text` property to a string that includes an ampersand (&) before the letter that will be the access key.</span></span> <span data-ttu-id="909a9-113">Например, чтобы задать буквы «P» как клавиша доступа, введите **& Печать** в сетку.</span><span class="sxs-lookup"><span data-stu-id="909a9-113">For example, to set the letter "P" as the access key, type **&Print** into the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="909a9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="909a9-114">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="909a9-115">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="909a9-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="909a9-116">Практическое руководство. Определение текста, отображаемого элементом управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="909a9-116">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="909a9-117">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="909a9-117">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
