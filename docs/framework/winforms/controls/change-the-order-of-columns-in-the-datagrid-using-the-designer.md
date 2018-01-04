---
title: "Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c36bfdd69cb4a3e7827302a7bde5139675a30429
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
При привязке Windows Forms <xref:System.Windows.Forms.DataGridView> элемента управления к источнику данных, порядок отображения столбцов, автоматически созданный определяется источником данных. Если вас не устраивает этот порядок можно изменить порядок столбцов, с помощью конструктора. Можно также добавить к элементу управления несвязанные столбцы и изменить порядок их отображения. Сведения о способах изменения порядка столбцов программным путем см. в разделе [как: изменить порядок столбцов в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).  
  
 В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)  
  
### <a name="to-change-the-column-order-using-the-designer"></a>Чтобы изменить порядок столбцов, с помощью конструктора  
  
1.  Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу <xref:System.Windows.Forms.DataGridView> управления, а затем выберите **Правка столбцов**.  
  
2.  Выберите столбец из **выбранные столбцы** списка.  
  
3.  Щелкните стрелку вверх или вниз справа от **выбранные столбцы** список до выбранного столбца в нужное место.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 [Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [Как: Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
