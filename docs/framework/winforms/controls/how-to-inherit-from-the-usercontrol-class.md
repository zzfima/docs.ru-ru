---
title: "Практическое руководство. Наследование класса UserControl."
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8d04eb3c0f9ad3ef9f316bf156a9cc9568e7f8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="56e4d-102">Практическое руководство. Наследование класса UserControl.</span><span class="sxs-lookup"><span data-stu-id="56e4d-102">How to: Inherit from the UserControl Class</span></span>
<span data-ttu-id="56e4d-103">Чтобы объединить функциональные возможности одного или нескольких элементов управления Windows Forms с пользовательским кодом, можно создать *пользовательский элемент управления*.</span><span class="sxs-lookup"><span data-stu-id="56e4d-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="56e4d-104">В пользовательских элементах управления объединяются быстрая разработка, стандартные функции элементов управления Windows Forms и универсальность пользовательских методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="56e4d-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="56e4d-105">При создании пользовательских элементов управления используется визуальный конструктор, в котором можно размещать стандартные элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="56e4d-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="56e4d-106">Все эти элементы управления сохраняют все унаследованные функции, а также внешний вид и поведение (оформление) стандартных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="56e4d-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="56e4d-107">Однако после того, как эти элементы управления будут встроены в пользовательский элемент управления, получить к ним доступ через код станет невозможно.</span><span class="sxs-lookup"><span data-stu-id="56e4d-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="56e4d-108">Пользовательский элемент управления имеет собственное оформление и обрабатывает все основные функции, связанные с элементами управления.</span><span class="sxs-lookup"><span data-stu-id="56e4d-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56e4d-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="56e4d-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="56e4d-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="56e4d-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="56e4d-111">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="56e4d-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-user-control"></a><span data-ttu-id="56e4d-112">Создание пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="56e4d-112">To create a user control</span></span>  
  
1.  <span data-ttu-id="56e4d-113">Создайте проект **библиотеки элементов управления Windows**.</span><span class="sxs-lookup"><span data-stu-id="56e4d-113">Create a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="56e4d-114">Проект будет создан с пустым пользовательским элементом управления.</span><span class="sxs-lookup"><span data-stu-id="56e4d-114">A new project is created with a blank user control.</span></span>  
  
2.  <span data-ttu-id="56e4d-115">Перетащите элементы управления со вкладки **Windows Forms** на **панели элементов** в конструктор.</span><span class="sxs-lookup"><span data-stu-id="56e4d-115">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>  
  
3.  <span data-ttu-id="56e4d-116">Расположите и оформите их так, как они должны будут отображаться в окончательном пользовательском элементе управления.</span><span class="sxs-lookup"><span data-stu-id="56e4d-116">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="56e4d-117">Если вы хотите разрешить разработчикам доступ к элементам управления, составляющим пользовательский элемент управления, объявите их как открытые или выборочно предоставьте свойства таких элементов управления.</span><span class="sxs-lookup"><span data-stu-id="56e4d-117">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="56e4d-118">Дополнительные сведения см. в разделе [Практическое руководство. Обеспечение доступа к свойствам составных элементов управления](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).</span><span class="sxs-lookup"><span data-stu-id="56e4d-118">For details, see [How to: Expose Properties of Constituent Controls](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).</span></span>  
  
4.  <span data-ttu-id="56e4d-119">Реализуйте необходимые пользовательские методы или свойства, которые будут входить в ваш элемент управления.</span><span class="sxs-lookup"><span data-stu-id="56e4d-119">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
5.  <span data-ttu-id="56e4d-120">Нажмите клавишу F5, чтобы собрать проект и запустить элемент управления в **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="56e4d-120">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="56e4d-121">Дополнительные сведения см. в разделе [Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="56e4d-121">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e4d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="56e4d-122">See Also</span></span>  
 [<span data-ttu-id="56e4d-123">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="56e4d-123">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="56e4d-124">Практическое руководство. Наследование класса Control</span><span class="sxs-lookup"><span data-stu-id="56e4d-124">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [<span data-ttu-id="56e4d-125">Практическое руководство. Наследование существующих элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56e4d-125">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [<span data-ttu-id="56e4d-126">Практическое руководство. Создание элементов управления для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56e4d-126">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="56e4d-127">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56e4d-127">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="56e4d-128">Практическое руководство. Тестирование поведения элемента UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="56e4d-128">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)
