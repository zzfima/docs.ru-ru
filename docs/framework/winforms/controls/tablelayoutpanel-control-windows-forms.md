---
title: Элемент управления TableLayoutPanel (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- layout [Windows Forms]
- controls [Windows Forms], sizing
- sizing [Windows Forms], automatic
- layout [Windows Forms], TableLayoutPanel control
- automatic sizing
ms.assetid: f55175c6-424e-4782-a86e-3f79c1550235
ms.openlocfilehash: 3615ab1f9a9076b8db0e5fde1e5bd4a1a804f3bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538532"
---
# <a name="tablelayoutpanel-control-windows-forms"></a><span data-ttu-id="14a50-102">Элемент управления TableLayoutPanel (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="14a50-102">TableLayoutPanel Control (Windows Forms)</span></span>
<span data-ttu-id="14a50-103">Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> упорядочивает содержимое в сетке.</span><span class="sxs-lookup"><span data-stu-id="14a50-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="14a50-104">Поскольку макет выполняется как во время разработки, так и во время выполнения, его можно изменять динамически по мере изменения среды приложения.</span><span class="sxs-lookup"><span data-stu-id="14a50-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="14a50-105">Это позволяет пропорционально изменять размер элементов управления в панели, так чтобы они учитывали изменения, такие как изменение размера родительского элемента управления или длины текста в случае локализации.</span><span class="sxs-lookup"><span data-stu-id="14a50-105">This gives the controls in the panel the ability to proportionally resize, so it can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14a50-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="14a50-106">In This Section</span></span>  
 [<span data-ttu-id="14a50-107">Общие сведения об элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="14a50-107">TableLayoutPanel Control Overview</span></span>](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-overview.md)  
 <span data-ttu-id="14a50-108">Основные понятия, связанные с элементом управления <xref:System.Windows.Forms.TableLayoutPanel>, который позволяет создавать макет со строками и столбцами.</span><span class="sxs-lookup"><span data-stu-id="14a50-108">Introduces the general concepts of the <xref:System.Windows.Forms.TableLayoutPanel> control, which allows you to create a layout with rows and columns.</span></span>  
  
 [<span data-ttu-id="14a50-109">Советы по использованию элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="14a50-109">Best Practices for the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/best-practices-for-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="14a50-110">Описаны рекомендации, помогающие наиболее эффективно использовать возможности макета элемента управления <xref:System.Windows.Forms.TableLayoutPanel>. </span><span class="sxs-lookup"><span data-stu-id="14a50-110">Outlines recommendations to help you get the most out of the layout features of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="14a50-111">Автоматическое изменение размеров элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="14a50-111">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="14a50-112">Объясняются способы поддержки элементом управления <xref:System.Windows.Forms.TableLayoutPanel> автоматического изменения размеров.</span><span class="sxs-lookup"><span data-stu-id="14a50-112">Explains the ways in which the <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior.</span></span>  
  
 [<span data-ttu-id="14a50-113">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="14a50-113">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 <span data-ttu-id="14a50-114">Показано, как осуществляется привязка и закрепление дочерних элементов управления в элементе управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="14a50-114">Shows how to anchor and dock child controls in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="14a50-115">Практическое руководство. Формирование макета формы Windows Forms с учетом будущей локализации</span><span class="sxs-lookup"><span data-stu-id="14a50-115">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 <span data-ttu-id="14a50-116">Демонстрирует использование элемента управления <xref:System.Windows.Forms.TableLayoutPanel> для создания формы, оптимизированной для локализации.</span><span class="sxs-lookup"><span data-stu-id="14a50-116">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to localization.</span></span>  
  
 [<span data-ttu-id="14a50-117">Практическое руководство. Создание в Windows Forms формы для ввода данных, размер которой можно изменять</span><span class="sxs-lookup"><span data-stu-id="14a50-117">How to: Create a Resizable Windows Form for Data Entry</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-resizable-windows-form-for-data-entry.md)  
 <span data-ttu-id="14a50-118">Демонстрирует использование элемента управления <xref:System.Windows.Forms.TableLayoutPanel> для создания формы, оптимизированной для изменения размеров.</span><span class="sxs-lookup"><span data-stu-id="14a50-118">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to resizing.</span></span>  
  
1.  <span data-ttu-id="14a50-119">[Практическое руководство. Выравнивание и растягивание элемента управления в элементе управления TableLayoutPanel](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="14a50-119">[How to: Align and Stretch a Control in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171688\(v=vs.110\))</span></span>  
  
2.  <span data-ttu-id="14a50-120">[Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="14a50-120">[How to: Span Rows and Columns in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171687\(v=vs.110\))</span></span>  
  
3.  <span data-ttu-id="14a50-121">[Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="14a50-121">[How to: Edit Columns and Rows in a TableLayoutPanel Control](http://msdn.microsoft.com/library/ms171686\(v=vs.110\))</span></span>  
  
4.  <span data-ttu-id="14a50-122">[Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="14a50-122">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](http://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
## <a name="reference"></a><span data-ttu-id="14a50-123">Ссылка</span><span class="sxs-lookup"><span data-stu-id="14a50-123">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="14a50-124">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="14a50-124">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 <span data-ttu-id="14a50-125">Содержит справочную документацию по типу <xref:System.Windows.Forms.TableLayoutSettings>.</span><span class="sxs-lookup"><span data-stu-id="14a50-125">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutSettings> type.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="14a50-126">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="14a50-126">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="14a50-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="14a50-127">Related Sections</span></span>  
 [<span data-ttu-id="14a50-128">Локализация</span><span class="sxs-lookup"><span data-stu-id="14a50-128">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)  
 <span data-ttu-id="14a50-129">Обзор разделов, связанных с локализацией.</span><span class="sxs-lookup"><span data-stu-id="14a50-129">Provides an overview of topics relating to localization.</span></span>  
  
 <span data-ttu-id="14a50-130">См. также [локализация приложений](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\)) или [локализация приложений](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="14a50-130">Also see [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.110\)) or [Localizing Applications](http://msdn.microsoft.com/library/z68135h5\(v=vs.120\))</span></span>
