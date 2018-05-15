---
title: Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF с помощью XAML
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: b55a51a7ca16416b6963c57395da2f2a88a55648
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="f3146-102">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="f3146-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="f3146-103"> предоставляет множество элементов управления с богатым набором функций.</span><span class="sxs-lookup"><span data-stu-id="f3146-103"> provides many controls with a rich feature set.</span></span> <span data-ttu-id="f3146-104">Тем не менее, иногда можно использовать [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страниц.</span><span class="sxs-lookup"><span data-stu-id="f3146-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="f3146-105">Например, может получить значительные преимущества в существующих [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления, или, возможно, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемент управления, который предоставляет уникальный функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="f3146-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="f3146-106">В этом пошаговом руководстве показано, как разместить форму Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3146-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="f3146-107">Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [размещение элемента управления Windows Forms в WPF с помощью XAML-пример](http://go.microsoft.com/fwlink/?LinkID=160000).</span><span class="sxs-lookup"><span data-stu-id="f3146-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](http://go.microsoft.com/fwlink/?LinkID=160000).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f3146-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f3146-108">Prerequisites</span></span>  
 <span data-ttu-id="f3146-109">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="f3146-109">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="f3146-110">.</span><span class="sxs-lookup"><span data-stu-id="f3146-110">.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="f3146-111">Размещение элемента управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3146-111">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="f3146-112">Чтобы разместить элемент управления MaskedTextBox, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f3146-112">To host the MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="f3146-113">Создание проекта приложения WPF с именем `HostingWfInWpfWithXaml`.</span><span class="sxs-lookup"><span data-stu-id="f3146-113">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2.  <span data-ttu-id="f3146-114">Добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="f3146-114">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="f3146-115">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="f3146-115">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="f3146-116">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="f3146-116">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="f3146-117">Откройте файл MainWindow.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f3146-117">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="f3146-118">В <xref:System.Windows.Window> элемента, добавьте следующее сопоставление пространства имен.</span><span class="sxs-lookup"><span data-stu-id="f3146-118">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="f3146-119">`wf` Сопоставление пространства имен устанавливает ссылку на сборку, содержащую элемент управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f3146-119">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="f3146-120">В <xref:System.Windows.Controls.Grid> элемент добавьте следующий код XAML.</span><span class="sxs-lookup"><span data-stu-id="f3146-120">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="f3146-121"><xref:System.Windows.Forms.MaskedTextBox> Будет создан как дочерний элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost> управления.</span><span class="sxs-lookup"><span data-stu-id="f3146-121">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6.  <span data-ttu-id="f3146-122">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="f3146-122">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3146-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f3146-123">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="f3146-124">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="f3146-124">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="f3146-125">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="f3146-125">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [<span data-ttu-id="f3146-126">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="f3146-126">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="f3146-127">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f3146-127">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="f3146-128">Элементы управления Windows Forms и эквивалентные элементы управления WPF</span><span class="sxs-lookup"><span data-stu-id="f3146-128">Windows Forms Controls and Equivalent WPF Controls</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)  
 [<span data-ttu-id="f3146-129">Размещение элемента управления Windows Forms в WPF с помощью XAML-пример</span><span class="sxs-lookup"><span data-stu-id="f3146-129">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160000)
