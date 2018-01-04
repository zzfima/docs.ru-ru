---
title: "Практическое руководство. Перемещение объектов ToolStripMenuItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfc1cb718b3738ac93b284b0b438b08d1e721349
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-move-toolstripmenuitems"></a>Практическое руководство. Перемещение объектов ToolStripMenuItem
Во время разработки, можно переместить целиком меню верхнего уровня с пунктами меню в другое место на <xref:System.Windows.Forms.MenuStrip>. Также можно перемещать отдельные элементы между меню верхнего уровня или изменять положение элементов в меню.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a>Чтобы переместить меню верхнего уровня и пунктов меню в другое расположение верхнего уровня  
  
1.  Щелкните, удерживая нажатой левую кнопку мыши в меню, которое требуется переместить.  
  
2.  Перетащите курсор в меню верхнего уровня, который находится перед новым предполагаемым расположением и отпустите кнопку мыши.  
  
     Выбранное меню перемещается справа от курсора.  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a>Чтобы переместить в расположение раскрывающегося меню верхнего уровня и пунктов меню  
  
1.  Щелкните меню, которое требуется переместить и нажмите клавиши CTRL + X или щелкните меню правой кнопкой мыши и выберите **Вырезать** в контекстном меню.  
  
2.  В целевом меню верхнего уровня щелкните элемент меню над новым предполагаемым расположением и нажмите клавиши CTRL + V или щелкните правой кнопкой мыши пункт меню над новым предполагаемым расположением и выберите **вставить** в контекстном меню.  
  
     Вырезанное меню вставляется после выбранного пункта меню.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a>Чтобы переместить элемент меню в пределах меню, используя редактор коллекции элементов  
  
1.  Щелкните правой кнопкой мыши меню, содержащее пункт меню, который требуется переместить.  
  
2.  В контекстном меню выберите **редактировать элементы раскрывающегося меню**.  
  
3.  В **редактор коллекции элементов**, щелкните элемент меню, которую требуется переместить.  
  
4.  Нажмите клавиши со стрелками вверх и вниз для перемещения элемента меню в меню.  
  
5.  Нажмите кнопку **ОК**.  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a>Чтобы переместить элемент меню в меню с помощью клавиатуры  
  
1.  Нажмите и удерживайте клавишу ALT.  
  
2.  Щелкните и удерживайте левую кнопку мыши на пункт меню, который требуется переместить.  
  
3.  Перетащите элемент меню на новое место и отпустите кнопку мыши.  
  
### <a name="to-move-a-menu-item-to-another-menu"></a>Чтобы переместить элемент меню в другое меню  
  
1.  Щелкните элемент меню, который требуется переместить и нажмите клавиши CTRL + X или щелкните правой кнопкой мыши пункт меню и выберите **Вырезать** в контекстном меню.  
  
2.  Щелкните меню, которое будет содержать вырезанный элемент меню.  
  
3.  Щелкните элемент меню, который находится перед новым предполагаемым расположением и нажмите клавиши CTRL + V или щелкните правой кнопкой мыши пункт меню, который находится перед новым предполагаемым расположением и выберите **вставить** в контекстном меню.  
  
     Вырезанный элемент меню вставляется после выбранного пункта меню.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
