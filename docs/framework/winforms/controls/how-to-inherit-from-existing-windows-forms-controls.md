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
ms.openlocfilehash: b0e0053816efde349c7e4d13d03bef5f8801c667
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849384"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="90a6c-102">Практическое руководство. Наследование существующих элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="90a6c-102">How to: Inherit from Existing Windows Forms Controls</span></span>

<span data-ttu-id="90a6c-103">Чтобы расширить функциональные возможности существующего элемента управления, можно создать элемент управления, производный от существующего элемента управления, путем наследования.</span><span class="sxs-lookup"><span data-stu-id="90a6c-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="90a6c-104">При наследовании из существующего элемента управления наследуются все его функциональные возможности и визуальные свойства.</span><span class="sxs-lookup"><span data-stu-id="90a6c-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="90a6c-105">Например, если вы создаете элемент <xref:System.Windows.Forms.Button>управления, который унаследовал от, ваш <xref:System.Windows.Forms.Button> новый элемент управления будет выглядеть и действовать точно так же, как стандартный элемент управления.</span><span class="sxs-lookup"><span data-stu-id="90a6c-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="90a6c-106">После этого вы сможете расширить или изменить функциональность нового элемента управления, реализовав пользовательские методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="90a6c-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="90a6c-107">В некоторых элементах управления вы также можете изменить внешний <xref:System.Windows.Forms.Control.OnPaint%2A> вид унаследованного элемента управления, переопределив его метод.</span><span class="sxs-lookup"><span data-stu-id="90a6c-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

## <a name="to-create-an-inherited-control"></a><span data-ttu-id="90a6c-108">Создание наследуемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="90a6c-108">To create an inherited control</span></span>

1. <span data-ttu-id="90a6c-109">В Visual Studio создайте новый проект **приложения Windows Forms.**</span><span class="sxs-lookup"><span data-stu-id="90a6c-109">In Visual Studio, create a new **Windows Forms Application** project.</span></span>

1. <span data-ttu-id="90a6c-110">В меню **Проект** выберите команду **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="90a6c-110">From the **Project** menu, choose **Add New Item**.</span></span>

    <span data-ttu-id="90a6c-111">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="90a6c-111">The **Add New Item** dialog box appears.</span></span>

1. <span data-ttu-id="90a6c-112">В диалоговом окне **Добавление нового элемента** дважды щелкните пункт **Пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="90a6c-112">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>

    <span data-ttu-id="90a6c-113">В ваш проект будет добавлен новый пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="90a6c-113">A new custom control is added to your project.</span></span>

1. <span data-ttu-id="90a6c-114">Если вы используете:</span><span class="sxs-lookup"><span data-stu-id="90a6c-114">If you're using:</span></span>

    - <span data-ttu-id="90a6c-115">Визуальный основной, в верхней части **решения Explorer**, нажмите Показать **все файлы**.</span><span class="sxs-lookup"><span data-stu-id="90a6c-115">Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="90a6c-116">Разверните папку CustomControl1.vb и откройте файл CustomControl1.Designer.vb в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="90a6c-116">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>
    - <span data-ttu-id="90a6c-117">С CustomControl1.cs.</span><span class="sxs-lookup"><span data-stu-id="90a6c-117">C#, open CustomControl1.cs in the Code Editor.</span></span>

1. <span data-ttu-id="90a6c-118">Найдите классную декларацию, <xref:System.Windows.Forms.Control>которая наследует ся.</span><span class="sxs-lookup"><span data-stu-id="90a6c-118">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>

1. <span data-ttu-id="90a6c-119">Измените базовый класс для элемента управления, который нужно использовать для наследования.</span><span class="sxs-lookup"><span data-stu-id="90a6c-119">Change the base class to the control that you want to inherit from.</span></span>

     <span data-ttu-id="90a6c-120">Например, если вы хотите <xref:System.Windows.Forms.Button>унаследовать от, измените декларацию класса на следующее:</span><span class="sxs-lookup"><span data-stu-id="90a6c-120">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. <span data-ttu-id="90a6c-121">Если используется Visual Basic, сохраните и закройте файл CustomControl1.Designer.vb.</span><span class="sxs-lookup"><span data-stu-id="90a6c-121">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="90a6c-122">Откройте файл CustomControl1.vb в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="90a6c-122">Open CustomControl1.vb in the Code Editor.</span></span>

1. <span data-ttu-id="90a6c-123">Реализуйте необходимые пользовательские методы или свойства, которые будут входить в ваш элемент управления.</span><span class="sxs-lookup"><span data-stu-id="90a6c-123">Implement any custom methods or properties that your control will incorporate.</span></span>

1. <span data-ttu-id="90a6c-124">Если вы хотите изменить графический внешний вид <xref:System.Windows.Forms.Control.OnPaint%2A> элемента управления, переопределить метод.</span><span class="sxs-lookup"><span data-stu-id="90a6c-124">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

    > [!NOTE]
    > <span data-ttu-id="90a6c-125">Переопределение <xref:System.Windows.Forms.Control.OnPaint%2A> не позволит вам изменить внешний вид всех элементов управления.</span><span class="sxs-lookup"><span data-stu-id="90a6c-125">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="90a6c-126">Те элементы управления, которые имеют все свои <xref:System.Windows.Forms.TextBox>картины, <xref:System.Windows.Forms.Control.OnPaint%2A> сделанные Windows (например, ) никогда не называют их метод, и, таким образом, никогда не будет использовать пользовательский код.</span><span class="sxs-lookup"><span data-stu-id="90a6c-126">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="90a6c-127">Обратитесь к документации справки для конкретного элемента управления, который вы хотите изменить, чтобы увидеть, доступен ли <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="90a6c-127">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="90a6c-128">Список всех элементов управления Windows Forms см. в разделе [Элементы управления для использования в формах Windows Forms](controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="90a6c-128">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="90a6c-129">Если элемент управления <xref:System.Windows.Forms.Control.OnPaint%2A> не указан в качестве элемента, вы не можете изменить его внешний вид, переопределив этот метод.</span><span class="sxs-lookup"><span data-stu-id="90a6c-129">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="90a6c-130">Дополнительные сведения о пользовательском оформлении см. в разделе [Рисование и отрисовка пользовательского элемента управления](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="90a6c-130">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

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

1. <span data-ttu-id="90a6c-131">Сохраните и проверьте элемент управления.</span><span class="sxs-lookup"><span data-stu-id="90a6c-131">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="90a6c-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="90a6c-132">See also</span></span>

- [<span data-ttu-id="90a6c-133">Создание собственных элементов управления</span><span class="sxs-lookup"><span data-stu-id="90a6c-133">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="90a6c-134">Практическое руководство. Наследование класса Control</span><span class="sxs-lookup"><span data-stu-id="90a6c-134">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="90a6c-135">Практическое руководство. Наследование класса UserControl.</span><span class="sxs-lookup"><span data-stu-id="90a6c-135">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="90a6c-136">Практическое руководство. Создание элементов управления для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="90a6c-136">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="90a6c-137">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90a6c-137">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="90a6c-138">Пошаговая прогулка: Наследование от управления формами Windows</span><span class="sxs-lookup"><span data-stu-id="90a6c-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
