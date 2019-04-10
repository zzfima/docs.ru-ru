---
title: Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: 02db78b07930676235e55e535fb24f6ff618d823
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339025"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="fbc71-102">Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="fbc71-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="fbc71-103">Элементы управления в <xref:System.Windows.Forms.TableLayoutPanel> элемент управления может охватывать соседних строк и столбцов.</span><span class="sxs-lookup"><span data-stu-id="fbc71-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fbc71-104">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="fbc71-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fbc71-105">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="fbc71-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fbc71-106">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="fbc71-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-span-columns-and-rows"></a><span data-ttu-id="fbc71-107">Чтобы объединить столбцы и строки</span><span class="sxs-lookup"><span data-stu-id="fbc71-107">To span columns and rows</span></span>  
  
1. <span data-ttu-id="fbc71-108">Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.</span><span class="sxs-lookup"><span data-stu-id="fbc71-108">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
2. <span data-ttu-id="fbc71-109">Перетащите <xref:System.Windows.Forms.Button> управления из **элементов** в левый верхний угол объекта <xref:System.Windows.Forms.TableLayoutPanel> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fbc71-109">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3. <span data-ttu-id="fbc71-110">Задайте <xref:System.Windows.Forms.Button> элемента управления **ColumnSpan** свойства **2**.</span><span class="sxs-lookup"><span data-stu-id="fbc71-110">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="fbc71-111">Обратите внимание, что <xref:System.Windows.Forms.Button> управления охватывает первый и второй столбцы.</span><span class="sxs-lookup"><span data-stu-id="fbc71-111">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>  
  
4. <span data-ttu-id="fbc71-112">Задайте <xref:System.Windows.Forms.Button> элемента управления **RowSpan** свойства **2**.</span><span class="sxs-lookup"><span data-stu-id="fbc71-112">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="fbc71-113">Обратите внимание, что <xref:System.Windows.Forms.Button> управления охватывает первую и вторую строку.</span><span class="sxs-lookup"><span data-stu-id="fbc71-113">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>  
  
5. <span data-ttu-id="fbc71-114">Задайте <xref:System.Windows.Forms.Button> элемента управления **ColumnSpan** свойства **1**.</span><span class="sxs-lookup"><span data-stu-id="fbc71-114">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="fbc71-115">Обратите внимание, что <xref:System.Windows.Forms.Button> управления перемещается в первый столбец, но охватывает первую и вторую строку.</span><span class="sxs-lookup"><span data-stu-id="fbc71-115">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc71-116">См. также</span><span class="sxs-lookup"><span data-stu-id="fbc71-116">See also</span></span>

- [<span data-ttu-id="fbc71-117">Элемент управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="fbc71-117">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
