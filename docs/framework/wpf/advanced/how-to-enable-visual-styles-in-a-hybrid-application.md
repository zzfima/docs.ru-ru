---
title: Практическое руководство. Включение визуальных стилей в гибридном приложении
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: dd52313e9100f9c6a1141b53ccc5a23a4b54410a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789921"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="92eb5-102">Практическое руководство. Включение визуальных стилей в гибридном приложении</span><span class="sxs-lookup"><span data-stu-id="92eb5-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="92eb5-103">В этом разделе показано, как включить визуальные стили для элемента управления Windows Forms, размещенного в приложении на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92eb5-103">This topic shows how to enable visual styles on a Windows Forms control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="92eb5-104">Если приложение вызывает метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>, большинство элементов управления Windows Forms будет автоматически использовать стили оформления.</span><span class="sxs-lookup"><span data-stu-id="92eb5-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your Windows Forms controls will automatically use visual styles.</span></span> <span data-ttu-id="92eb5-105">Дополнительные сведения см. в статье [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md) (Отрисовка элементов управления со стилями оформления).</span><span class="sxs-lookup"><span data-stu-id="92eb5-105">For more information, see [Rendering Controls with Visual Styles](../../winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="92eb5-106">Полный листинг кода задач, показанных в этом разделе, см. в разделе [Включение визуальных стилей в примере гибридного приложения](https://go.microsoft.com/fwlink/?LinkID=159986).</span><span class="sxs-lookup"><span data-stu-id="92eb5-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="92eb5-107">Включение визуальных стилей Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92eb5-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="92eb5-108">Чтобы включить визуальные стили Windows Forms, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="92eb5-108">To enable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="92eb5-109">Создайте проект приложения [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с именем `HostingWfWithVisualStyles`.</span><span class="sxs-lookup"><span data-stu-id="92eb5-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2. <span data-ttu-id="92eb5-110">В обозревателе решений добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="92eb5-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="92eb5-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="92eb5-111">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="92eb5-112">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="92eb5-112">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="92eb5-113">На панели элементов дважды щелкните значок <xref:System.Windows.Controls.Grid>, чтобы поместить элемент <xref:System.Windows.Controls.Grid> в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="92eb5-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4. <span data-ttu-id="92eb5-114">В окно свойств задайте для свойств <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> значение **Авто**.</span><span class="sxs-lookup"><span data-stu-id="92eb5-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5. <span data-ttu-id="92eb5-115">В представление конструирования или представлении XAML выберите <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="92eb5-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6. <span data-ttu-id="92eb5-116">В окно свойств перейдите на вкладку **события** .</span><span class="sxs-lookup"><span data-stu-id="92eb5-116">In the Properties window, click the **Events** tab.</span></span>  
  
7. <span data-ttu-id="92eb5-117">Дважды щелкните событие <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="92eb5-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8. <span data-ttu-id="92eb5-118">В файле MainWindow. XAML. vb или MainWindow.xaml.cs вставьте следующий код, обрабатывающий событие <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="92eb5-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="92eb5-119">Нажмите клавишу F5 для построения и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="92eb5-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="92eb5-120">Элемент управления Windows Forms окрашен в стили оформления.</span><span class="sxs-lookup"><span data-stu-id="92eb5-120">The Windows Forms control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="92eb5-121">Отключение визуальных стилей Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92eb5-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="92eb5-122">Чтобы отключить стили оформления, просто удалите вызов метода <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="92eb5-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="92eb5-123">Чтобы отключить визуальные стили Windows Forms, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="92eb5-123">To disable Windows Forms visual styles</span></span>  
  
1. <span data-ttu-id="92eb5-124">Откройте файл MainWindow.xaml.vb или MainWindow.xaml.cs в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="92eb5-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2. <span data-ttu-id="92eb5-125">Закомментируйте вызов метода <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="92eb5-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3. <span data-ttu-id="92eb5-126">Нажмите клавишу F5 для построения и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="92eb5-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="92eb5-127">Элемент управления Windows Forms закрашивается стандартным стилем системы.</span><span class="sxs-lookup"><span data-stu-id="92eb5-127">The Windows Forms control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92eb5-128">См. также:</span><span class="sxs-lookup"><span data-stu-id="92eb5-128">See also</span></span>

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="92eb5-129">Отрисовка элементов управления с применением визуальных стилей</span><span class="sxs-lookup"><span data-stu-id="92eb5-129">Rendering Controls with Visual Styles</span></span>](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [<span data-ttu-id="92eb5-130">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="92eb5-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
