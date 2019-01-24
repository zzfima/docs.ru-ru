---
title: Разработка составного элемента Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: 82d76c1656ff14c6d1c9bbbb1c79ec3a30708a90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635719"
---
# <a name="developing-a-composite-windows-forms-control"></a><span data-ttu-id="80247-102">Разработка составного элемента Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80247-102">Developing a Composite Windows Forms Control</span></span>
<span data-ttu-id="80247-103">Можно разработать составной элемент управления Windows Forms, объединив другие элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="80247-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="80247-104">Составные элементы управления, которые являются производными от <xref:System.Web.UI.UserControl> называются пользовательскими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="80247-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="80247-105">Базовый класс <xref:System.Windows.Forms.UserControl> обеспечивает маршрутизацию событий клавиатуры для дочерних элементов управления, это гарантирует, что дочерние элементы управления смогут получать фокус ввода.</span><span class="sxs-lookup"><span data-stu-id="80247-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="80247-106">Пример пользовательского элемента управления, см. в разделе <xref:System.Windows.Forms.UserControl> в [как: Применение атрибутов в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="80247-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="80247-107">Конструктор Windows Forms в Visual Studio предоставляет широкие возможности поддержки времени разработки для пользовательских элементов управления.</span><span class="sxs-lookup"><span data-stu-id="80247-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>  
  
-   <span data-ttu-id="80247-108">[Практическое руководство. Отображение элемента управления в Выбор элементов панели элементов-диалоговое окно](https://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-108">[How to: Display a Control in the Choose Toolbox Items Dialog Box](https://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span></span>  
  
-   [<span data-ttu-id="80247-109">Пошаговое руководство: Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="80247-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   <span data-ttu-id="80247-110">[Пошаговое руководство: Наследование от Windows Forms элемента управления с визуальным C# ](https://msdn.microsoft.com/library/09476da0-8d4c-4a4c-b969-649519dfb438))</span><span class="sxs-lookup"><span data-stu-id="80247-110">[Walkthrough: Inheriting from a Windows Forms Control with Visual C#](https://msdn.microsoft.com/library/09476da0-8d4c-4a4c-b969-649519dfb438))</span></span>  
  
-   <span data-ttu-id="80247-111">[Практическое руководство. Предоставление точечного рисунка панели элементов для элемента управления](https://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-111">[How to: Provide a Toolbox Bitmap for a Control](https://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="80247-112">[Практическое руководство. Наследование Windows существующих элементов управления формы](https://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-112">[How to: Inherit from Existing Windows Forms Controls](https://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="80247-113">[Пошаговое руководство: Отладка пользовательских элементов управления Windows Forms во время разработки](https://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-113">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](https://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="80247-114">[Практическое руководство. Наследовать от класса Control](https://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-114">[How to: Inherit from the Control Class](https://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span></span>  
  
-   [<span data-ttu-id="80247-115">Практическое руководство. Тестирование во время выполнения поведения элемента UserControl</span><span class="sxs-lookup"><span data-stu-id="80247-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   <span data-ttu-id="80247-116">[Практическое руководство. Выравнивание элементов управления по границам формы во время разработки](https://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-116">[How to: Align a Control to the Edges of Forms at Design Time](https://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="80247-117">[Практическое руководство. Наследование класса UserControl](https://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-117">[How to: Inherit from the UserControl Class](https://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="80247-118">[Практическое руководство. Автор элементы управления для форм Windows Forms](https://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-118">[How to: Author Controls for Windows Forms](https://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="80247-119">[Практическое руководство. Создание составных элементов управления](https://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-119">[How to: Author Composite Controls](https://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="80247-120">[Пошаговое руководство: Создание составного элемента управления с помощью Visual Basic](https://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-120">[Walkthrough: Authoring a Composite Control with Visual Basic](https://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="80247-121">[Пошаговое руководство: Создание составного элемента управления с визуальным C# ](https://msdn.microsoft.com/library/f88481a8-c746-4a36-9479-374ce5f2e91f))</span><span class="sxs-lookup"><span data-stu-id="80247-121">[Walkthrough: Authoring a Composite Control with Visual C#](https://msdn.microsoft.com/library/f88481a8-c746-4a36-9479-374ce5f2e91f))</span></span>  
  
-   <span data-ttu-id="80247-122">[Пошаговое руководство: Наследование элементов управления Windows Forms с помощью Visual Basic](https://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-122">[Walkthrough: Inheriting from a Windows Forms Control with Visual Basic](https://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="80247-123">[Практическое руководство. Создание элемента управления Windows Forms, используются преимущества функций времени разработки](https://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="80247-123">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="80247-124">[Практическое руководство. Создание элемента управления Windows Forms, используются преимущества функций времени разработки](https://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="80247-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80247-125">См. также</span><span class="sxs-lookup"><span data-stu-id="80247-125">See also</span></span>
- [<span data-ttu-id="80247-126">Практическое руководство. Применение атрибутов в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80247-126">How to: Apply Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="80247-127">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="80247-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="80247-128">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="80247-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
