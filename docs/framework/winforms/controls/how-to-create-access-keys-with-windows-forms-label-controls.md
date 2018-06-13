---
title: Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: fc9592981f3d926b2b5b85b6869da13dc644e7a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530807"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="a000d-102">Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a000d-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="a000d-103">Windows Forms <xref:System.Windows.Forms.Label> элементы управления можно использовать для определения клавиши доступа для других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a000d-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="a000d-104">При определении клавиши доступа в элементе управления label, пользователь может нажать клавишу ALT в сочетании с символом, передать фокус элементу управления, следующему в последовательности табуляции.</span><span class="sxs-lookup"><span data-stu-id="a000d-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="a000d-105">Поскольку метки не может получать фокус, фокус автоматически перемещается к следующему элементу управления в последовательности табуляции.</span><span class="sxs-lookup"><span data-stu-id="a000d-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="a000d-106">Этот метод используется для присвоения ключи доступа для текстовых полей, поля со списком, списки и таблицы данных.</span><span class="sxs-lookup"><span data-stu-id="a000d-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="a000d-107">Чтобы назначить клавиши доступа к элементу управления с меткой</span><span class="sxs-lookup"><span data-stu-id="a000d-107">To assign an access key to a control with a label</span></span>  
  
1.  <span data-ttu-id="a000d-108">Сначала нарисуйте метку, а затем другого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a000d-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="a000d-109">- или -</span><span class="sxs-lookup"><span data-stu-id="a000d-109">-or-</span></span>  
  
     <span data-ttu-id="a000d-110">Нарисуйте элементы управления в любом порядке и задайте <xref:System.Windows.Forms.Control.TabIndex%2A> свойство метки на единицу меньше, чем у элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a000d-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2.  <span data-ttu-id="a000d-111">Задайте для свойства label <xref:System.Windows.Forms.Label.UseMnemonic%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="a000d-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="a000d-112">Используйте амперсанд (&) в метке <xref:System.Windows.Forms.Label.Text%2A> свойства, которому назначается ключ доступа для метки.</span><span class="sxs-lookup"><span data-stu-id="a000d-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="a000d-113">Дополнительные сведения см. в разделе [Создание сочетаний клавиш для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="a000d-113">For more information, see [Creating Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a000d-114">Может потребоваться отобразить амперсанды в элементе управления label, а не использовать их для создания ключей доступа.</span><span class="sxs-lookup"><span data-stu-id="a000d-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="a000d-115">Это может произойти, если элемент управления label привязан к полю в наборе записей, включающем амперсанды.</span><span class="sxs-lookup"><span data-stu-id="a000d-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="a000d-116">Для отображения в элементе управления label амперсанды <xref:System.Windows.Forms.Label.UseMnemonic%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="a000d-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="a000d-117">Если вы хотите отобразить амперсанды и назначить клавишу доступа, установите <xref:System.Windows.Forms.Label.UseMnemonic%2A> свойства `true` и укажите клавишу доступа с помощью одного амперсанда (&) и знак для отображения с помощью двух знаков амперсанда.</span><span class="sxs-lookup"><span data-stu-id="a000d-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a000d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a000d-118">See Also</span></span>  
 [<span data-ttu-id="a000d-119">Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a000d-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [<span data-ttu-id="a000d-120">Общие сведения об элементе управления Label</span><span class="sxs-lookup"><span data-stu-id="a000d-120">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="a000d-121">Элемент управления Label</span><span class="sxs-lookup"><span data-stu-id="a000d-121">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
