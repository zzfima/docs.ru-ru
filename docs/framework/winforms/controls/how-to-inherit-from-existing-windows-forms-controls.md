---
title: Наследование от существующих элементов управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d0025ba136698c0a74a73e64a83fa4f526e44843
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736480"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="35b8a-102">Практическое руководство. Наследование существующих элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35b8a-102">How to: Inherit from Existing Windows Forms Controls</span></span>

<span data-ttu-id="35b8a-103">Чтобы расширить функциональные возможности существующего элемента управления, можно создать элемент управления, производный от существующего элемента управления, путем наследования.</span><span class="sxs-lookup"><span data-stu-id="35b8a-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="35b8a-104">При наследовании из существующего элемента управления наследуются все его функциональные возможности и визуальные свойства.</span><span class="sxs-lookup"><span data-stu-id="35b8a-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="35b8a-105">Например, если вы создавали элемент управления, наследуемый от <xref:System.Windows.Forms.Button>, новый элемент управления будет выглядеть и работать точно так же, как и стандартный элемент управления <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="35b8a-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="35b8a-106">После этого вы сможете расширить или изменить функциональность нового элемента управления, реализовав пользовательские методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="35b8a-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="35b8a-107">В некоторых элементах управления можно также изменить внешний вид наследуемого элемента управления, переопределив его метод <xref:System.Windows.Forms.Control.OnPaint%2A>.</span><span class="sxs-lookup"><span data-stu-id="35b8a-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

## <a name="to-create-an-inherited-control"></a><span data-ttu-id="35b8a-108">Создание наследуемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="35b8a-108">To create an inherited control</span></span>

1. <span data-ttu-id="35b8a-109">В Visual Studio создайте новый проект **приложения Windows Forms** .</span><span class="sxs-lookup"><span data-stu-id="35b8a-109">In Visual Studio, create a new **Windows Forms Application** project.</span></span>

1. <span data-ttu-id="35b8a-110">В меню **Проект** выберите команду **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="35b8a-110">From the **Project** menu, choose **Add New Item**.</span></span>

    <span data-ttu-id="35b8a-111">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="35b8a-111">The **Add New Item** dialog box appears.</span></span>

1. <span data-ttu-id="35b8a-112">В диалоговом окне **Добавление нового элемента** дважды щелкните пункт **Пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="35b8a-112">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>

    <span data-ttu-id="35b8a-113">В ваш проект будет добавлен новый пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="35b8a-113">A new custom control is added to your project.</span></span>

1. <span data-ttu-id="35b8a-114">При использовании:</span><span class="sxs-lookup"><span data-stu-id="35b8a-114">If you using:</span></span>

    - <span data-ttu-id="35b8a-115">Visual Basic в верхней части **Обозреватель решений**щелкните " **отобразить все файлы**".</span><span class="sxs-lookup"><span data-stu-id="35b8a-115">Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="35b8a-116">Разверните папку CustomControl1.vb и откройте файл CustomControl1.Designer.vb в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="35b8a-116">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>
    - <span data-ttu-id="35b8a-117">C#Откройте CustomControl1.cs в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="35b8a-117">C#, open CustomControl1.cs in the Code Editor.</span></span>

1. <span data-ttu-id="35b8a-118">Нахождение объявления класса, наследуемого от <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="35b8a-118">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>

1. <span data-ttu-id="35b8a-119">Измените базовый класс для элемента управления, который нужно использовать для наследования.</span><span class="sxs-lookup"><span data-stu-id="35b8a-119">Change the base class to the control that you want to inherit from.</span></span>

     <span data-ttu-id="35b8a-120">Например, если необходимо наследовать от <xref:System.Windows.Forms.Button>, измените объявление класса следующим образом:</span><span class="sxs-lookup"><span data-stu-id="35b8a-120">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. <span data-ttu-id="35b8a-121">Если используется Visual Basic, сохраните и закройте файл CustomControl1.Designer.vb.</span><span class="sxs-lookup"><span data-stu-id="35b8a-121">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="35b8a-122">Откройте файл CustomControl1.vb в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="35b8a-122">Open CustomControl1.vb in the Code Editor.</span></span>

1. <span data-ttu-id="35b8a-123">Реализуйте необходимые пользовательские методы или свойства, которые будут входить в ваш элемент управления.</span><span class="sxs-lookup"><span data-stu-id="35b8a-123">Implement any custom methods or properties that your control will incorporate.</span></span>

1. <span data-ttu-id="35b8a-124">Если вы хотите изменить графический внешний вид элемента управления, переопределите метод <xref:System.Windows.Forms.Control.OnPaint%2A>.</span><span class="sxs-lookup"><span data-stu-id="35b8a-124">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

    > [!NOTE]
    > <span data-ttu-id="35b8a-125">Переопределение <xref:System.Windows.Forms.Control.OnPaint%2A> не позволит изменять внешний вид всех элементов управления.</span><span class="sxs-lookup"><span data-stu-id="35b8a-125">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="35b8a-126">Эти элементы управления, которые выполняются в Windows (например, <xref:System.Windows.Forms.TextBox>), никогда не вызывают свой метод <xref:System.Windows.Forms.Control.OnPaint%2A> и, таким образом, никогда не будут использовать пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="35b8a-126">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="35b8a-127">Чтобы узнать, доступен ли метод <xref:System.Windows.Forms.Control.OnPaint%2A>, обратитесь к справочной документации по конкретному элементу управления, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="35b8a-127">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="35b8a-128">Список всех элементов управления Windows Forms см. в разделе [Элементы управления для использования в формах Windows Forms](controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="35b8a-128">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="35b8a-129">Если элемент управления не имеет <xref:System.Windows.Forms.Control.OnPaint%2A> указан как метод члена, его внешний вид нельзя изменить, переопределив этот метод.</span><span class="sxs-lookup"><span data-stu-id="35b8a-129">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="35b8a-130">Дополнительные сведения о пользовательском оформлении см. в разделе [Рисование и отрисовка пользовательского элемента управления](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="35b8a-130">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. <span data-ttu-id="35b8a-131">Сохраните и проверьте элемент управления.</span><span class="sxs-lookup"><span data-stu-id="35b8a-131">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="35b8a-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="35b8a-132">See also</span></span>

- [<span data-ttu-id="35b8a-133">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="35b8a-133">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="35b8a-134">Практическое руководство. Наследование класса Control</span><span class="sxs-lookup"><span data-stu-id="35b8a-134">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="35b8a-135">Практическое руководство. Наследование класса UserControl</span><span class="sxs-lookup"><span data-stu-id="35b8a-135">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="35b8a-136">Практическое руководство. Создание элементов управления для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35b8a-136">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="35b8a-137">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="35b8a-137">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="35b8a-138">Пошаговое руководство. наследование от элемента управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="35b8a-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
