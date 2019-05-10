---
title: Практическое руководство. Создание переключателей в элементах управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 21da5564bfeec01d448c23d3e734bdd16fc1566b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666434"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>Практическое руководство. Создание переключателей в элементах управления ToolStrip
Когда пользователь щелкает кнопку-переключатель, он отображается углубленным и остается таковым, пока пользователь не щелкнет кнопку еще раз.  
  
### <a name="to-create-a-toggling-toolstripbutton"></a>Для создания переключателя ToolStripButton  
  
- Используйте код, как в следующем примере кода. Этот код предполагает, что форма содержит <xref:System.Windows.Forms.ToolStrip> элемента управления и что его <xref:System.Windows.Forms.ToolStrip.Items%2A> коллекция содержит <xref:System.Windows.Forms.ToolStripButton> вызывается `toolStripButton1`. Также предполагается, что у вас есть обработчик событий, который называется `toolStripButton1_CheckedChanged`.  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolStripButton>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
