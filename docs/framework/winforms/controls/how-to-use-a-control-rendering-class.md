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
ms.openlocfilehash: a0f450ff5f169026007002a0d2907ee35e79b29d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630554"
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="0e4f4-102">Практическое руководство. Использование класса отрисовки элемента управления</span><span class="sxs-lookup"><span data-stu-id="0e4f4-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="0e4f4-103">В этом примере демонстрируется использование <xref:System.Windows.Forms.ComboBoxRenderer> класс для отображения стрелку раскрывающегося списка, поле со списком элемента управления поля.</span><span class="sxs-lookup"><span data-stu-id="0e4f4-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="0e4f4-104">Пример состоит из <xref:System.Windows.Forms.Control.OnPaint%2A> метод простого пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0e4f4-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="0e4f4-105"><xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> Свойство используется для определения, включены ли стили оформления в клиентской области окон приложений.</span><span class="sxs-lookup"><span data-stu-id="0e4f4-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="0e4f4-106">Если визуальные стили включены, то <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> метод визуализирует стрелку раскрывающегося списка с использованием стилей оформления; в противном случае <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> метод визуализирует стрелку раскрывающегося списка в классическом стиле Windows.</span><span class="sxs-lookup"><span data-stu-id="0e4f4-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e4f4-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0e4f4-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0e4f4-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0e4f4-108">Compiling the Code</span></span>  
 <span data-ttu-id="0e4f4-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="0e4f4-109">This example requires:</span></span>  
  
- <span data-ttu-id="0e4f4-110">Пользовательские элементы управления, производные от <xref:System.Windows.Forms.Control> класса.</span><span class="sxs-lookup"><span data-stu-id="0e4f4-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
- <span data-ttu-id="0e4f4-111">Объект <xref:System.Windows.Forms.Form> , на котором размещается пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="0e4f4-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
- <span data-ttu-id="0e4f4-112">Ссылки на <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, и <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="0e4f4-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e4f4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0e4f4-113">See also</span></span>

- [<span data-ttu-id="0e4f4-114">Отрисовка элементов управления с применением визуальных стилей</span><span class="sxs-lookup"><span data-stu-id="0e4f4-114">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
