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
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Практическое руководство. Приведение размера элемента управления Label в соответствие с его содержимым в Windows Forms
Элемент управления Windows Forms <xref:System.Windows.Forms.Label> может быть однострочным или многострочным, а также иметь фиксированный размер или автоматически изменять размер в соответствии с заголовком. Свойство <xref:System.Windows.Forms.Label.AutoSize%2A> помогает задать размер элементов управления в соответствии с большим или меньшим названием, что особенно полезно, если заголовок изменится во время выполнения.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Изменение размера элемента управления Label динамически в соответствии с его содержимым  
  
1. Задайте для свойства <xref:System.Windows.Forms.Label.AutoSize%2A> значение `true`.  
  
 Если <xref:System.Windows.Forms.Label.AutoSize%2A> имеет значение `false`, слова, указанные в свойстве <xref:System.Windows.Forms.Label.Text%2A>, будут переноситься на следующую строку, если это возможно, но элемент управления не будет расти.  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Определение клавиш доступа с помощью элементов управления Label в Windows Forms](how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Общие сведения об элементе управления Label](label-control-overview-windows-forms.md)
- [Элемент управления Label](label-control-windows-forms.md)
