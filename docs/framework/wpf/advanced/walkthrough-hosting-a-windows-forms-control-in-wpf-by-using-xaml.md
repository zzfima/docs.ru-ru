---
title: Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF с помощью XAML
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 10554145de9725bb4cfc655ed88195dce28d739c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032114"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="0a27d-102">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="0a27d-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="0a27d-103">предоставляет множество элементов управления с богатым набором функций.</span><span class="sxs-lookup"><span data-stu-id="0a27d-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="0a27d-104">Тем не менее, иногда можно использовать [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страниц.</span><span class="sxs-lookup"><span data-stu-id="0a27d-104">However, you may sometimes want to use [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="0a27d-105">Например, может получить значительные преимущества в существующих [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления, или имеете [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления, предоставляющий уникальную функциональность.</span><span class="sxs-lookup"><span data-stu-id="0a27d-105">For example, you may have a substantial investment in existing [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls, or you may have a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="0a27d-106">В этом пошаговом руководстве показано, как разместить форм Windows <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] страницы с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a27d-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="0a27d-107">Полный пример кода для задач, демонстрируемых в этом пошаговом руководстве, см. в разделе [размещение элемента управления Windows Forms в WPF с помощью XAML примером](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span><span class="sxs-lookup"><span data-stu-id="0a27d-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="0a27d-108">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="0a27d-108">Prerequisites</span></span>  

<span data-ttu-id="0a27d-109">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0a27d-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="0a27d-110">Размещение элемента управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0a27d-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="0a27d-111">Чтобы разместить элемент управления MaskedTextBox, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0a27d-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="0a27d-112">Создание проекта приложения WPF с именем `HostingWfInWpfWithXaml`.</span><span class="sxs-lookup"><span data-stu-id="0a27d-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="0a27d-113">Добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="0a27d-113">Add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="0a27d-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="0a27d-114">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="0a27d-115">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="0a27d-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="0a27d-116">Откройте файл MainWindow.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a27d-116">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4. <span data-ttu-id="0a27d-117">В <xref:System.Windows.Window> элемента, добавьте следующее сопоставление пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0a27d-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="0a27d-118">`wf` Сопоставление пространства имен устанавливает ссылку на сборку, содержащую элемент управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0a27d-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="0a27d-119">В <xref:System.Windows.Controls.Grid> элемент добавьте следующий XAML.</span><span class="sxs-lookup"><span data-stu-id="0a27d-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="0a27d-120"><xref:System.Windows.Forms.MaskedTextBox> Элемент управления создается в качестве дочернего элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0a27d-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="0a27d-121">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="0a27d-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a27d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0a27d-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="0a27d-123">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0a27d-123">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="0a27d-124">Пошаговое руководство: Размещение элемента управления Windows Forms в WPF</span><span class="sxs-lookup"><span data-stu-id="0a27d-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="0a27d-125">Пошаговое руководство: Размещение Windows Forms составного элемента управления в WPF</span><span class="sxs-lookup"><span data-stu-id="0a27d-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="0a27d-126">Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0a27d-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="0a27d-127">Элементы управления Windows Forms и эквивалентные элементы управления WPF</span><span class="sxs-lookup"><span data-stu-id="0a27d-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="0a27d-128">Размещение элемента управления Windows Forms в WPF с помощью примера XAML</span><span class="sxs-lookup"><span data-stu-id="0a27d-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160000)
