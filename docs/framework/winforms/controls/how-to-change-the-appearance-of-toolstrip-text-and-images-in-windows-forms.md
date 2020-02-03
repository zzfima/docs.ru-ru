---
title: Как изменить внешний вид текста и изображений ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
ms.openlocfilehash: 7816e138e44554683c201895ece1f886ace8bfa6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746597"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a>Практическое руководство. Изменение внешнего вида текста и изображений элемента управления ToolStrip в Windows Forms
Можно управлять отображением текста и изображений на <xref:System.Windows.Forms.ToolStripItem> и их согласованности друг с другом и <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a>Определение того, что отображается в элементе ToolStripItem  
  
- Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> нужное значение. Возможные варианты: `Image`, `ImageAndText`, `None`и `Text`. Значение по умолчанию — `ImageAndText`.  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a>Выровняйте текст по ToolStripItem  
  
- Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> нужное значение. Возможности — это любое сочетание верхнего, среднего и нижнего угла по левому краю, центру и правому. Значение по умолчанию — `MiddleCenter`.  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a>Выровняйте изображение по ToolStripItem  
  
- Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> нужное значение. Возможности — это любое сочетание верхнего, среднего и нижнего угла по левому краю, центру и правому. Значение по умолчанию — `MiddleLeft`.  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a>Определение способа отображения текста и изображений по отношению друг к другу  
  
- Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> нужное значение. Возможные значения — `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage` и `TextBeforeImage`. Значение по умолчанию — `ImageBeforeText`.  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ToolStrip>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Архитектура элемента управления ToolStrip](toolstrip-control-architecture.md)
- [Технологии, положенные в основу работы элемента управления ToolStrip](toolstrip-technology-summary.md)
