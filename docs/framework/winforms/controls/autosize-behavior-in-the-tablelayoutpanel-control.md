---
title: Автоматическое изменение размеров элемента управления TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
ms.openlocfilehash: 466edeee5f45ec72ef265ef4855049c7852641b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164974"
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a><span data-ttu-id="4d689-102">Автоматическое изменение размеров элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4d689-102">AutoSize Behavior in the TableLayoutPanel Control</span></span>
## <a name="distinct-autosize-behaviors"></a><span data-ttu-id="4d689-103">Поведение различных AutoSize</span><span class="sxs-lookup"><span data-stu-id="4d689-103">Distinct AutoSize Behaviors</span></span>  
 <span data-ttu-id="4d689-104"><xref:System.Windows.Forms.TableLayoutPanel> Элемент управления поддерживает автоматическое изменение размеров одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="4d689-104">The <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior in the following ways:</span></span>  
  
-   <span data-ttu-id="4d689-105">Через <xref:System.Windows.Forms.Control.AutoSize%2A> свойство;</span><span class="sxs-lookup"><span data-stu-id="4d689-105">Through the <xref:System.Windows.Forms.Control.AutoSize%2A> property;</span></span>  
  
-   <span data-ttu-id="4d689-106">Через <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> свойство <xref:System.Windows.Forms.TableLayoutPanel> стили столбцов и строк элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4d689-106">Through the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property on the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a><span data-ttu-id="4d689-107">Свойство AutoSize со стилями столбцов и строк</span><span class="sxs-lookup"><span data-stu-id="4d689-107">The AutoSize Property with Row and Column Styles</span></span>  
 <span data-ttu-id="4d689-108">В следующей таблице описаны взаимодействие между <xref:System.Windows.Forms.Control.AutoSize%2A> свойство и <xref:System.Windows.Forms.TableLayoutPanel> стили столбцов и строк элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4d689-108">The following table describes the interaction between the <xref:System.Windows.Forms.Control.AutoSize%2A> property and the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
|<span data-ttu-id="4d689-109">Параметр AutoSize</span><span class="sxs-lookup"><span data-stu-id="4d689-109">AutoSize setting</span></span>|<span data-ttu-id="4d689-110">Взаимодействие со стилем</span><span class="sxs-lookup"><span data-stu-id="4d689-110">Style interaction</span></span>|  
|----------------------|-----------------------|  
|`false`|<span data-ttu-id="4d689-111"><xref:System.Windows.Forms.TableLayoutPanel> Управления выполняется слева направо и выделяет место для столбца или строки или в следующем порядке.</span><span class="sxs-lookup"><span data-stu-id="4d689-111">The <xref:System.Windows.Forms.TableLayoutPanel> control proceeds from left to right, and allocates space for the column or row or in the following order.</span></span><br /><br /> <span data-ttu-id="4d689-112">1.  Если <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> свойству <xref:System.Windows.Forms.SizeType.Absolute>, заданные в точках <xref:System.Windows.Forms.ColumnStyle.Width%2A> или <xref:System.Windows.Forms.RowStyle.Height%2A> выделяется.</span><span class="sxs-lookup"><span data-stu-id="4d689-112">1.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.Absolute>, the number of pixels specified by <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> is allocated.</span></span><br /><span data-ttu-id="4d689-113">2.  Если <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> свойству <xref:System.Windows.Forms.SizeType.AutoSize>, возвращенный дочернего элемента управления в точках <xref:System.Windows.Forms.Control.GetPreferredSize%2A> метод выделяется.</span><span class="sxs-lookup"><span data-stu-id="4d689-113">2.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.AutoSize>, the number of pixels returned by the child control’s <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method is allocated.</span></span><br /><span data-ttu-id="4d689-114">3.  После ввода всех <xref:System.Windows.Forms.SizeType.Absolute> и <xref:System.Windows.Forms.SizeType.AutoSize> столбцов или строк выделяется, все столбцы и строки с <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> присвоено <xref:System.Windows.Forms.SizeType.Percent> используются для пропорционально распределить свободное место</span><span class="sxs-lookup"><span data-stu-id="4d689-114">3.  After space for all <xref:System.Windows.Forms.SizeType.Absolute> and <xref:System.Windows.Forms.SizeType.AutoSize> columns or rows is allocated, any columns or rows with <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> set to <xref:System.Windows.Forms.SizeType.Percent> are used to proportionally allocate the remaining free space</span></span>|  
|`true`|<span data-ttu-id="4d689-115">Аналогичен описанному взаимодействию, за исключением, <xref:System.Windows.Forms.SizeType.Percent> столбцов или строк получить автоматического изменения размеров.</span><span class="sxs-lookup"><span data-stu-id="4d689-115">Similar to the previous interaction, with the exception that <xref:System.Windows.Forms.SizeType.Percent> columns or rows acquire an automatic sizing aspect.</span></span><br /><br /> <span data-ttu-id="4d689-116"><xref:System.Windows.Forms.TableLayoutPanel> Развертывания элемента управления, столбца или строки для создания свободного места, таким образом, нет столбца или строки с <xref:System.Windows.Forms.SizeType.Percent> перекрывалось его содержимое.</span><span class="sxs-lookup"><span data-stu-id="4d689-116">The <xref:System.Windows.Forms.TableLayoutPanel> control expands the column or row to create adequate free space, so that no column or row with <xref:System.Windows.Forms.SizeType.Percent> styling clips its contents.</span></span> <span data-ttu-id="4d689-117"><xref:System.Windows.Forms.TableLayoutPanel> Управления выделяет новое пространство пропорционально в зависимости <xref:System.Windows.Forms.ColumnStyle.Width%2A> или <xref:System.Windows.Forms.RowStyle.Height%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4d689-117">The <xref:System.Windows.Forms.TableLayoutPanel> control allocates the new space proportionally according to the <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d689-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4d689-118">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="4d689-119">Общие сведения об элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="4d689-119">TableLayoutPanel Control Overview</span></span>](tablelayoutpanel-control-overview.md)
