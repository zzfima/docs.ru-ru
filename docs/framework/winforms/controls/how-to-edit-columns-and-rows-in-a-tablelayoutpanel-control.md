---
title: "Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: net.ComponentModel.StyleCollectionEditor
helpviewer_keywords:
- columns [Windows Forms], editing
- TableLayoutPanel control [Windows Forms], editing
- rows [Windows Forms], editing
ms.assetid: c367ed43-40dc-49eb-9e0f-ba70e83dfec0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 84dbcfcbad30f9ef08548874c5e68ed658aa0914
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control"></a>Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel
Можно использовать редактор коллекций элемента <xref:System.Windows.Forms.TableLayoutPanel> элемент управления с именем **стили столбцов и строк** диалоговое окно для редактирования строк и столбцов элементов управления.  
  
> [!NOTE]
>  Если требуется, чтобы элемент управления охватывал несколько строк или столбцов, задайте `RowSpan` и `ColumnSpan` свойства элемента управления. Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Если вы хотите выравнивание элементов управления в ячейке или элемент управления, чтобы растянуть в ячейке, используйте элемент управления <xref:System.Windows.Forms.Control.Anchor%2A> свойство. Для получения дополнительной информации см. [Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md).  
>   
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-edit-rows-and-columns"></a>Для редактирования строк и столбцов  
  
1.  Перетащите <xref:System.Windows.Forms.TableLayoutPanel> управления из **элементов** на форму.  
  
2.  Нажмите кнопку <xref:System.Windows.Forms.TableLayoutPanel> глиф смарт-тега элемента управления (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) и выберите **изменить строки и столбцы** Открытие  **Стили столбцов и строк** диалоговое окно. Вы можете также щелкните правой кнопкой мыши <xref:System.Windows.Forms.TableLayoutPanel> управления и выберите **изменить строки и столбцы** в контекстном меню.  
  
3.  Чтобы добавить или удалить столбцы, выберите **столбцы** из **тип члена** раскрывающегося списка.  
  
4.  Чтобы добавить или удалить строки, выберите **строк** из **тип члена** раскрывающегося списка.  
  
5.  Нажмите кнопку **добавить** кнопку, чтобы добавить строку или столбец в конец **член** списка.  
  
6.  Нажмите кнопку **вставить** кнопку, чтобы добавить строки или столбца перед выбранного элемента в списке.  
  
7.  При добавлении строки или столбца выберите **тип размера** для новой строки или столбца. Для получения дополнительной информации см. <xref:System.Windows.Forms.SizeType>.  
  
8.  Чтобы удалить строку или столбец, щелкните **удалить** кнопку, чтобы удалить выбранный элемент в **член** списка.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.SizeType>  
 [Элемент управления TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
