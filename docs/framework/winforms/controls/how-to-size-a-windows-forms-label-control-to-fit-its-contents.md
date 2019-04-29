---
title: Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 110aab0c0826bb4b06e22158afd6af37b5406be4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971201"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a><span data-ttu-id="71c7f-102">Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71c7f-102">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>
<span data-ttu-id="71c7f-103">Windows Forms <xref:System.Windows.Forms.Label> элемент управления может быть одной или несколькими строками, которая может быть либо фиксированного размера или может автоматически изменять свой размер надписи.</span><span class="sxs-lookup"><span data-stu-id="71c7f-103">The Windows Forms <xref:System.Windows.Forms.Label> control can be single-line or multi-line, and it can be either fixed in size or can automatically resize itself to accommodate its caption.</span></span> <span data-ttu-id="71c7f-104"><xref:System.Windows.Forms.Label.AutoSize%2A> Свойство помогает определить размер элементов управления в соответствии с размером надписи, который является особенно удобно в том случае, если заголовок будет изменяться во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="71c7f-104">The <xref:System.Windows.Forms.Label.AutoSize%2A> property helps you size the controls to fit larger or smaller captions, which is particularly useful if the caption will change at run time.</span></span>  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a><span data-ttu-id="71c7f-105">Чтобы сделать элемент управления label динамически изменить размер, чтобы вместить его содержимое</span><span class="sxs-lookup"><span data-stu-id="71c7f-105">To make a label control resize dynamically to fit its contents</span></span>  
  
1. <span data-ttu-id="71c7f-106">Задайте его <xref:System.Windows.Forms.Label.AutoSize%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="71c7f-106">Set its <xref:System.Windows.Forms.Label.AutoSize%2A> property to `true`.</span></span>  
  
 <span data-ttu-id="71c7f-107">Если <xref:System.Windows.Forms.Label.AutoSize%2A> присваивается `false`, слова, указанные в <xref:System.Windows.Forms.Label.Text%2A> свойство будет переносится на следующую строку, если это возможно, но элемент управления не будет увеличиваться.</span><span class="sxs-lookup"><span data-stu-id="71c7f-107">If <xref:System.Windows.Forms.Label.AutoSize%2A> is set to `false`, the words specified in the <xref:System.Windows.Forms.Label.Text%2A> property will wrap to the next line if possible, but the control will not grow.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c7f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="71c7f-108">See also</span></span>

- [<span data-ttu-id="71c7f-109">Практическое руководство. Создание ключей доступа с помощью элементов управления Label в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="71c7f-109">How to: Create Access Keys with Windows Forms Label Controls</span></span>](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [<span data-ttu-id="71c7f-110">Общие сведения об элементе управления Label</span><span class="sxs-lookup"><span data-stu-id="71c7f-110">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="71c7f-111">Элемент управления Label</span><span class="sxs-lookup"><span data-stu-id="71c7f-111">Label Control</span></span>](label-control-windows-forms.md)
