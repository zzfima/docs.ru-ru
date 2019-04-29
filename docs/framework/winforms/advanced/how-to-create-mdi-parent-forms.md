---
title: Практическое руководство. Создание родительских MDI-форм
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms
- MDI [Windows Forms], creating forms
ms.assetid: 12c71221-2377-4bb6-b10b-7b4b300fd462
ms.openlocfilehash: d3ec2e16f06169790711c92c9d445ae93ee50c95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937596"
---
# <a name="how-to-create-mdi-parent-forms"></a><span data-ttu-id="61212-102">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="61212-102">How to: Create MDI Parent Forms</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="61212-103">В этом разделе используется элемент управления <xref:System.Windows.Forms.MainMenu>, который был заменен на элемент управления <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="61212-103">This topic uses the <xref:System.Windows.Forms.MainMenu> control, which has been replaced by the <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="61212-104">Элемент управления <xref:System.Windows.Forms.MainMenu> сохраняется для обеспечения обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="61212-104">The <xref:System.Windows.Forms.MainMenu> control is retained for both backward compatibility and future use, if you choose.</span></span>  <span data-ttu-id="61212-105">Сведения о создании MDI родительской формы с помощью <xref:System.Windows.Forms.MenuStrip>, см. в разделе [как: Создание списка в окне интерфейса MDI с помощью MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="61212-105">For information about creating a MDI parent Form by using a <xref:System.Windows.Forms.MenuStrip>, see [How to: Create an MDI Window List with MenuStrip](../controls/how-to-create-an-mdi-window-list-with-menustrip-windows-forms.md).</span></span>  
  
 <span data-ttu-id="61212-106">Базой для приложения многодокументного интерфейса (MDI) является родительская MDI-форма.</span><span class="sxs-lookup"><span data-stu-id="61212-106">The foundation of a Multiple-Document Interface (MDI) application is the MDI parent form.</span></span> <span data-ttu-id="61212-107">Это форма, содержащая дочерние MDI-окна, которые являются вложенными окнами, когда пользователи взаимодействуют с MDI-приложением.</span><span class="sxs-lookup"><span data-stu-id="61212-107">This is the form that contains the MDI child windows, which are the sub-windows wherein the user interacts with the MDI application.</span></span> <span data-ttu-id="61212-108">Создание родительской MDI-формы представляет собой несложный процесс, как с помощью конструктора Windows Forms, так и на программном уровне.</span><span class="sxs-lookup"><span data-stu-id="61212-108">Creating an MDI parent form is easy, both in the Windows Forms Designer and programmatically.</span></span>  
  
### <a name="to-create-an-mdi-parent-form-at-design-time"></a><span data-ttu-id="61212-109">Создание родительской MDI-формы во время разработки</span><span class="sxs-lookup"><span data-stu-id="61212-109">To create an MDI parent form at design time</span></span>  
  
1. <span data-ttu-id="61212-110">Создайте проект приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="61212-110">Create a Windows Application project.</span></span>  
  
2. <span data-ttu-id="61212-111">В **свойства** окне <xref:System.Windows.Forms.Form.IsMdiContainer%2A> свойства **true**.</span><span class="sxs-lookup"><span data-stu-id="61212-111">In the **Properties** window, set the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to **true**.</span></span>  
  
     <span data-ttu-id="61212-112">При этом форма назначается в качестве MDI-контейнера для дочерних окон.</span><span class="sxs-lookup"><span data-stu-id="61212-112">This designates the form as an MDI container for child windows.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61212-113">При необходимости, при настройке свойств в окне **Свойства** для свойства `WindowState` также можно задать значение **Maximized**, так как управлять дочерними MDI-окнами проще, когда родительская форма развернута.</span><span class="sxs-lookup"><span data-stu-id="61212-113">While setting properties in the **Properties** window, you can also set the `WindowState` property to **Maximized**, if you like, as it is easiest to manipulate MDI child windows when the parent form is maximized.</span></span> <span data-ttu-id="61212-114">Кроме того, следует помнить, что граница родительской MDI-формы будет окрашена в системный цвет (заданный на панели управления Windows), а не в черный цвет, заданный с помощью свойства <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="61212-114">Additionally, be aware that the edge of the MDI parent form will pick up the system color (set in the Windows System Control Panel), rather than the back color you set using the <xref:System.Windows.Forms.Control.BackColor%2A?displayProperty=nameWithType> property.</span></span>  
  
3. <span data-ttu-id="61212-115">Перетащите элемент управления **MenuStrip** из **панели элементов** в форму.</span><span class="sxs-lookup"><span data-stu-id="61212-115">From the **Toolbox**, drag a **MenuStrip** control to the form.</span></span> <span data-ttu-id="61212-116">Создайте пункт меню верхнего уровня — для свойства **Text** задайте значение **&File**, пункты меню должны называться **&New** и **&Close**.</span><span class="sxs-lookup"><span data-stu-id="61212-116">Create a top-level menu item with the **Text** property set to **&File** with submenu items called **&New** and **&Close**.</span></span> <span data-ttu-id="61212-117">Также создайте пункт меню верхнего уровня **&Window**.</span><span class="sxs-lookup"><span data-stu-id="61212-117">Also create a top-level menu item called **&Window**.</span></span>  
  
     <span data-ttu-id="61212-118">Первое меню будет создавать и скрывать пункты меню во время выполнения, а второе меню будет отслеживать открытые дочерние MDI-окна.</span><span class="sxs-lookup"><span data-stu-id="61212-118">The first menu will create and hide menu items at run time, and the second menu will keep track of the open MDI child windows.</span></span> <span data-ttu-id="61212-119">На этом этапе вы создали родительское MDI-окно.</span><span class="sxs-lookup"><span data-stu-id="61212-119">At this point, you have created an MDI parent window.</span></span>  
  
4. <span data-ttu-id="61212-120">Нажмите клавишу **F5** для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="61212-120">Press **F5** to run the application.</span></span> <span data-ttu-id="61212-121">Сведения о создании дочерних MDI-окон, действующих в родительской MDI-формы, см. в разделе [как: Создание дочерних MDI-форм](how-to-create-mdi-child-forms.md).</span><span class="sxs-lookup"><span data-stu-id="61212-121">For information about creating MDI child windows that operate within the MDI parent form, see [How to: Create MDI Child Forms](how-to-create-mdi-child-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61212-122">См. также</span><span class="sxs-lookup"><span data-stu-id="61212-122">See also</span></span>

- [<span data-ttu-id="61212-123">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="61212-123">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="61212-124">Практическое руководство. Создание дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="61212-124">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="61212-125">Практическое руководство. Определить активную дочернюю форму MDI</span><span class="sxs-lookup"><span data-stu-id="61212-125">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="61212-126">Практическое руководство. Отправки данных в активную дочернюю форму MDI</span><span class="sxs-lookup"><span data-stu-id="61212-126">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="61212-127">Практическое руководство. Упорядочение дочерних форм MDI</span><span class="sxs-lookup"><span data-stu-id="61212-127">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
