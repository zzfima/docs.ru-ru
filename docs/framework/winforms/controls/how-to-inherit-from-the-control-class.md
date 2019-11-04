---
title: Практическое руководство. Наследование класса Control.
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7af7d1fe8f14c71dfc90836d84023b98feb44961
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458383"
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="0ab7b-102">Практическое руководство. Наследование класса Control.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-102">How to: Inherit from the Control Class</span></span>

<span data-ttu-id="0ab7b-103">Если необходимо создать полностью настраиваемый элемент управления для использования в форме Windows Forms, следует наследовать от класса <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="0ab7b-104">При наследовании от класса <xref:System.Windows.Forms.Control> требуется выполнение большего планирования и реализации, а также обеспечивается самый широкий диапазон параметров.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="0ab7b-105">При наследовании от <xref:System.Windows.Forms.Control>наследуются самые базовые функции, делающие элементы управления работоспособными.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="0ab7b-106">Функции, свойственные классу <xref:System.Windows.Forms.Control>, управляют вводом данных пользователем с помощью клавиатуры и мыши, определяют границы и размер элемента управления, предоставляют дескриптор Windows и обеспечивают обработку сообщений и безопасность.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="0ab7b-107">Они не включают оформление (в данном случае отрисовку графического интерфейса элемента управления) или конкретные функции взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="0ab7b-108">Все эти аспекты необходимо прописывать в пользовательском коде.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-108">You must provide all of these aspects through custom code.</span></span>

## <a name="to-create-a-custom-control"></a><span data-ttu-id="0ab7b-109">Создание пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="0ab7b-109">To create a custom control</span></span>

1. <span data-ttu-id="0ab7b-110">В Visual Studio создайте новый проект **приложения Windows** или **библиотеки элементов управления Windows** .</span><span class="sxs-lookup"><span data-stu-id="0ab7b-110">In Visual Studio, create a new **Windows Application** or **Windows Control Library** project.</span></span>

2. <span data-ttu-id="0ab7b-111">В меню **Проект** выберите команду **Добавить класс**.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-111">From the **Project** menu, choose **Add Class**.</span></span>

3. <span data-ttu-id="0ab7b-112">В диалоговом окне **Добавление нового элемента** щелкните пункт **Пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-112">In the **Add New Item** dialog box, click **Custom Control**.</span></span>

   <span data-ttu-id="0ab7b-113">В ваш проект будет добавлен новый пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-113">A new custom control is added to your project.</span></span>

4. <span data-ttu-id="0ab7b-114">Нажмите клавишу **F7** , чтобы открыть **Редактор кода** для пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-114">Press **F7** to open the **Code Editor** for your custom control.</span></span>

5. <span data-ttu-id="0ab7b-115">Выберите метод <xref:System.Windows.Forms.Control.OnPaint%2A>, который будет пустым, за исключением вызова метода <xref:System.Windows.Forms.Control.OnPaint%2A> базового класса.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-115">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>

6. <span data-ttu-id="0ab7b-116">Измените код, добавив в него пользовательское оформление вашего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-116">Modify the code to incorporate any custom painting you want for your control.</span></span>

   <span data-ttu-id="0ab7b-117">Сведения о написании кода для отрисовки графического интерфейса элементов управления см. в разделе [Рисование и отрисовка пользовательского элемента управления](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="0ab7b-117">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

7. <span data-ttu-id="0ab7b-118">Реализуйте необходимые пользовательские методы, свойства или события, которые будут входить в ваш элемент управления.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-118">Implement any custom methods, properties, or events that your control will incorporate.</span></span>

8. <span data-ttu-id="0ab7b-119">Сохраните и проверьте элемент управления.</span><span class="sxs-lookup"><span data-stu-id="0ab7b-119">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ab7b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0ab7b-120">See also</span></span>

- [<span data-ttu-id="0ab7b-121">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="0ab7b-121">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="0ab7b-122">Практическое руководство. Наследование класса UserControl</span><span class="sxs-lookup"><span data-stu-id="0ab7b-122">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="0ab7b-123">Практическое руководство. Наследование существующих элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ab7b-123">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="0ab7b-124">Практическое руководство. Создание элементов управления для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ab7b-124">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="0ab7b-125">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0ab7b-125">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="0ab7b-126">Создание элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="0ab7b-126">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
