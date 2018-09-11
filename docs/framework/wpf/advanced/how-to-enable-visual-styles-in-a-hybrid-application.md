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
ms.openlocfilehash: f4684e277335a119d41d5bd79d504ed37a76d6fc
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44268475"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a><span data-ttu-id="ef36a-102">Практическое руководство. Включение визуальных стилей в гибридном приложении</span><span class="sxs-lookup"><span data-stu-id="ef36a-102">How to: Enable Visual Styles in a Hybrid Application</span></span>
<span data-ttu-id="ef36a-103">В этом разделе показано, как включить [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] визуальные стили на [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] размещение элементов управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложения на основе.</span><span class="sxs-lookup"><span data-stu-id="ef36a-103">This topic shows how to enable [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visual styles on a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hosted in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
 <span data-ttu-id="ef36a-104">Если приложение вызывает <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод, большая часть вашей [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления будут автоматически использовать визуальные стили, если приложение запускается на компьютере [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef36a-104">If your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method, most of your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls will automatically use visual styles when your application is run on [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)].</span></span> <span data-ttu-id="ef36a-105">Дополнительные сведения см. в разделе [отображение элементов управления с использованием стилей оформления](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).</span><span class="sxs-lookup"><span data-stu-id="ef36a-105">For more information, see [Rendering Controls with Visual Styles](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md).</span></span>  
  
 <span data-ttu-id="ef36a-106">Полный пример кода для задач, приведенных в этом разделе, см. в разделе [включения визуальных стилей в пример гибридного приложения](https://go.microsoft.com/fwlink/?LinkID=159986).</span><span class="sxs-lookup"><span data-stu-id="ef36a-106">For a complete code listing of the tasks illustrated in this topic, see [Enabling Visual Styles in a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=159986).</span></span>  
  
## <a name="enabling-windows-forms-visual-styles"></a><span data-ttu-id="ef36a-107">Включение визуальных стилей Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef36a-107">Enabling Windows Forms Visual Styles</span></span>  
  
#### <a name="to-enable-windows-forms-visual-styles"></a><span data-ttu-id="ef36a-108">Чтобы включить визуальные стили Windows Forms, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ef36a-108">To enable Windows Forms visual styles</span></span>  
  
1.  <span data-ttu-id="ef36a-109">Создание [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] проект приложения с именем `HostingWfWithVisualStyles`.</span><span class="sxs-lookup"><span data-stu-id="ef36a-109">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Application project named `HostingWfWithVisualStyles`.</span></span>  
  
2.  <span data-ttu-id="ef36a-110">В обозревателе решений добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="ef36a-110">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="ef36a-111">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="ef36a-111">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="ef36a-112">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="ef36a-112">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="ef36a-113">В области элементов дважды щелкните <xref:System.Windows.Controls.Grid> значок, чтобы поместить <xref:System.Windows.Controls.Grid> элемента в рабочей области конструирования.</span><span class="sxs-lookup"><span data-stu-id="ef36a-113">In the Toolbox, double-click the <xref:System.Windows.Controls.Grid> icon to place a <xref:System.Windows.Controls.Grid> element on the design surface.</span></span>  
  
4.  <span data-ttu-id="ef36a-114">В окне «Свойства» задайте значения <xref:System.Windows.FrameworkElement.Height%2A> и <xref:System.Windows.FrameworkElement.Width%2A> свойства **автоматически**.</span><span class="sxs-lookup"><span data-stu-id="ef36a-114">In the Properties window, set the values of the <xref:System.Windows.FrameworkElement.Height%2A> and <xref:System.Windows.FrameworkElement.Width%2A> properties to **Auto**.</span></span>  
  
5.  <span data-ttu-id="ef36a-115">В представлении конструирования или XAML, выберите <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="ef36a-115">In Design view or XAML view, select the <xref:System.Windows.Window>.</span></span>  
  
6.  <span data-ttu-id="ef36a-116">В окне «Свойства» щелкните **события** вкладки.</span><span class="sxs-lookup"><span data-stu-id="ef36a-116">In the Properties window, click the **Events** tab.</span></span>  
  
7.  <span data-ttu-id="ef36a-117">Дважды щелкните <xref:System.Windows.FrameworkElement.Loaded> событий.</span><span class="sxs-lookup"><span data-stu-id="ef36a-117">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>
  
8.  <span data-ttu-id="ef36a-118">В файле MainWindow.xaml.vb или MainWindow.xaml.cs вставьте следующий код для обработки <xref:System.Windows.FrameworkElement.Loaded> событий.</span><span class="sxs-lookup"><span data-stu-id="ef36a-118">In MainWindow.xaml.vb or MainWindow.xaml.cs, insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. <span data-ttu-id="ef36a-119">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ef36a-119">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="ef36a-120">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Элемент управления отрисовывается с использованием стилей оформления.</span><span class="sxs-lookup"><span data-stu-id="ef36a-120">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with visual styles.</span></span>  
  
## <a name="disabling-windows-forms-visual-styles"></a><span data-ttu-id="ef36a-121">Отключение визуальных стилей Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef36a-121">Disabling Windows Forms Visual Styles</span></span>  
 <span data-ttu-id="ef36a-122">Чтобы отключить визуальные стили, просто удалите вызов <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="ef36a-122">To disable visual styles, simply remove the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
#### <a name="to-disable-windows-forms-visual-styles"></a><span data-ttu-id="ef36a-123">Чтобы отключить визуальные стили Windows Forms, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ef36a-123">To disable Windows Forms visual styles</span></span>  
  
1.  <span data-ttu-id="ef36a-124">Откройте файл MainWindow.xaml.vb или MainWindow.xaml.cs в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="ef36a-124">Open MainWindow.xaml.vb or MainWindow.xaml.cs in the Code Editor.</span></span>  
  
2.  <span data-ttu-id="ef36a-125">Закомментируйте вызов <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="ef36a-125">Comment out the call to the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> method.</span></span>  
  
3.  <span data-ttu-id="ef36a-126">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="ef36a-126">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="ef36a-127">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Элемент управления отрисовывается с системным стилем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ef36a-127">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is painted with the default system style.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef36a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ef36a-128">See Also</span></span>  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>  
 <xref:System.Windows.Forms.VisualStyles>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="ef36a-129">Отрисовка элементов управления с применением визуальных стилей</span><span class="sxs-lookup"><span data-stu-id="ef36a-129">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 [<span data-ttu-id="ef36a-130">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="ef36a-130">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
