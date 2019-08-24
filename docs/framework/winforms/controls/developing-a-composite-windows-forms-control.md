---
title: Разработка составного элемента Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 9ccbf3de3f5c65b99a06c29ffce4c96896d11fae
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015960"
---
# <a name="develop-a-composite-windows-forms-control"></a><span data-ttu-id="545f9-102">Разработка составного элемента управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="545f9-102">Develop a composite Windows Forms control</span></span>

<span data-ttu-id="545f9-103">Можно разработать составной элемент управления Windows Forms, объединив другие элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="545f9-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="545f9-104">Составные элементы управления, производные от <xref:System.Web.UI.UserControl> , называются пользовательскими.</span><span class="sxs-lookup"><span data-stu-id="545f9-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="545f9-105">Базовый класс <xref:System.Windows.Forms.UserControl> обеспечивает маршрутизацию событий клавиатуры для дочерних элементов управления, это гарантирует, что дочерние элементы управления смогут получать фокус ввода.</span><span class="sxs-lookup"><span data-stu-id="545f9-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="545f9-106">Пример пользовательского элемента управления см. в <xref:System.Windows.Forms.UserControl> примере в [разделе как Применение атрибутов в элементах](how-to-apply-attributes-in-windows-forms-controls.md)управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="545f9-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>

<span data-ttu-id="545f9-107">Конструктор Windows Forms в Visual Studio обеспечивает широкую поддержку во время разработки для разработки пользовательских элементов управления.</span><span class="sxs-lookup"><span data-stu-id="545f9-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>

- [<span data-ttu-id="545f9-108">Практическое руководство. Отображение элемента управления в диалоговом окне "Выбор элементов панели элементов"</span><span class="sxs-lookup"><span data-stu-id="545f9-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)

- [<span data-ttu-id="545f9-109">Пошаговое руководство: Сериализация коллекций стандартных типов с помощью Десигнерсериализатионвисибилитяттрибуте</span><span class="sxs-lookup"><span data-stu-id="545f9-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)

- [<span data-ttu-id="545f9-110">Пошаговое руководство: Наследование от элемента управления Windows Forms с помощью VisualC#</span><span class="sxs-lookup"><span data-stu-id="545f9-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

- [<span data-ttu-id="545f9-111">Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления</span><span class="sxs-lookup"><span data-stu-id="545f9-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)

- [<span data-ttu-id="545f9-112">Практическое руководство. Наследовать от существующих элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="545f9-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)

- [<span data-ttu-id="545f9-113">Пошаговое руководство: Отладка пользовательских элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="545f9-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

- [<span data-ttu-id="545f9-114">Практическое руководство. Наследование от класса Control</span><span class="sxs-lookup"><span data-stu-id="545f9-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)

- [<span data-ttu-id="545f9-115">Практическое руководство. Проверка поведения элемента управления UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="545f9-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)

- [<span data-ttu-id="545f9-116">Практическое руководство. Выровняйте элемент управления по краям форм во время разработки</span><span class="sxs-lookup"><span data-stu-id="545f9-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)

- [<span data-ttu-id="545f9-117">Практическое руководство. Наследование от класса UserControl</span><span class="sxs-lookup"><span data-stu-id="545f9-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)

- [<span data-ttu-id="545f9-118">Практическое руководство. Создание элементов управления для Windows Forms</span><span class="sxs-lookup"><span data-stu-id="545f9-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)

- [<span data-ttu-id="545f9-119">Практическое руководство. Создание составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="545f9-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)

- [<span data-ttu-id="545f9-120">Пошаговое руководство: Создание составного элемента управления с помощью VisualC#</span><span class="sxs-lookup"><span data-stu-id="545f9-120">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)

- [<span data-ttu-id="545f9-121">Пошаговое руководство: Создание элемента управления Windows Forms, который использует преимущества функций времени разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="545f9-121">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

- <span data-ttu-id="545f9-122">[Практическое руководство. Создание элемента управления Windows Forms, который использует преимущества функций времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="545f9-122">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>

## <a name="see-also"></a><span data-ttu-id="545f9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="545f9-123">See also</span></span>

- [<span data-ttu-id="545f9-124">Практическое руководство. Применение атрибутов в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="545f9-124">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="545f9-125">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="545f9-125">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="545f9-126">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="545f9-126">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
