---
title: Практическое руководство. Наследование класса UserControl.
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 10bb807d012a130ad633b7ce06f99c5abf2cdda1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458369"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="6b712-102">Практическое руководство. Наследование класса UserControl.</span><span class="sxs-lookup"><span data-stu-id="6b712-102">How to: Inherit from the UserControl Class</span></span>

<span data-ttu-id="6b712-103">Чтобы объединить функциональные возможности одного или нескольких элементов управления Windows Forms с пользовательским кодом, можно создать *пользовательский элемент управления*.</span><span class="sxs-lookup"><span data-stu-id="6b712-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="6b712-104">В пользовательских элементах управления объединяются быстрая разработка, стандартные функции элементов управления Windows Forms и универсальность пользовательских методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="6b712-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="6b712-105">При создании пользовательских элементов управления используется визуальный конструктор, в котором можно размещать стандартные элементы управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6b712-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="6b712-106">Все эти элементы управления сохраняют все унаследованные функции, а также внешний вид и поведение (оформление) стандартных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6b712-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="6b712-107">Однако после того, как эти элементы управления будут встроены в пользовательский элемент управления, получить к ним доступ через код станет невозможно.</span><span class="sxs-lookup"><span data-stu-id="6b712-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="6b712-108">Пользовательский элемент управления имеет собственное оформление и обрабатывает все основные функции, связанные с элементами управления.</span><span class="sxs-lookup"><span data-stu-id="6b712-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>

## <a name="to-create-a-user-control"></a><span data-ttu-id="6b712-109">Создание пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="6b712-109">To create a user control</span></span>

1. <span data-ttu-id="6b712-110">Создайте новый проект **библиотеки элементов управления Windows** в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6b712-110">Create a new **Windows Control Library** project in Visual Studio.</span></span>

   <span data-ttu-id="6b712-111">Проект будет создан с пустым пользовательским элементом управления.</span><span class="sxs-lookup"><span data-stu-id="6b712-111">A new project is created with a blank user control.</span></span>

2. <span data-ttu-id="6b712-112">Перетащите элементы управления со вкладки **Windows Forms** на **панели элементов** в конструктор.</span><span class="sxs-lookup"><span data-stu-id="6b712-112">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>

3. <span data-ttu-id="6b712-113">Расположите и оформите их так, как они должны будут отображаться в окончательном пользовательском элементе управления.</span><span class="sxs-lookup"><span data-stu-id="6b712-113">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="6b712-114">Если вы хотите разрешить разработчикам доступ к элементам управления, составляющим пользовательский элемент управления, объявите их как открытые или выборочно предоставьте свойства таких элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6b712-114">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="6b712-115">Дополнительные сведения см. в разделе [Практическое руководство. Обеспечение доступа к свойствам составных элементов управления](how-to-expose-properties-of-constituent-controls.md).</span><span class="sxs-lookup"><span data-stu-id="6b712-115">For details, see [How to: Expose Properties of Constituent Controls](how-to-expose-properties-of-constituent-controls.md).</span></span>

4. <span data-ttu-id="6b712-116">Реализуйте необходимые пользовательские методы или свойства, которые будут входить в ваш элемент управления.</span><span class="sxs-lookup"><span data-stu-id="6b712-116">Implement any custom methods or properties that your control will incorporate.</span></span>

5. <span data-ttu-id="6b712-117">Нажмите клавишу **F5** , чтобы выполнить сборку проекта и запустить элемент управления в **тестовом контейнере UserControl**.</span><span class="sxs-lookup"><span data-stu-id="6b712-117">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="6b712-118">Дополнительные сведения см. в разделе [Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="6b712-118">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b712-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6b712-119">See also</span></span>

- [<span data-ttu-id="6b712-120">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="6b712-120">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="6b712-121">Практическое руководство. Наследование класса Control</span><span class="sxs-lookup"><span data-stu-id="6b712-121">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="6b712-122">Практическое руководство. Наследование существующих элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6b712-122">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="6b712-123">Практическое руководство. Создание элементов управления для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6b712-123">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="6b712-124">Устранение неполадок наследуемых обработчиков событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b712-124">Troubleshoot Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="6b712-125">Практическое руководство. Тестирование поведения элемента UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="6b712-125">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
