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
ms.openlocfilehash: b51d3bd8e9d8816dfae6c10fc752adb0b3cea59c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337790"
---
# <a name="tablelayoutpanel-control-windows-forms"></a><span data-ttu-id="56a8f-102">Элемент управления TableLayoutPanel (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="56a8f-102">TableLayoutPanel Control (Windows Forms)</span></span>
<span data-ttu-id="56a8f-103">Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> упорядочивает содержимое в сетке.</span><span class="sxs-lookup"><span data-stu-id="56a8f-103">The <xref:System.Windows.Forms.TableLayoutPanel> control arranges its contents in a grid.</span></span> <span data-ttu-id="56a8f-104">Так как макет строится как во время разработки, так и во время выполнения, его можно изменять динамически по мере изменения среды приложения.</span><span class="sxs-lookup"><span data-stu-id="56a8f-104">Because the layout is performed both at design time and run time, it can change dynamically as the application environment changes.</span></span> <span data-ttu-id="56a8f-105">Это позволяет пропорционально изменять размер элементов управления в панели, так чтобы они учитывали изменения, такие как изменение размера родительского элемента управления или длины текста в случае локализации.</span><span class="sxs-lookup"><span data-stu-id="56a8f-105">This gives the controls in the panel the ability to proportionally resize, so it can respond to changes such as the parent control resizing or text length changing due to localization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56a8f-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="56a8f-106">In This Section</span></span>  
 [<span data-ttu-id="56a8f-107">Общие сведения об элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="56a8f-107">TableLayoutPanel Control Overview</span></span>](tablelayoutpanel-control-overview.md)  
 <span data-ttu-id="56a8f-108">Основные понятия, связанные с элементом управления <xref:System.Windows.Forms.TableLayoutPanel>, который позволяет создавать макет со строками и столбцами.</span><span class="sxs-lookup"><span data-stu-id="56a8f-108">Introduces the general concepts of the <xref:System.Windows.Forms.TableLayoutPanel> control, which allows you to create a layout with rows and columns.</span></span>  
  
 [<span data-ttu-id="56a8f-109">Советы по использованию элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="56a8f-109">Best Practices for the TableLayoutPanel Control</span></span>](best-practices-for-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="56a8f-110">Описаны рекомендации, помогающие наиболее эффективно использовать возможности макета элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="56a8f-110">Outlines recommendations to help you get the most out of the layout features of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="56a8f-111">Автоматическое изменение размеров элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="56a8f-111">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)  
 <span data-ttu-id="56a8f-112">Объясняются способы поддержки элементом управления <xref:System.Windows.Forms.TableLayoutPanel> автоматического изменения размеров.</span><span class="sxs-lookup"><span data-stu-id="56a8f-112">Explains the ways in which the <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior.</span></span>  
  
 [<span data-ttu-id="56a8f-113">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="56a8f-113">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 <span data-ttu-id="56a8f-114">Показано, как осуществляется привязка и закрепление дочерних элементов управления в элементе управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="56a8f-114">Shows how to anchor and dock child controls in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 [<span data-ttu-id="56a8f-115">Практическое руководство. Разработка макета формы Windows, с учетом будущей локализации</span><span class="sxs-lookup"><span data-stu-id="56a8f-115">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 <span data-ttu-id="56a8f-116">Демонстрирует использование элемента управления <xref:System.Windows.Forms.TableLayoutPanel> для создания формы, оптимизированной для локализации.</span><span class="sxs-lookup"><span data-stu-id="56a8f-116">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to localization.</span></span>  
  
 [<span data-ttu-id="56a8f-117">Практическое руководство. Создание переменного размера Windows формы для ввода данных</span><span class="sxs-lookup"><span data-stu-id="56a8f-117">How to: Create a Resizable Windows Form for Data Entry</span></span>](how-to-create-a-resizable-windows-form-for-data-entry.md)  
 <span data-ttu-id="56a8f-118">Демонстрирует использование элемента управления <xref:System.Windows.Forms.TableLayoutPanel> для создания формы, оптимизированной для изменения размеров.</span><span class="sxs-lookup"><span data-stu-id="56a8f-118">Demonstrates using a <xref:System.Windows.Forms.TableLayoutPanel> control to build a form that responds well to resizing.</span></span>  
  
1. [<span data-ttu-id="56a8f-119">Практическое руководство. Выравнивание и Растягивание элемента управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="56a8f-119">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="56a8f-120">Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="56a8f-120">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
3. [<span data-ttu-id="56a8f-121">Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="56a8f-121">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="56a8f-122">Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="56a8f-122">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
  
## <a name="reference"></a><span data-ttu-id="56a8f-123">Ссылка</span><span class="sxs-lookup"><span data-stu-id="56a8f-123">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="56a8f-124">Справочная документация по элементу управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="56a8f-124">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.TableLayoutSettings>  
 <span data-ttu-id="56a8f-125">Содержит справочную документацию по типу <xref:System.Windows.Forms.TableLayoutSettings>.</span><span class="sxs-lookup"><span data-stu-id="56a8f-125">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutSettings> type.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="56a8f-126">Справочная документация по элементу управления <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="56a8f-126">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="56a8f-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="56a8f-127">Related Sections</span></span>  
 [<span data-ttu-id="56a8f-128">Локализация</span><span class="sxs-lookup"><span data-stu-id="56a8f-128">Localization</span></span>](../../../standard/globalization-localization/localization.md)  
 <span data-ttu-id="56a8f-129">Обзор разделов, связанных с локализацией.</span><span class="sxs-lookup"><span data-stu-id="56a8f-129">Provides an overview of topics relating to localization.</span></span>  
  
 <span data-ttu-id="56a8f-130">Также см. в разделе [локализация приложений](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/z68135h5(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="56a8f-130">Also see [Localizing Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/z68135h5(v=vs.120)).</span></span>
