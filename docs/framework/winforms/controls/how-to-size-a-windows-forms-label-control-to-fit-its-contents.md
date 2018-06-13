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
ms.openlocfilehash: e067966b606d77ceb9d11d2784c0d5f73ad332a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533732"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms
Windows Forms <xref:System.Windows.Forms.Label> элемент управления может быть одной или нескольких строк, а также может быть либо фиксированного размера или можно автоматически изменить размер самой надписи. <xref:System.Windows.Forms.Label.AutoSize%2A> Свойства помогает определить размер элементов управления в соответствии с размером надписи, который является особенно полезно, если заголовок изменится во время выполнения.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Чтобы сделать элемент управления label динамически изменить размер в соответствии с содержимым  
  
1.  Задайте его <xref:System.Windows.Forms.Label.AutoSize%2A> свойства `true`.  
  
 Если <xref:System.Windows.Forms.Label.AutoSize%2A> равно `false`, слова, указанные в <xref:System.Windows.Forms.Label.Text%2A> свойство будет переносится на следующую строку, если это возможно, но элемент управления не будет расти.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)  
 [Общие сведения об элементе управления Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Элемент управления Label](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
