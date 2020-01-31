---
title: Размещение элемента управления Windows Forms в WPF с помощью XAML
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 1aef42cb-4cfb-44b4-9a7a-c02632d3d9c7
ms.openlocfilehash: 2c5764ac2dfd9f5747087cc76e3971c002f12b90
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794193"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml"></a><span data-ttu-id="93552-102">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF с помощью XAML</span><span class="sxs-lookup"><span data-stu-id="93552-102">Walkthrough: Hosting a Windows Forms Control in WPF by Using XAML</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="93552-103">предоставляет множество элементов управления с богатым набором функций.</span><span class="sxs-lookup"><span data-stu-id="93552-103">provides many controls with a rich feature set.</span></span> <span data-ttu-id="93552-104">Однако иногда может потребоваться использовать Windows Forms элементы управления на страницах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93552-104">However, you may sometimes want to use Windows Forms controls on your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pages.</span></span> <span data-ttu-id="93552-105">Например, у вас может быть существенный вклад в существующие элементы управления Windows Forms или имеется элемент управления Windows Forms, обеспечивающий уникальную функциональность.</span><span class="sxs-lookup"><span data-stu-id="93552-105">For example, you may have a substantial investment in existing Windows Forms controls, or you may have a Windows Forms control that provides unique functionality.</span></span>  
  
 <span data-ttu-id="93552-106">В этом пошаговом руководстве показано, как разместить элемент управления Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> на странице [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93552-106">This walkthrough shows you how to host a Windows Forms <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="93552-107">Полный листинг кода задач, приведенных в этом пошаговом руководстве, см. в разделе [Размещение элемента управления Windows Forms в WPF с помощью примера XAML](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span><span class="sxs-lookup"><span data-stu-id="93552-107">For a complete code listing of the tasks shown in this walkthrough, see [Hosting a Windows Forms Control in WPF by Using XAML Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/HostingWfInWpfWithXaml).</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="93552-108">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="93552-108">Prerequisites</span></span>  

<span data-ttu-id="93552-109">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="93552-109">You need Visual Studio to complete this walkthrough.</span></span>  
  
## <a name="hosting-the-windows-forms-control"></a><span data-ttu-id="93552-110">Размещение элемента управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93552-110">Hosting the Windows Forms Control</span></span>  
  
#### <a name="to-host-the-maskedtextbox-control"></a><span data-ttu-id="93552-111">Чтобы разместить элемент управления MaskedTextBox, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="93552-111">To host the MaskedTextBox control</span></span>  
  
1. <span data-ttu-id="93552-112">Создайте проект приложения WPF с именем `HostingWfInWpfWithXaml`.</span><span class="sxs-lookup"><span data-stu-id="93552-112">Create a WPF Application project named `HostingWfInWpfWithXaml`.</span></span>  
  
2. <span data-ttu-id="93552-113">Добавьте ссылки на следующие сборки.</span><span class="sxs-lookup"><span data-stu-id="93552-113">Add references to the following assemblies.</span></span>  
  
    - <span data-ttu-id="93552-114">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="93552-114">WindowsFormsIntegration</span></span>  
  
    - <span data-ttu-id="93552-115">System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="93552-115">System.Windows.Forms</span></span>  
  
3. <span data-ttu-id="93552-116">Откройте файл MainWindow. XAML в конструкторе WPF.</span><span class="sxs-lookup"><span data-stu-id="93552-116">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
4. <span data-ttu-id="93552-117">В элементе <xref:System.Windows.Window> добавьте следующее сопоставление пространства имен.</span><span class="sxs-lookup"><span data-stu-id="93552-117">In the <xref:System.Windows.Window> element, add the following namespace mapping.</span></span> <span data-ttu-id="93552-118">Сопоставление пространства имен `wf` устанавливает ссылку на сборку, содержащую элемент управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="93552-118">The `wf` namespace mapping establishes a reference to the assembly that contains the Windows Forms control.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5. <span data-ttu-id="93552-119">В элемент <xref:System.Windows.Controls.Grid> добавьте следующий код XAML.</span><span class="sxs-lookup"><span data-stu-id="93552-119">In the <xref:System.Windows.Controls.Grid> element add the following XAML.</span></span>  
  
     <span data-ttu-id="93552-120">Элемент управления <xref:System.Windows.Forms.MaskedTextBox> создается как дочерний элемент управления <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="93552-120">The <xref:System.Windows.Forms.MaskedTextBox> control is created as a child of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control.</span></span>  
  
     [!code-xaml[HostingWfInWpfWithXaml#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWpfWithXaml/CSharp/HostingWfInWpf/Window1.xaml#3)]  
  
6. <span data-ttu-id="93552-121">Нажмите клавишу F5 для построения и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="93552-121">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93552-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="93552-122">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="93552-123">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="93552-123">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="93552-124">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="93552-124">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="93552-125">Пошаговое руководство. Размещение составного элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="93552-125">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="93552-126">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93552-126">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="93552-127">Элементы управления Windows Forms и эквивалентные элементы управления WPF</span><span class="sxs-lookup"><span data-stu-id="93552-127">Windows Forms Controls and Equivalent WPF Controls</span></span>](windows-forms-controls-and-equivalent-wpf-controls.md)
- [<span data-ttu-id="93552-128">Размещение элемента управления Windows Forms в WPF с помощью примера XAML</span><span class="sxs-lookup"><span data-stu-id="93552-128">Hosting a Windows Forms Control in WPF by Using XAML Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160000)
