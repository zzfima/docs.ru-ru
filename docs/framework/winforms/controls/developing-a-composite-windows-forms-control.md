---
title: Разработка составного элемента Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 3b829b1eea68eed7ff8ded80496620af628d3510
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707369"
---
# <a name="developing-a-composite-windows-forms-control"></a><span data-ttu-id="4318d-102">Разработка составного элемента Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4318d-102">Developing a Composite Windows Forms Control</span></span>
<span data-ttu-id="4318d-103">Можно разработать составной элемент управления Windows Forms, объединив другие элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4318d-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="4318d-104">Составные элементы управления, которые являются производными от <xref:System.Web.UI.UserControl> называются пользовательскими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="4318d-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="4318d-105">Базовый класс <xref:System.Windows.Forms.UserControl> обеспечивает маршрутизацию событий клавиатуры для дочерних элементов управления, это гарантирует, что дочерние элементы управления смогут получать фокус ввода.</span><span class="sxs-lookup"><span data-stu-id="4318d-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="4318d-106">Пример пользовательского элемента управления, см. в разделе <xref:System.Windows.Forms.UserControl> в [как: Применение атрибутов в элементах управления Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="4318d-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="4318d-107">Конструктор Windows Forms в Visual Studio предоставляет широкие возможности поддержки времени разработки для пользовательских элементов управления.</span><span class="sxs-lookup"><span data-stu-id="4318d-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>  
  
-   [<span data-ttu-id="4318d-108">Практическое руководство. Отображение элемента управления в Выбор элементов панели элементов-диалоговое окно</span><span class="sxs-lookup"><span data-stu-id="4318d-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
  
-   [<span data-ttu-id="4318d-109">Пошаговое руководство: Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="4318d-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   [<span data-ttu-id="4318d-110">Пошаговое руководство: Наследование элементов управления Windows Forms с помощью VisualC#</span><span class="sxs-lookup"><span data-stu-id="4318d-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
  
-   [<span data-ttu-id="4318d-111">Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления</span><span class="sxs-lookup"><span data-stu-id="4318d-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)  
  
-   [<span data-ttu-id="4318d-112">Практическое руководство. Наследование Windows существующих элементов управления формы</span><span class="sxs-lookup"><span data-stu-id="4318d-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)  
  
-   [<span data-ttu-id="4318d-113">Пошаговое руководство: Отладка пользовательских элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="4318d-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
  
-   [<span data-ttu-id="4318d-114">Практическое руководство. Наследовать от класса Control</span><span class="sxs-lookup"><span data-stu-id="4318d-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)  
  
-   [<span data-ttu-id="4318d-115">Практическое руководство. Тестирование во время выполнения поведения элемента UserControl</span><span class="sxs-lookup"><span data-stu-id="4318d-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   [<span data-ttu-id="4318d-116">Практическое руководство. Выравнивание элементов управления по границам формы во время разработки</span><span class="sxs-lookup"><span data-stu-id="4318d-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
  
-   [<span data-ttu-id="4318d-117">Практическое руководство. Наследование класса UserControl</span><span class="sxs-lookup"><span data-stu-id="4318d-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)  
  
-   [<span data-ttu-id="4318d-118">Практическое руководство. Автор элементы управления для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4318d-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)  
  
-   [<span data-ttu-id="4318d-119">Практическое руководство. Создание составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="4318d-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)  
  
-   [<span data-ttu-id="4318d-120">Пошаговое руководство: Создание составного элемента управления с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4318d-120">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)  
  
-   [<span data-ttu-id="4318d-121">Пошаговое руководство: Создание составного элемента управления с помощью VisualC#</span><span class="sxs-lookup"><span data-stu-id="4318d-121">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
  
-   [<span data-ttu-id="4318d-122">Пошаговое руководство: Наследование элементов управления Windows Forms с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4318d-122">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
  
-   [<span data-ttu-id="4318d-123">Пошаговое руководство: Создание элемента управления Windows Forms, используются преимущества функций Visual Studio во время разработки</span><span class="sxs-lookup"><span data-stu-id="4318d-123">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)  
  
-   <span data-ttu-id="4318d-124">[Практическое руководство. Создание элемента управления Windows Forms, используются преимущества функций времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="4318d-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4318d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="4318d-125">See also</span></span>
- [<span data-ttu-id="4318d-126">Практическое руководство. Применение атрибутов в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4318d-126">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="4318d-127">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4318d-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="4318d-128">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="4318d-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
