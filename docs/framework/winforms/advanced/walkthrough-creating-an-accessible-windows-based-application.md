---
title: Пошаговое руководство. Создание приложения Windows с поддержкой специальных возможностей
ms.date: 03/30/2017
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
ms.openlocfilehash: e7bc996c3d64c0ea3ac8fca5fef759ad309f2967
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747556"
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a><span data-ttu-id="d4177-102">Пошаговое руководство. Создание приложения Windows с поддержкой специальных возможностей</span><span class="sxs-lookup"><span data-stu-id="d4177-102">Walkthrough: Creating an Accessible Windows-based Application</span></span>
<span data-ttu-id="d4177-103">Создание приложений со специальными возможностями необходимо по деловым соображениям.</span><span class="sxs-lookup"><span data-stu-id="d4177-103">Creating an accessible application has important business implications.</span></span> <span data-ttu-id="d4177-104">Во многих странах для продаваемого программного обеспечения существуют правительственные требования в отношении специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="d4177-104">Many governments have accessibility regulations for software purchase.</span></span> <span data-ttu-id="d4177-105">Логотип "Сертифицировано для Windows" предполагает соответствие продукта требованиям в отношении специальных возможностей.</span><span class="sxs-lookup"><span data-stu-id="d4177-105">The Certified for Windows logo includes accessibility requirements.</span></span> <span data-ttu-id="d4177-106">По предварительным оценкам, только в США 30 миллионов пользователей нуждаются в программном обеспечении со специальными возможностями. Многие из них являются потенциальными клиентами.</span><span class="sxs-lookup"><span data-stu-id="d4177-106">An estimated 30 million residents of the U.S. alone, many of them potential customers, are affected by the accessibility of software.</span></span>  
  
 <span data-ttu-id="d4177-107">В этом пошаговом руководстве рассматриваются пять требований в отношении специальных возможностей, выполнение которых необходимо для использования эмблемы "Сертифицировано для Windows".</span><span class="sxs-lookup"><span data-stu-id="d4177-107">This walkthrough will address the five accessibility requirements for the Certified for Windows logo.</span></span> <span data-ttu-id="d4177-108">Согласно этим требованиям в приложении со специальными возможностями обеспечиваются:</span><span class="sxs-lookup"><span data-stu-id="d4177-108">According to these requirements, an accessible application will:</span></span>  
  
-   <span data-ttu-id="d4177-109">поддержка настройки размера, цвета, шрифта и параметров ввода с панели управления;</span><span class="sxs-lookup"><span data-stu-id="d4177-109">Support Control Panel size, color, font, and input settings.</span></span> <span data-ttu-id="d4177-110">изменение размеров строк меню, строк заголовков, границ и строки состояния при изменении соответствующих параметров на панели управления</span><span class="sxs-lookup"><span data-stu-id="d4177-110">The menu bar, title bar, borders, and status bar will all resize themselves when the user changes the control panel settings.</span></span> <span data-ttu-id="d4177-111">(дополнительные изменения элементов управления или кода в приложении не требуются);</span><span class="sxs-lookup"><span data-stu-id="d4177-111">No additional changes to the controls or code are required in this application.</span></span>  
  
-   <span data-ttu-id="d4177-112">поддержка режима высокой контрастности;</span><span class="sxs-lookup"><span data-stu-id="d4177-112">Support High Contrast mode.</span></span>  
  
-   <span data-ttu-id="d4177-113">документированный доступ с клавиатуры ко всем возможностям;</span><span class="sxs-lookup"><span data-stu-id="d4177-113">Provide documented keyboard access to all features.</span></span>  
  
-   <span data-ttu-id="d4177-114">наглядное и программное представление фокуса клавиатуры;</span><span class="sxs-lookup"><span data-stu-id="d4177-114">Expose location of the keyboard focus visually and programmatically.</span></span>  
  
-   <span data-ttu-id="d4177-115">предоставление важной информации не только с помощью звукового сигнала.</span><span class="sxs-lookup"><span data-stu-id="d4177-115">Avoid conveying important information by sound alone.</span></span>  
  
 <span data-ttu-id="d4177-116">Подробнее см. в разделе [Ресурсы для создания приложений со специальными возможностями](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span><span class="sxs-lookup"><span data-stu-id="d4177-116">For more information, see [Resources for Designing Accessible Applications](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span></span>  
  
 <span data-ttu-id="d4177-117">Информацию о поддержке различных раскладок клавиатуры см. в разделе [Рекомендации по разработке международных приложений](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span><span class="sxs-lookup"><span data-stu-id="d4177-117">For information on supporting varying keyboard layouts, see [Best Practices for Developing World-Ready Applications](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="d4177-118">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="d4177-118">Creating the Project</span></span>  
 <span data-ttu-id="d4177-119">В этом пошаговом руководстве создается пользовательский интерфейс для приложения, принимающего заказы на пиццу.</span><span class="sxs-lookup"><span data-stu-id="d4177-119">This walkthrough creates the user interface for an application that takes pizza orders.</span></span> <span data-ttu-id="d4177-120">Оно содержит поле (<xref:System.Windows.Forms.TextBox>) для имени заказчика, группу переключателей (<xref:System.Windows.Forms.RadioButton>) для выбора размера пиццы, флажки (<xref:System.Windows.Forms.CheckedListBox>) для выбора начинки, две кнопки с надписями "Заказать" и "Отмена", а также меню с командой "Выход".</span><span class="sxs-lookup"><span data-stu-id="d4177-120">It consists of a <xref:System.Windows.Forms.TextBox> for the customer's name, a <xref:System.Windows.Forms.RadioButton> group to select the pizza size, a <xref:System.Windows.Forms.CheckedListBox> for selecting the toppings, two Button controls labeled Order and Cancel, and a Menu with an Exit command.</span></span>  
  
 <span data-ttu-id="d4177-121">Пользователь вводит имя заказчика, размер пиццы и выбранную начинку.</span><span class="sxs-lookup"><span data-stu-id="d4177-121">The user enters the customer's name, the size of the pizza, and the toppings desired.</span></span> <span data-ttu-id="d4177-122">Когда пользователь нажимает кнопку "Заказать", сводка заказа и его цена выводятся в окне сообщения, а элементы управления очищаются и становятся готовыми к приему следующего заказа.</span><span class="sxs-lookup"><span data-stu-id="d4177-122">When the user clicks the Order button, a summary of the order and its cost are displayed in a message box and the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="d4177-123">Когда пользователь нажимает кнопку "Отмена", элементы управления очищаются и становятся готовыми к приему следующего заказа.</span><span class="sxs-lookup"><span data-stu-id="d4177-123">When the user clicks the Cancel button, the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="d4177-124">Когда пользователь выбирает в меню команду "Выход", программа закрывается.</span><span class="sxs-lookup"><span data-stu-id="d4177-124">When the user clicks the Exit menu item, the program closes.</span></span>  
  
 <span data-ttu-id="d4177-125">Основное внимание в этом пошаговом руководстве уделяется не коду для системы розничной продажи, а специальным возможностям пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="d4177-125">The emphasis of this walkthrough is not the code for a retail order system, but the accessibility of the user interface.</span></span> <span data-ttu-id="d4177-126">В примере демонстрируются специальные возможности для некоторых часто используемых элементов управления, таких как кнопки, переключатели, поля и метки.</span><span class="sxs-lookup"><span data-stu-id="d4177-126">The walkthrough demonstrates the accessibility features of several frequently used controls, including buttons, radio buttons, text boxes, and labels.</span></span>  
  
#### <a name="to-begin-making-the-application"></a><span data-ttu-id="d4177-127">Начало разработки приложения</span><span class="sxs-lookup"><span data-stu-id="d4177-127">To begin making the application</span></span>  
  
-   <span data-ttu-id="d4177-128">Создайте новое приложение Windows в Visual Basic или Visual C#.</span><span class="sxs-lookup"><span data-stu-id="d4177-128">Create a new Windows Application in Visual Basic or Visual C#.</span></span> <span data-ttu-id="d4177-129">Назовите проект **PizzaOrder**.</span><span class="sxs-lookup"><span data-stu-id="d4177-129">Name the project **PizzaOrder**.</span></span> <span data-ttu-id="d4177-130">(Подробнее см. в разделе [Создание решений и проектов](/visualstudio/ide/creating-solutions-and-projects).)</span><span class="sxs-lookup"><span data-stu-id="d4177-130">(For details see [Creating New Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).)</span></span>  
  
## <a name="adding-the-controls-to-the-form"></a><span data-ttu-id="d4177-131">Добавление элементов управления в форму</span><span class="sxs-lookup"><span data-stu-id="d4177-131">Adding the Controls to the Form</span></span>  
 <span data-ttu-id="d4177-132">При добавлении элементов управления в форму придерживайтесь приведенных ниже правил для того, чтобы приложение было доступным для пользователей с физическими ограничениями.</span><span class="sxs-lookup"><span data-stu-id="d4177-132">When adding the controls to a form, keep in mind the following guidelines to make an accessible application:</span></span>  
  
-   <span data-ttu-id="d4177-133">Задайте свойства <xref:System.Windows.Forms.Control.AccessibleDescription%2A> и <xref:System.Windows.Forms.Control.AccessibleName%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4177-133">Set the <xref:System.Windows.Forms.Control.AccessibleDescription%2A> and <xref:System.Windows.Forms.Control.AccessibleName%2A> properties.</span></span> <span data-ttu-id="d4177-134">В этом примере для свойства <xref:System.Windows.Forms.Control.AccessibleRole%2A> достаточным является значение Default.</span><span class="sxs-lookup"><span data-stu-id="d4177-134">In this example, the Default setting for the <xref:System.Windows.Forms.Control.AccessibleRole%2A> is sufficient.</span></span> <span data-ttu-id="d4177-135">Подробнее о свойствах специальных возможностей см. в разделе [Определение сведений, связанных со специальными возможностями, для элементов управления в Windows Forms](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="d4177-135">For more information on the accessibility properties, see [Providing Accessibility Information for Controls on a Windows Form](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span></span>  
  
-   <span data-ttu-id="d4177-136">Задайте размер шрифта 10 пунктов или выше.</span><span class="sxs-lookup"><span data-stu-id="d4177-136">Set the font size to 10 points or larger.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4177-137">Если задать для формы размер шрифта 10 в начале работы, то все элементы управления, добавляемые в форму после этого, также будут иметь размер шрифта 10.</span><span class="sxs-lookup"><span data-stu-id="d4177-137">If you set the font size of the form to 10 when you start, then all controls subsequently added to the form will have a font size of 10.</span></span>  
  
-   <span data-ttu-id="d4177-138">Убедитесь в том, что любой элемент управления Label, относящийся к элементу TextBox, непосредственно предшествует элементу TextBox в последовательности табуляции.</span><span class="sxs-lookup"><span data-stu-id="d4177-138">Make sure any Label control that describes a TextBox control immediately precedes the TextBox control in the tab order.</span></span>  
  
-   <span data-ttu-id="d4177-139">Добавьте клавишу доступа, с помощью символа «&», в <xref:System.Windows.Forms.Control.Text%2A> свойства любого элемента управления, пользователь может потребоваться перейти.</span><span class="sxs-lookup"><span data-stu-id="d4177-139">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of any control the user may want to navigate to.</span></span>  
  
-   <span data-ttu-id="d4177-140">Добавьте клавишу доступа, с помощью символа «&», в <xref:System.Windows.Forms.Control.Text%2A> метки, которая предшествует элементу управления, который пользователь может потребоваться перейти.</span><span class="sxs-lookup"><span data-stu-id="d4177-140">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of the label that precedes a control that the user may want to navigate to.</span></span> <span data-ttu-id="d4177-141">Задайте для свойства <xref:System.Windows.Forms.Label.UseMnemonic%2A> метки значение `true`, чтобы при нажатии клавиши доступа фокус переводился на следующий элемент управления в последовательности табуляции.</span><span class="sxs-lookup"><span data-stu-id="d4177-141">Set the labels' <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`, so that the focus is set to the next control in the tab order when the user presses the access key.</span></span>  
  
-   <span data-ttu-id="d4177-142">Добавьте клавиши доступа для всех элементов меню.</span><span class="sxs-lookup"><span data-stu-id="d4177-142">Add access keys to all menu items.</span></span>  
  
#### <a name="to-make-your-windows-application-accessible"></a><span data-ttu-id="d4177-143">Обеспечение специальных возможностей приложения Windows</span><span class="sxs-lookup"><span data-stu-id="d4177-143">To make your Windows Application accessible</span></span>  
  
-   <span data-ttu-id="d4177-144">Добавьте в форму элементы управления и задайте их свойства, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="d4177-144">Add the controls to the form and set the properties as described below.</span></span> <span data-ttu-id="d4177-145">Модель размещения элементов управления в форме см. на рисунке после таблицы.</span><span class="sxs-lookup"><span data-stu-id="d4177-145">See the picture at the end of the table for a model of how to arrange the controls on the form.</span></span>  
  
    |<span data-ttu-id="d4177-146">Object</span><span class="sxs-lookup"><span data-stu-id="d4177-146">Object</span></span>|<span data-ttu-id="d4177-147">Свойство.</span><span class="sxs-lookup"><span data-stu-id="d4177-147">Property</span></span>|<span data-ttu-id="d4177-148">Значение</span><span class="sxs-lookup"><span data-stu-id="d4177-148">Value</span></span>|  
    |------------|--------------|-----------|  
    |<span data-ttu-id="d4177-149">Form1</span><span class="sxs-lookup"><span data-stu-id="d4177-149">Form1</span></span>|<span data-ttu-id="d4177-150">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-150">AccessibleDescription</span></span>|<span data-ttu-id="d4177-151">Форма заказа</span><span class="sxs-lookup"><span data-stu-id="d4177-151">Order form</span></span>|  
    ||<span data-ttu-id="d4177-152">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-152">AccessibleName</span></span>|<span data-ttu-id="d4177-153">Форма заказа</span><span class="sxs-lookup"><span data-stu-id="d4177-153">Order form</span></span>|  
    ||<span data-ttu-id="d4177-154">Размер шрифта</span><span class="sxs-lookup"><span data-stu-id="d4177-154">Font Size</span></span>|<span data-ttu-id="d4177-155">10</span><span class="sxs-lookup"><span data-stu-id="d4177-155">10</span></span>|  
    ||<span data-ttu-id="d4177-156">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-156">Text</span></span>|<span data-ttu-id="d4177-157">Форма заказа пиццы</span><span class="sxs-lookup"><span data-stu-id="d4177-157">Pizza Order Form</span></span>|  
    |<span data-ttu-id="d4177-158">PictureBox</span><span class="sxs-lookup"><span data-stu-id="d4177-158">PictureBox</span></span>|<span data-ttu-id="d4177-159">name</span><span class="sxs-lookup"><span data-stu-id="d4177-159">Name</span></span>|<span data-ttu-id="d4177-160">logo</span><span class="sxs-lookup"><span data-stu-id="d4177-160">logo</span></span>|  
    ||<span data-ttu-id="d4177-161">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-161">AccessibleDescription</span></span>|<span data-ttu-id="d4177-162">Порция пиццы</span><span class="sxs-lookup"><span data-stu-id="d4177-162">A slice of pizza</span></span>|  
    ||<span data-ttu-id="d4177-163">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-163">AccessibleName</span></span>|<span data-ttu-id="d4177-164">Логотип компании</span><span class="sxs-lookup"><span data-stu-id="d4177-164">Company logo</span></span>|  
    ||<span data-ttu-id="d4177-165">Изображение</span><span class="sxs-lookup"><span data-stu-id="d4177-165">Image</span></span>|<span data-ttu-id="d4177-166">Любой значок или растровое изображение</span><span class="sxs-lookup"><span data-stu-id="d4177-166">Any icon or bitmap</span></span>|  
    |<span data-ttu-id="d4177-167">Метка</span><span class="sxs-lookup"><span data-stu-id="d4177-167">Label</span></span>|<span data-ttu-id="d4177-168">name</span><span class="sxs-lookup"><span data-stu-id="d4177-168">Name</span></span>|<span data-ttu-id="d4177-169">companyLabel</span><span class="sxs-lookup"><span data-stu-id="d4177-169">companyLabel</span></span>|  
    ||<span data-ttu-id="d4177-170">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-170">Text</span></span>|<span data-ttu-id="d4177-171">Вкусная пицца</span><span class="sxs-lookup"><span data-stu-id="d4177-171">Good Pizza</span></span>|  
    ||<span data-ttu-id="d4177-172">TabIndex</span><span class="sxs-lookup"><span data-stu-id="d4177-172">TabIndex</span></span>|<span data-ttu-id="d4177-173">1</span><span class="sxs-lookup"><span data-stu-id="d4177-173">1</span></span>|  
    ||<span data-ttu-id="d4177-174">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-174">AccessibleDescription</span></span>|<span data-ttu-id="d4177-175">Название компании</span><span class="sxs-lookup"><span data-stu-id="d4177-175">Company name</span></span>|  
    ||<span data-ttu-id="d4177-176">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-176">AccessibleName</span></span>|<span data-ttu-id="d4177-177">Название компании</span><span class="sxs-lookup"><span data-stu-id="d4177-177">Company name</span></span>|  
    ||<span data-ttu-id="d4177-178">Backcolor</span><span class="sxs-lookup"><span data-stu-id="d4177-178">Backcolor</span></span>|<span data-ttu-id="d4177-179">Синий</span><span class="sxs-lookup"><span data-stu-id="d4177-179">Blue</span></span>|  
    ||<span data-ttu-id="d4177-180">Forecolor</span><span class="sxs-lookup"><span data-stu-id="d4177-180">Forecolor</span></span>|<span data-ttu-id="d4177-181">Желтый</span><span class="sxs-lookup"><span data-stu-id="d4177-181">Yellow</span></span>|  
    ||<span data-ttu-id="d4177-182">Font size</span><span class="sxs-lookup"><span data-stu-id="d4177-182">Font size</span></span>|<span data-ttu-id="d4177-183">18</span><span class="sxs-lookup"><span data-stu-id="d4177-183">18</span></span>|  
    |<span data-ttu-id="d4177-184">Метка</span><span class="sxs-lookup"><span data-stu-id="d4177-184">Label</span></span>|<span data-ttu-id="d4177-185">name</span><span class="sxs-lookup"><span data-stu-id="d4177-185">Name</span></span>|<span data-ttu-id="d4177-186">customerLabel</span><span class="sxs-lookup"><span data-stu-id="d4177-186">customerLabel</span></span>|  
    ||<span data-ttu-id="d4177-187">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-187">Text</span></span>|<span data-ttu-id="d4177-188">&Имя</span><span class="sxs-lookup"><span data-stu-id="d4177-188">&Name</span></span>|  
    ||<span data-ttu-id="d4177-189">TabIndex</span><span class="sxs-lookup"><span data-stu-id="d4177-189">TabIndex</span></span>|<span data-ttu-id="d4177-190">2</span><span class="sxs-lookup"><span data-stu-id="d4177-190">2</span></span>|  
    ||<span data-ttu-id="d4177-191">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-191">AccessibleDescription</span></span>|<span data-ttu-id="d4177-192">Подпись имени заказчика</span><span class="sxs-lookup"><span data-stu-id="d4177-192">Customer name label</span></span>|  
    ||<span data-ttu-id="d4177-193">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-193">AccessibleName</span></span>|<span data-ttu-id="d4177-194">Подпись имени заказчика</span><span class="sxs-lookup"><span data-stu-id="d4177-194">Customer name label</span></span>|  
    ||<span data-ttu-id="d4177-195">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="d4177-195">UseMnemonic</span></span>|<span data-ttu-id="d4177-196">True</span><span class="sxs-lookup"><span data-stu-id="d4177-196">True</span></span>|  
    |<span data-ttu-id="d4177-197">TextBox</span><span class="sxs-lookup"><span data-stu-id="d4177-197">TextBox</span></span>|<span data-ttu-id="d4177-198">name</span><span class="sxs-lookup"><span data-stu-id="d4177-198">Name</span></span>|<span data-ttu-id="d4177-199">customerName</span><span class="sxs-lookup"><span data-stu-id="d4177-199">customerName</span></span>|  
    ||<span data-ttu-id="d4177-200">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-200">Text</span></span>|<span data-ttu-id="d4177-201">(нет)</span><span class="sxs-lookup"><span data-stu-id="d4177-201">(none)</span></span>|  
    ||<span data-ttu-id="d4177-202">TabIndex</span><span class="sxs-lookup"><span data-stu-id="d4177-202">TabIndex</span></span>|<span data-ttu-id="d4177-203">3</span><span class="sxs-lookup"><span data-stu-id="d4177-203">3</span></span>|  
    ||<span data-ttu-id="d4177-204">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-204">AccessibleDescription</span></span>|<span data-ttu-id="d4177-205">Имя заказчика</span><span class="sxs-lookup"><span data-stu-id="d4177-205">Customer name</span></span>|  
    ||<span data-ttu-id="d4177-206">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-206">AccessibleName</span></span>|<span data-ttu-id="d4177-207">Имя заказчика</span><span class="sxs-lookup"><span data-stu-id="d4177-207">Customer name</span></span>|  
    |<span data-ttu-id="d4177-208">GroupBox</span><span class="sxs-lookup"><span data-stu-id="d4177-208">GroupBox</span></span>|<span data-ttu-id="d4177-209">name</span><span class="sxs-lookup"><span data-stu-id="d4177-209">Name</span></span>|<span data-ttu-id="d4177-210">sizeOptions</span><span class="sxs-lookup"><span data-stu-id="d4177-210">sizeOptions</span></span>|  
    ||<span data-ttu-id="d4177-211">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-211">AccessibleDescription</span></span>|<span data-ttu-id="d4177-212">Размеры порции пиццы</span><span class="sxs-lookup"><span data-stu-id="d4177-212">Pizza size options</span></span>|  
    ||<span data-ttu-id="d4177-213">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-213">AccessibleName</span></span>|<span data-ttu-id="d4177-214">Размеры порции пиццы</span><span class="sxs-lookup"><span data-stu-id="d4177-214">Pizza size options</span></span>|  
    ||<span data-ttu-id="d4177-215">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-215">Text</span></span>|<span data-ttu-id="d4177-216">Размер пиццы</span><span class="sxs-lookup"><span data-stu-id="d4177-216">Pizza size</span></span>|  
    ||<span data-ttu-id="d4177-217">TabIndex</span><span class="sxs-lookup"><span data-stu-id="d4177-217">TabIndex</span></span>|<span data-ttu-id="d4177-218">4</span><span class="sxs-lookup"><span data-stu-id="d4177-218">4</span></span>|  
    |<span data-ttu-id="d4177-219">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d4177-219">RadioButton</span></span>|<span data-ttu-id="d4177-220">name</span><span class="sxs-lookup"><span data-stu-id="d4177-220">Name</span></span>|<span data-ttu-id="d4177-221">smallPizza</span><span class="sxs-lookup"><span data-stu-id="d4177-221">smallPizza</span></span>|  
    ||<span data-ttu-id="d4177-222">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-222">Text</span></span>|<span data-ttu-id="d4177-223">&Маленькая 300 р.</span><span class="sxs-lookup"><span data-stu-id="d4177-223">&Small $6.00</span></span>|  
    ||<span data-ttu-id="d4177-224">Установлен</span><span class="sxs-lookup"><span data-stu-id="d4177-224">Checked</span></span>|<span data-ttu-id="d4177-225">True</span><span class="sxs-lookup"><span data-stu-id="d4177-225">True</span></span>|  
    ||<span data-ttu-id="d4177-226">TabIndex</span><span class="sxs-lookup"><span data-stu-id="d4177-226">TabIndex</span></span>|<span data-ttu-id="d4177-227">0</span><span class="sxs-lookup"><span data-stu-id="d4177-227">0</span></span>|  
    ||<span data-ttu-id="d4177-228">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-228">AccessibleDescription</span></span>|<span data-ttu-id="d4177-229">Маленькая пицца</span><span class="sxs-lookup"><span data-stu-id="d4177-229">Small pizza</span></span>|  
    ||<span data-ttu-id="d4177-230">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-230">AccessibleName</span></span>|<span data-ttu-id="d4177-231">Маленькая пицца</span><span class="sxs-lookup"><span data-stu-id="d4177-231">Small pizza</span></span>|  
    |<span data-ttu-id="d4177-232">RadioButton</span><span class="sxs-lookup"><span data-stu-id="d4177-232">RadioButton</span></span>|<span data-ttu-id="d4177-233">name</span><span class="sxs-lookup"><span data-stu-id="d4177-233">Name</span></span>|<span data-ttu-id="d4177-234">largePizza</span><span class="sxs-lookup"><span data-stu-id="d4177-234">largePizza</span></span>|  
    ||<span data-ttu-id="d4177-235">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-235">Text</span></span>|<span data-ttu-id="d4177-236">&Большая 500 р.</span><span class="sxs-lookup"><span data-stu-id="d4177-236">&Large $10.00</span></span>|  
    ||<span data-ttu-id="d4177-237">TabIndex</span><span class="sxs-lookup"><span data-stu-id="d4177-237">TabIndex</span></span>|<span data-ttu-id="d4177-238">1</span><span class="sxs-lookup"><span data-stu-id="d4177-238">1</span></span>|  
    ||<span data-ttu-id="d4177-239">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-239">AccessibleDescription</span></span>|<span data-ttu-id="d4177-240">Большая пицца</span><span class="sxs-lookup"><span data-stu-id="d4177-240">Large pizza</span></span>|  
    ||<span data-ttu-id="d4177-241">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-241">AccessibleName</span></span>|<span data-ttu-id="d4177-242">Большая пицца</span><span class="sxs-lookup"><span data-stu-id="d4177-242">Large pizza</span></span>|  
    |<span data-ttu-id="d4177-243">Метка</span><span class="sxs-lookup"><span data-stu-id="d4177-243">Label</span></span>|<span data-ttu-id="d4177-244">name</span><span class="sxs-lookup"><span data-stu-id="d4177-244">Name</span></span>|<span data-ttu-id="d4177-245">toppingsLabel</span><span class="sxs-lookup"><span data-stu-id="d4177-245">toppingsLabel</span></span>|  
    ||<span data-ttu-id="d4177-246">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-246">Text</span></span>|<span data-ttu-id="d4177-247">&Начинки (40 р. за каждую)</span><span class="sxs-lookup"><span data-stu-id="d4177-247">&Toppings ($0.75 each)</span></span>|  
    ||<span data-ttu-id="d4177-248">TabIndex</span><span class="sxs-lookup"><span data-stu-id="d4177-248">TabIndex</span></span>|<span data-ttu-id="d4177-249">5</span><span class="sxs-lookup"><span data-stu-id="d4177-249">5</span></span>|  
    ||<span data-ttu-id="d4177-250">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-250">AccessibleDescription</span></span>|<span data-ttu-id="d4177-251">Метка начинки</span><span class="sxs-lookup"><span data-stu-id="d4177-251">Toppings label</span></span>|  
    ||<span data-ttu-id="d4177-252">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-252">AccessibleName</span></span>|<span data-ttu-id="d4177-253">Метка начинки</span><span class="sxs-lookup"><span data-stu-id="d4177-253">Toppings label</span></span>|  
    ||<span data-ttu-id="d4177-254">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="d4177-254">UseMnemonic</span></span>|<span data-ttu-id="d4177-255">True</span><span class="sxs-lookup"><span data-stu-id="d4177-255">True</span></span>|  
    |<span data-ttu-id="d4177-256">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="d4177-256">CheckedListBox</span></span>|<span data-ttu-id="d4177-257">name</span><span class="sxs-lookup"><span data-stu-id="d4177-257">Name</span></span>|<span data-ttu-id="d4177-258">toppings</span><span class="sxs-lookup"><span data-stu-id="d4177-258">toppings</span></span>|  
    ||<span data-ttu-id="d4177-259">TabIndex</span><span class="sxs-lookup"><span data-stu-id="d4177-259">TabIndex</span></span>|<span data-ttu-id="d4177-260">6</span><span class="sxs-lookup"><span data-stu-id="d4177-260">6</span></span>|  
    ||<span data-ttu-id="d4177-261">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-261">AccessibleDescription</span></span>|<span data-ttu-id="d4177-262">Выбор начинок</span><span class="sxs-lookup"><span data-stu-id="d4177-262">Available toppings</span></span>|  
    ||<span data-ttu-id="d4177-263">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-263">AccessibleName</span></span>|<span data-ttu-id="d4177-264">Выбор начинок</span><span class="sxs-lookup"><span data-stu-id="d4177-264">Available toppings</span></span>|  
    ||<span data-ttu-id="d4177-265">Элементы</span><span class="sxs-lookup"><span data-stu-id="d4177-265">Items</span></span>|<span data-ttu-id="d4177-266">Пепперони, колбаса, грибы</span><span class="sxs-lookup"><span data-stu-id="d4177-266">Pepperoni, Sausage, Mushrooms</span></span>|  
    |<span data-ttu-id="d4177-267">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d4177-267">Button</span></span>|<span data-ttu-id="d4177-268">name</span><span class="sxs-lookup"><span data-stu-id="d4177-268">Name</span></span>|<span data-ttu-id="d4177-269">порядок</span><span class="sxs-lookup"><span data-stu-id="d4177-269">order</span></span>|  
    ||<span data-ttu-id="d4177-270">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-270">Text</span></span>|<span data-ttu-id="d4177-271">&Порядок</span><span class="sxs-lookup"><span data-stu-id="d4177-271">&Order</span></span>|  
    ||<span data-ttu-id="d4177-272">TabIndex</span><span class="sxs-lookup"><span data-stu-id="d4177-272">TabIndex</span></span>|<span data-ttu-id="d4177-273">7</span><span class="sxs-lookup"><span data-stu-id="d4177-273">7</span></span>|  
    ||<span data-ttu-id="d4177-274">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-274">AccessibleDescription</span></span>|<span data-ttu-id="d4177-275">Сумма заказа</span><span class="sxs-lookup"><span data-stu-id="d4177-275">Total the order</span></span>|  
    ||<span data-ttu-id="d4177-276">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-276">AccessibleName</span></span>|<span data-ttu-id="d4177-277">Сумма заказа</span><span class="sxs-lookup"><span data-stu-id="d4177-277">Total order</span></span>|  
    |<span data-ttu-id="d4177-278">Кнопка</span><span class="sxs-lookup"><span data-stu-id="d4177-278">Button</span></span>|<span data-ttu-id="d4177-279">name</span><span class="sxs-lookup"><span data-stu-id="d4177-279">Name</span></span>|<span data-ttu-id="d4177-280">cancel</span><span class="sxs-lookup"><span data-stu-id="d4177-280">cancel</span></span>|  
    ||<span data-ttu-id="d4177-281">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-281">Text</span></span>|<span data-ttu-id="d4177-282">О&тмена</span><span class="sxs-lookup"><span data-stu-id="d4177-282">&Cancel</span></span>|  
    ||<span data-ttu-id="d4177-283">TabIndex</span><span class="sxs-lookup"><span data-stu-id="d4177-283">TabIndex</span></span>|<span data-ttu-id="d4177-284">8</span><span class="sxs-lookup"><span data-stu-id="d4177-284">8</span></span>|  
    ||<span data-ttu-id="d4177-285">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="d4177-285">AccessibleDescription</span></span>|<span data-ttu-id="d4177-286">Отмена заказа</span><span class="sxs-lookup"><span data-stu-id="d4177-286">Cancel the order</span></span>|  
    ||<span data-ttu-id="d4177-287">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="d4177-287">AccessibleName</span></span>|<span data-ttu-id="d4177-288">Отмена заказа</span><span class="sxs-lookup"><span data-stu-id="d4177-288">Cancel order</span></span>|  
    |<span data-ttu-id="d4177-289">MainMenu</span><span class="sxs-lookup"><span data-stu-id="d4177-289">MainMenu</span></span>|<span data-ttu-id="d4177-290">name</span><span class="sxs-lookup"><span data-stu-id="d4177-290">Name</span></span>|<span data-ttu-id="d4177-291">theMainMenu</span><span class="sxs-lookup"><span data-stu-id="d4177-291">theMainMenu</span></span>|  
    |<span data-ttu-id="d4177-292">MenuItem</span><span class="sxs-lookup"><span data-stu-id="d4177-292">MenuItem</span></span>|<span data-ttu-id="d4177-293">name</span><span class="sxs-lookup"><span data-stu-id="d4177-293">Name</span></span>|<span data-ttu-id="d4177-294">fileCommands</span><span class="sxs-lookup"><span data-stu-id="d4177-294">fileCommands</span></span>|  
    ||<span data-ttu-id="d4177-295">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-295">Text</span></span>|<span data-ttu-id="d4177-296">&Файл</span><span class="sxs-lookup"><span data-stu-id="d4177-296">&File</span></span>|  
    |<span data-ttu-id="d4177-297">MenuItem</span><span class="sxs-lookup"><span data-stu-id="d4177-297">MenuItem</span></span>|<span data-ttu-id="d4177-298">name</span><span class="sxs-lookup"><span data-stu-id="d4177-298">Name</span></span>|<span data-ttu-id="d4177-299">exitApp</span><span class="sxs-lookup"><span data-stu-id="d4177-299">exitApp</span></span>|  
    ||<span data-ttu-id="d4177-300">Текста</span><span class="sxs-lookup"><span data-stu-id="d4177-300">Text</span></span>|<span data-ttu-id="d4177-301">Вы&ход</span><span class="sxs-lookup"><span data-stu-id="d4177-301">E&xit</span></span>|
    
      <span data-ttu-id="d4177-302">Форма будет выглядеть примерно как на следующем изображении:</span><span class="sxs-lookup"><span data-stu-id="d4177-302">Your form will look something like the following image:</span></span>
    
      ![Форма заказа пиццы имя текстового поля и размер и начинки выделением.](./media/walkthrough-creating-an-accessible-windows-based-application/visual-basic-pizza-order-form.gif)  

## <a name="supporting-high-contrast-mode"></a><span data-ttu-id="d4177-304">Поддержка режима высокой контрастности</span><span class="sxs-lookup"><span data-stu-id="d4177-304">Supporting High Contrast Mode</span></span>  
 <span data-ttu-id="d4177-305">Режим высокой контрастности представляет собой тип системной настройки Windows, при которой удобство чтения текста повышается за счет более контрастных цветов и размеров шрифта, подходящих для пользователей с нарушениями зрения.</span><span class="sxs-lookup"><span data-stu-id="d4177-305">High Contrast mode is a Windows system setting that improves readability by using contrasting colors and font sizes that are beneficial for visually impaired users.</span></span> <span data-ttu-id="d4177-306"><xref:System.Windows.Forms.SystemInformation.HighContrast%2A> Свойство позволяет определить, установлен ли режим высокой контрастности.</span><span class="sxs-lookup"><span data-stu-id="d4177-306">The <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> property is provided to determine whether the High Contrast mode is set.</span></span>  
  
 <span data-ttu-id="d4177-307">Если свойство SystemInformation.HighContrast имеет значение `true`, то в приложении происходит следующее:</span><span class="sxs-lookup"><span data-stu-id="d4177-307">If SystemInformation.HighContrast is `true`, the application should:</span></span>  
  
-   <span data-ttu-id="d4177-308">Все элементы пользовательского интерфейса отображаются с использованием системной цветовой схемы.</span><span class="sxs-lookup"><span data-stu-id="d4177-308">Display all user interface elements using the system color scheme</span></span>  
  
-   <span data-ttu-id="d4177-309">Любая информация, передающаяся цветом, также передается с помощью визуальных или звуковых сигналов.</span><span class="sxs-lookup"><span data-stu-id="d4177-309">Convey by visual cues or sound any information that is conveyed through color.</span></span> <span data-ttu-id="d4177-310">Например, если определенный элемент списка выделен красным шрифтом, можно также отобразить его полужирным шрифтом, чтобы пользователь, не различающий цвета, видел, что элемент выделен.</span><span class="sxs-lookup"><span data-stu-id="d4177-310">For example, if particular list items are highlighted by using a red font, you could also add bold to the font, so that the user has a non-color cue that the items are highlighted.</span></span>  
  
-   <span data-ttu-id="d4177-311">Опускаются все рисунки или узоры за текстом.</span><span class="sxs-lookup"><span data-stu-id="d4177-311">Omit any images or patterns behind text</span></span>  
  
 <span data-ttu-id="d4177-312">Приложение должно проверять значение свойства <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> при запуске и отвечать на системное событие <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="d4177-312">The application should check the setting of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> when the application starts and respond to the system event <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span></span> <span data-ttu-id="d4177-313">При изменении значения свойства <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> происходит событие <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="d4177-313">The <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event is raised whenever the value of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> changes.</span></span>  
  
 <span data-ttu-id="d4177-314">В этом примере единственным элементом, не использующим системные параметры цвета, является `lblCompanyName`.</span><span class="sxs-lookup"><span data-stu-id="d4177-314">In our application, the only element that is not using the system settings for color is `lblCompanyName`.</span></span> <span data-ttu-id="d4177-315"><xref:System.Drawing.SystemColors> Класс используется для замены параметров цвета метки на выбранные пользователем системные цвета.</span><span class="sxs-lookup"><span data-stu-id="d4177-315">The <xref:System.Drawing.SystemColors> class is used to change the color settings of the label to the user-selected system colors.</span></span>  
  
#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a><span data-ttu-id="d4177-316">Эффективный способ обеспечения высокой контрастности</span><span class="sxs-lookup"><span data-stu-id="d4177-316">To enable High Contrast mode in an effective way</span></span>  
  
1. <span data-ttu-id="d4177-317">Создайте метод, задающий для метки системные цвета.</span><span class="sxs-lookup"><span data-stu-id="d4177-317">Create a method to set the colors of the label to the system colors.</span></span>  
  
    ```  
    ' Visual Basic  
    Private Sub SetColorScheme()  
       If SystemInformation.HighContrast Then  
          companyLabel.BackColor = SystemColors.Window  
          companyLabel.ForeColor = SystemColors.WindowText  
       Else  
          companyLabel.BackColor = Color.Blue  
          companyLabel.ForeColor = Color.Yellow  
       End If  
    End Sub  
  
    // C#  
    private void SetColorScheme()  
    {  
       if (SystemInformation.HighContrast)  
       {  
          companyLabel.BackColor = SystemColors.Window;  
          companyLabel.ForeColor = SystemColors.WindowText;  
       }  
       else  
       {  
          companyLabel.BackColor = Color.Blue;  
          companyLabel.ForeColor = Color.Yellow;  
       }  
    }  
    ```  
  
2. <span data-ttu-id="d4177-318">Вызовите процедуру `SetColorScheme` в конструкторе форм (`Public Sub New()` в Visual Basic; `public class Form1` в Visual C#).</span><span class="sxs-lookup"><span data-stu-id="d4177-318">Call the `SetColorScheme` procedure in the form constructor (`Public Sub New()` in Visual Basic and `public class Form1` in Visual C#).</span></span> <span data-ttu-id="d4177-319">Чтобы получить доступ к конструктору в Visual Basic, необходимо развернуть область с меткой **Код, автоматически созданный конструктором форм Windows**.</span><span class="sxs-lookup"><span data-stu-id="d4177-319">To access the constructor in Visual Basic, you will need to expand the region labeled **Windows Form Designer generated code**.</span></span>  
  
    ```  
    ' Visual Basic   
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
    }  
    ```  
  
3. <span data-ttu-id="d4177-320">Создайте процедуру обработки события с соответствующей подписью для реагирования на событие <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="d4177-320">Create an event procedure, with the appropriate signature, to respond to the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Sub UserPreferenceChanged(ByVal sender As Object, _  
    ByVal e As Microsoft.Win32.UserPreferenceChangedEventArgs)  
       SetColorScheme()  
    End Sub  
  
    // C#  
    public void UserPreferenceChanged(object sender,   
    Microsoft.Win32.UserPreferenceChangedEventArgs e)  
    {  
       SetColorScheme();  
    }  
    ```  
  
4. <span data-ttu-id="d4177-321">Добавьте код в конструктор форм после вызова метода `InitializeComponents`, чтобы подключить процедуру обработки событий к системному событию.</span><span class="sxs-lookup"><span data-stu-id="d4177-321">Add code to the form constructor, after the call to `InitializeComponents`, to hook up the event procedure to the system event.</span></span> <span data-ttu-id="d4177-322">Этот метод вызывает процедуру `SetColorScheme`.</span><span class="sxs-lookup"><span data-stu-id="d4177-322">This method calls the `SetColorScheme` procedure.</span></span>  
  
    ```  
    ' Visual Basic  
    Public Sub New()  
       MyBase.New()  
       InitializeComponent()  
       SetColorScheme()  
       AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
    End Sub  
  
    // C#  
    public Form1()  
    {  
       InitializeComponent();  
       SetColorScheme();  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          += new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
    }  
    ```  
  
5. <span data-ttu-id="d4177-323">Добавьте код в метод <xref:System.Windows.Forms.Control.Dispose%2A> формы перед вызовом метода <xref:System.Windows.Forms.Control.Dispose%2A> базового класса, чтобы освободить событие при закрытии приложения.</span><span class="sxs-lookup"><span data-stu-id="d4177-323">Add code to the form <xref:System.Windows.Forms.Control.Dispose%2A> method, before the call to the <xref:System.Windows.Forms.Control.Dispose%2A> method of the base class, to release the event when the application closes.</span></span> <span data-ttu-id="d4177-324">Чтобы получить доступ к методу <xref:System.Windows.Forms.Control.Dispose%2A> в Visual Basic, необходимо развернуть область "Код, автоматически созданный конструктором форм Windows".</span><span class="sxs-lookup"><span data-stu-id="d4177-324">To access the <xref:System.Windows.Forms.Control.Dispose%2A> method in Visual Basic, you will need to expand the region labeled Windows Form Designer generated code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4177-325">Код системного события выполняется в потоке, отдельном от основного приложения.</span><span class="sxs-lookup"><span data-stu-id="d4177-325">The system event code runs a thread separate from the main application.</span></span> <span data-ttu-id="d4177-326">Если не освободить событие, то код, связанный с событием, будет выполняться даже после закрытия программы.</span><span class="sxs-lookup"><span data-stu-id="d4177-326">If you do not release the event, the code that you hook up to the event will run even after the program is closed.</span></span>  
  
    ```  
    ' Visual Basic  
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)  
       If disposing Then  
          If Not (components Is Nothing) Then  
             components.Dispose()  
          End If  
       End If  
       RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _  
          AddressOf Me.UserPreferenceChanged  
       MyBase.Dispose(disposing)  
    End Sub  
  
    // C#  
    protected override void Dispose( bool disposing )  
    {  
       if( disposing )  
       {  
          if (components != null)   
          {  
             components.Dispose();  
          }  
       }  
       Microsoft.Win32.SystemEvents.UserPreferenceChanged   
          -= new Microsoft.Win32.UserPreferenceChangedEventHandler(  
          this.UserPreferenceChanged);  
       base.Dispose( disposing );  
    }  
    ```  
  
6. <span data-ttu-id="d4177-327">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="d4177-327">Press F5 to run the application.</span></span>  
  
## <a name="conveying-important-information-by-means-other-than-sound"></a><span data-ttu-id="d4177-328">Передача важной информации способами помимо звукового сигнала</span><span class="sxs-lookup"><span data-stu-id="d4177-328">Conveying Important Information by Means Other Than Sound</span></span>  
 <span data-ttu-id="d4177-329">В этом приложении никакая информация не предоставляется только с помощью звукового сигнала.</span><span class="sxs-lookup"><span data-stu-id="d4177-329">In this application, no information is conveyed by sound alone.</span></span> <span data-ttu-id="d4177-330">Если вы используете звук в своем приложении, следует также предусмотреть альтернативные способы передачи информации.</span><span class="sxs-lookup"><span data-stu-id="d4177-330">If you use sound in your application, then you should supply the information by some other means as well.</span></span>  
  
#### <a name="to-supply-information-by-some-other-means-than-sound"></a><span data-ttu-id="d4177-331">Обеспечение передачи важной информации способами помимо звукового сигнала</span><span class="sxs-lookup"><span data-stu-id="d4177-331">To supply information by some other means than sound</span></span>  
  
1. <span data-ttu-id="d4177-332">Сделайте строку заголовка мигающей с помощью функции FlashWindow интерфейса Windows API.</span><span class="sxs-lookup"><span data-stu-id="d4177-332">Make the title bar flash by using the Windows API function FlashWindow.</span></span> <span data-ttu-id="d4177-333">Пример вызова функций Windows API, см. в разделе [Пошаговое руководство: Вызов Windows API](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span><span class="sxs-lookup"><span data-stu-id="d4177-333">For an example of how to call Windows API functions, see [Walkthrough: Calling Windows APIs](~/docs/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4177-334">У пользователя может быть включена служба визуального оповещения Windows, что также приведет к миганию окна при подаче системных звуковых сигналов через встроенные динамики компьютера.</span><span class="sxs-lookup"><span data-stu-id="d4177-334">The user may have the Windows SoundSentry service enabled, which will also cause the window to flash when the system sounds are played through the computer's built-in speaker.</span></span>  
  
2. <span data-ttu-id="d4177-335">Выводите важную информацию в немодальном окне, чтобы пользователь мог реагировать на нее.</span><span class="sxs-lookup"><span data-stu-id="d4177-335">Display the important information in a non-modal window so that the user may respond to it.</span></span>  
  
3. <span data-ttu-id="d4177-336">При выводе окна сообщения передавайте ему фокус клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="d4177-336">Display a message box that acquires the keyboard focus.</span></span> <span data-ttu-id="d4177-337">Этот способ не следует применять в момент, когда пользователь может осуществлять ввод с клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="d4177-337">Avoid this method when the user may be typing.</span></span>  
  
4. <span data-ttu-id="d4177-338">Выводите индикатор состояния в области уведомлений о состоянии панели задач.</span><span class="sxs-lookup"><span data-stu-id="d4177-338">Display a status indicator in the status notification area of the taskbar.</span></span> <span data-ttu-id="d4177-339">Подробнее см. в разделе [Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="d4177-339">For details, see [Adding Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="d4177-340">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="d4177-340">Testing the Application</span></span>  
 <span data-ttu-id="d4177-341">Перед развертыванием приложения необходимо протестировать реализованные специальные возможности.</span><span class="sxs-lookup"><span data-stu-id="d4177-341">Before deploying the application, you should test the accessibility features that you have implemented.</span></span>  
  
#### <a name="to-test-accessibility-features"></a><span data-ttu-id="d4177-342">Тестирование специальных возможностей</span><span class="sxs-lookup"><span data-stu-id="d4177-342">To test accessibility features</span></span>  
  
1. <span data-ttu-id="d4177-343">Для проверки доступа с клавиатуры отключите мышь и перейдите к каждому элемента пользовательского интерфейса, используя только клавиатуру.</span><span class="sxs-lookup"><span data-stu-id="d4177-343">To test keyboard access, unplug the mouse and navigate the user interface for each feature using only the keyboard.</span></span> <span data-ttu-id="d4177-344">Убедитесь в том, что все задачи можно выполнить с помощью клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="d4177-344">Ensure that all tasks may be performed using the keyboard only.</span></span>  
  
2. <span data-ttu-id="d4177-345">Для проверки режима высокой контрастности используйте компонент "Специальные возможности" на панели управления.</span><span class="sxs-lookup"><span data-stu-id="d4177-345">To test support of High Contrast, choose the Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="d4177-346">Выберите вкладку "Экран" и установите флажок "Высокая контрастность".</span><span class="sxs-lookup"><span data-stu-id="d4177-346">Click the Display tab and select the Use High Contrast check box.</span></span> <span data-ttu-id="d4177-347">Перейдите по всем элементам управления и убедитесь в том, что отражаются изменения цвета и шрифта.</span><span class="sxs-lookup"><span data-stu-id="d4177-347">Navigate through all user interface elements to ensure that the color and font changes are reflected.</span></span> <span data-ttu-id="d4177-348">Кроме того, убедитесь в том, что отсутствуют рисунки или узоры под текстом.</span><span class="sxs-lookup"><span data-stu-id="d4177-348">Also, ensure that images or patterns drawn behind text are omitted.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4177-349">В Windows NT 4 значок "Специальные возможности" на панели управления отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d4177-349">Windows NT 4 does not have an Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="d4177-350">Поэтому этот способ изменения значения свойства SystemInformation.HighContrast не работает в Windows NT 4.</span><span class="sxs-lookup"><span data-stu-id="d4177-350">Thus, this procedure for changing the SystemInformation.HighContrast setting does not work in Windows NT 4.</span></span>  
  
3. <span data-ttu-id="d4177-351">Доступны также другие средства тестирования специальных возможностей приложения.</span><span class="sxs-lookup"><span data-stu-id="d4177-351">Other tools are readily available for testing the accessibility of an application.</span></span>  
  
4. <span data-ttu-id="d4177-352">Для тестирования демонстрации фокуса клавиатуры запустите экранную лупу.</span><span class="sxs-lookup"><span data-stu-id="d4177-352">To test exposing the keyboard focus, run Magnifier.</span></span> <span data-ttu-id="d4177-353">(Для этого нажмите кнопку **Пуск**, выберите **Программы**, **Стандартные**, **Специальные возможности**, а затем щелкните **Экранная лупа**.)</span><span class="sxs-lookup"><span data-stu-id="d4177-353">(To open it, click the **Start** menu, point to **Programs**, point to **Accessories**, point to **Accessibility**, and then click **Magnifier**).</span></span> <span data-ttu-id="d4177-354">Выполните переходы по интерфейсу пользователя, используя клавишу TAB и мышь.</span><span class="sxs-lookup"><span data-stu-id="d4177-354">Navigate the user interface using both keyboard tabbing and the mouse.</span></span> <span data-ttu-id="d4177-355">Убедитесь в том, что все переходы правильно отображаются **экранной лупой**.</span><span class="sxs-lookup"><span data-stu-id="d4177-355">Ensure that all navigation is tracked properly in **Magnifier**.</span></span>  
  
5. <span data-ttu-id="d4177-356">Для проверки отображения элементов экрана запустите программу Inspect и перейдите к каждому элементу с помощью мыши и клавиши TAB.</span><span class="sxs-lookup"><span data-stu-id="d4177-356">To test exposing screen elements, run Inspect, and use both the mouse and the TAB key to reach each element.</span></span> <span data-ttu-id="d4177-357">Убедитесь в том, что сведения, выводящиеся в полях "Name", "State", "Role", "Location" и "Value" окна программы Inspect для каждого объекта в интерфейсе являются полезными для пользователя.</span><span class="sxs-lookup"><span data-stu-id="d4177-357">Ensure that the information presented in the Name, State, Role, Location, and Value fields of the Inspect window is meaningful to the user for each object in the UI.</span></span>
