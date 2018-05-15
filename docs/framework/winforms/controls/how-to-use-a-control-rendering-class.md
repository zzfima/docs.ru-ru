---
title: Практическое руководство. Использование класса отрисовки элемента управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: e5b82c3317d2d162fbd5a182166a9e0061fd770e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="eccd0-102">Практическое руководство. Использование класса отрисовки элемента управления</span><span class="sxs-lookup"><span data-stu-id="eccd0-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="eccd0-103">В этом примере демонстрируется использование <xref:System.Windows.Forms.ComboBoxRenderer> класса для отображения стрелку раскрывающегося списка поля со списком поле элемента управления.</span><span class="sxs-lookup"><span data-stu-id="eccd0-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="eccd0-104">Пример состоит из <xref:System.Windows.Forms.Control.OnPaint%2A> метод простого пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="eccd0-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="eccd0-105"><xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> Свойство используется для определения, включены ли визуальные стили в клиентской области окна приложения.</span><span class="sxs-lookup"><span data-stu-id="eccd0-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="eccd0-106">Если визуальные стили включены, то <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> метода сделает стрелку раскрывающегося списка с применением визуальных стилей; в противном случае <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> метода сделает стрелку раскрывающегося списка в классическом стиле Windows.</span><span class="sxs-lookup"><span data-stu-id="eccd0-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eccd0-107">Пример</span><span class="sxs-lookup"><span data-stu-id="eccd0-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eccd0-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="eccd0-108">Compiling the Code</span></span>  
 <span data-ttu-id="eccd0-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="eccd0-109">This example requires:</span></span>  
  
-   <span data-ttu-id="eccd0-110">Пользовательский элемент управления на основе <xref:System.Windows.Forms.Control> класса.</span><span class="sxs-lookup"><span data-stu-id="eccd0-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
-   <span data-ttu-id="eccd0-111">Объект <xref:System.Windows.Forms.Form> , на котором размещается пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="eccd0-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
-   <span data-ttu-id="eccd0-112">Ссылки на <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, и <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="eccd0-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eccd0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="eccd0-113">See Also</span></span>  
 [<span data-ttu-id="eccd0-114">Отрисовка элементов управления с применением визуальных стилей</span><span class="sxs-lookup"><span data-stu-id="eccd0-114">Rendering Controls with Visual Styles</span></span>](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
