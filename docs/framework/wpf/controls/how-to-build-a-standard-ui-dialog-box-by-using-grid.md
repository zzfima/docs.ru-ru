---
title: Практическое руководство. Создание стандартного диалогового окна пользовательского интерфейса с помощью сетки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 0ade908e92e552017acb9ba242ccba2c28c3c995
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59149530"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="0fc86-102">Практическое руководство. Создание стандартного диалогового окна пользовательского интерфейса с помощью сетки</span><span class="sxs-lookup"><span data-stu-id="0fc86-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="0fc86-103">В этом примере показано, как создать стандартную [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] диалоговое окно с помощью <xref:System.Windows.Controls.Grid> элемент.</span><span class="sxs-lookup"><span data-stu-id="0fc86-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fc86-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0fc86-104">Example</span></span>  
 <span data-ttu-id="0fc86-105">В следующем примере создается диалоговое окно, похожее **запуска** диалогового окна в [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] операционной системы.</span><span class="sxs-lookup"><span data-stu-id="0fc86-105">The following example creates a dialog box like the **Run** dialog box in the [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="0fc86-106">В примере создается <xref:System.Windows.Controls.Grid> и использует <xref:System.Windows.Controls.ColumnDefinition> и <xref:System.Windows.Controls.RowDefinition> классам определять пятью столбцами и четырьмя строками.</span><span class="sxs-lookup"><span data-stu-id="0fc86-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="0fc86-107">Затем добавляет и помещает <xref:System.Windows.Controls.Image>, `RunIcon.png`, чтобы представить образ, который находится в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="0fc86-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="0fc86-108">Изображение размещается в первом столбце и строке <xref:System.Windows.Controls.Grid> (в левом верхнем углу).</span><span class="sxs-lookup"><span data-stu-id="0fc86-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="0fc86-109">Затем в примере добавляется <xref:System.Windows.Controls.TextBlock> элемент в первый столбец, который охватывает оставшиеся столбцы первой строки.</span><span class="sxs-lookup"><span data-stu-id="0fc86-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="0fc86-110">Он добавляет другой <xref:System.Windows.Controls.TextBlock> элемент второй строки в первом столбце, для представления **откройте** текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="0fc86-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="0fc86-111">Объект <xref:System.Windows.Controls.TextBlock> с помощью которой представляет область ввода данных.</span><span class="sxs-lookup"><span data-stu-id="0fc86-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="0fc86-112">Наконец, в примере добавляется три <xref:System.Windows.Controls.Button> элементов в последнюю строку, которые представляют **ОК**, **отменить**, и **Обзор** события.</span><span class="sxs-lookup"><span data-stu-id="0fc86-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0fc86-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0fc86-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="0fc86-114">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="0fc86-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="0fc86-115">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="0fc86-115">How-to Topics</span></span>](grid-how-to-topics.md)
