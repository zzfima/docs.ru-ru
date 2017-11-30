---
title: "Практическое руководство. Наследование существующих элементов управления Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6e6133576d65e95ac42a1680de152d84892e2c5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="1be14-102">Практическое руководство. Наследование существующих элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1be14-102">How to: Inherit from Existing Windows Forms Controls</span></span>
<span data-ttu-id="1be14-103">Чтобы расширить функциональные возможности существующего элемента управления, можно создать элемент управления, производный от существующего элемента управления, путем наследования.</span><span class="sxs-lookup"><span data-stu-id="1be14-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="1be14-104">При наследовании из существующего элемента управления наследуются все его функциональные возможности и визуальные свойства.</span><span class="sxs-lookup"><span data-stu-id="1be14-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="1be14-105">Например, при создании элемента управления, который наследуется от <xref:System.Windows.Forms.Button>, новый элемент управления будет выглядеть и act, так же, как стандартный <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1be14-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="1be14-106">После этого вы сможете расширить или изменить функциональность нового элемента управления, реализовав пользовательские методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="1be14-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="1be14-107">В некоторых элементах управления можно также изменить внешний вид наследуемого элемента управления путем переопределения его <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1be14-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1be14-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="1be14-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1be14-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="1be14-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1be14-110">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="1be14-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-an-inherited-control"></a><span data-ttu-id="1be14-111">Создание наследуемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="1be14-111">To create an inherited control</span></span>  
  
1.  <span data-ttu-id="1be14-112">Создайте проект **приложения Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="1be14-112">Create a new **Windows Forms Application** project.</span></span>  
  
2.  <span data-ttu-id="1be14-113">В меню **Проект** выберите команду **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="1be14-113">From the **Project** menu, choose **Add New Item**.</span></span>  
  
     <span data-ttu-id="1be14-114">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="1be14-114">The **Add New Item** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="1be14-115">В диалоговом окне **Добавление нового элемента** дважды щелкните пункт **Пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="1be14-115">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>  
  
     <span data-ttu-id="1be14-116">В ваш проект будет добавлен новый пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1be14-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="1be14-117">Если используется Visual Basic, в верхней части окна **Обозреватель решений** щелкните параметр **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="1be14-117">If you using Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="1be14-118">Разверните папку CustomControl1.vb и откройте файл CustomControl1.Designer.vb в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="1be14-118">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>  
  
5.  <span data-ttu-id="1be14-119">Если используется C#, откройте в редакторе кода файл CustomControl1.cs.</span><span class="sxs-lookup"><span data-stu-id="1be14-119">If you are using C#, open CustomControl1.cs in the Code Editor.</span></span>  
  
6.  <span data-ttu-id="1be14-120">Найдите объявление класса, который наследуется от <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="1be14-120">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>  
  
7.  <span data-ttu-id="1be14-121">Измените базовый класс для элемента управления, который нужно использовать для наследования.</span><span class="sxs-lookup"><span data-stu-id="1be14-121">Change the base class to the control that you want to inherit from.</span></span>  
  
     <span data-ttu-id="1be14-122">Например, если вы хотите наследовать <xref:System.Windows.Forms.Button>, измените объявление класса следующим:</span><span class="sxs-lookup"><span data-stu-id="1be14-122">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  <span data-ttu-id="1be14-123">Если используется Visual Basic, сохраните и закройте файл CustomControl1.Designer.vb.</span><span class="sxs-lookup"><span data-stu-id="1be14-123">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="1be14-124">Откройте файл CustomControl1.vb в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="1be14-124">Open CustomControl1.vb in the Code Editor.</span></span>  
  
9. <span data-ttu-id="1be14-125">Реализуйте необходимые пользовательские методы или свойства, которые будут входить в ваш элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1be14-125">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
10. <span data-ttu-id="1be14-126">Если вы хотите изменить графический интерфейс элемента управления, переопределите <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1be14-126">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1be14-127">Переопределение <xref:System.Windows.Forms.Control.OnPaint%2A> не позволяют изменять внешний вид всех элементов управления.</span><span class="sxs-lookup"><span data-stu-id="1be14-127">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="1be14-128">Элементы управления, оформленные средствами Windows (например, <xref:System.Windows.Forms.TextBox>) никогда не вызывать их <xref:System.Windows.Forms.Control.OnPaint%2A> метода и потому не используйте собственный код.</span><span class="sxs-lookup"><span data-stu-id="1be14-128">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="1be14-129">См. в справочной документации по конкретным элементом управления, требуется ли изменить <xref:System.Windows.Forms.Control.OnPaint%2A> метод доступен.</span><span class="sxs-lookup"><span data-stu-id="1be14-129">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="1be14-130">Список всех элементов управления Windows Forms см. в разделе [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="1be14-130">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="1be14-131">Если элемент управления не имеет <xref:System.Windows.Forms.Control.OnPaint%2A> указана метода-члена, путем переопределения этого метода невозможно изменить его внешний вид.</span><span class="sxs-lookup"><span data-stu-id="1be14-131">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="1be14-132">Дополнительные сведения о пользовательском оформлении см. в разделе [Рисование и отрисовка пользовательского элемента управления](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="1be14-132">For more information about custom painting, see [Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span></span>  
  
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
  
11. <span data-ttu-id="1be14-133">Сохраните и проверьте элемент управления.</span><span class="sxs-lookup"><span data-stu-id="1be14-133">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be14-134">См. также</span><span class="sxs-lookup"><span data-stu-id="1be14-134">See Also</span></span>  
 [<span data-ttu-id="1be14-135">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="1be14-135">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="1be14-136">Практическое руководство. Наследование класса Control</span><span class="sxs-lookup"><span data-stu-id="1be14-136">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [<span data-ttu-id="1be14-137">Практическое руководство. Наследование класса UserControl</span><span class="sxs-lookup"><span data-stu-id="1be14-137">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [<span data-ttu-id="1be14-138">Практическое руководство. Создание элементов управления для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1be14-138">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="1be14-139">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1be14-139">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="1be14-140">Пошаговое руководство. Наследование элементов управления форм Windows Forms с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1be14-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [<span data-ttu-id="1be14-141">Пошаговое руководство. Наследование элементов управления форм Windows Forms с помощью Visual C#</span><span class="sxs-lookup"><span data-stu-id="1be14-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
