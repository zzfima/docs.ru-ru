---
title: Изменение размера элемента управления Label в соответствии с его содержимым
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 6a563693feaa5074f5d13f0b82cc4d0305a79c23
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743784"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="38593-102">Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38593-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="38593-103">Элемент управления Windows Forms <xref:System.Windows.Forms.Label> может быть однострочным или многострочным, а также иметь фиксированный размер или автоматически изменять размер в соответствии с заголовком.</span><span class="sxs-lookup"><span data-stu-id="38593-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="38593-104">Свойство <xref:System.Windows.Forms.Label.AutoSize%2A> помогает задать размер элементов управления в соответствии с большим или меньшим названием, что особенно полезно, если заголовок изменится во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="38593-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="38593-105">Изменение размера элемента управления Label динамически в соответствии с его содержимым</span><span class="sxs-lookup"><span data-stu-id="38593-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1. <span data-ttu-id="38593-106">Задайте для свойства <xref:System.Windows.Forms.Label.AutoSize%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="38593-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="38593-107">Если <xref:System.Windows.Forms.Label.AutoSize%2A> имеет значение `false`, слова, указанные в свойстве <xref:System.Windows.Forms.Label.Text%2A>, будут переноситься на следующую строку, если это возможно, но элемент управления не будет расти.</span><span class="sxs-lookup"><span data-stu-id="38593-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38593-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="38593-108">See also</span></span>

- [<span data-ttu-id="38593-109">Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38593-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="38593-110">Общие сведения об элементе управления Label</span><span class="sxs-lookup"><span data-stu-id="38593-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="38593-111">Элемент управления Label</span><span class="sxs-lookup"><span data-stu-id="38593-111">Label Control</span></span>](label-control-windows-forms.md)
