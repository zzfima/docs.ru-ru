---
title: "Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 029eb160545164535b8b5ae058cdc7ad85d69ab9
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора
Иногда необходимо запретить пользователям вставлять новые строки данных или удалять существующие из элемента управления <xref:System.Windows.Forms.DataGridView>. Новые строки добавляются в специальную строку для новых записей в нижней части элемента управления. При отключении функции добавления, строки для новых записей не отображается. Вы может затем сделать элемент управления доступным только для чтения, отключив удаления строк и редактирования ячейки.  
  
 В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-prevent-row-addition-and-deletion"></a>Для предотвращения добавления и удаления строк  
  
-   Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу <xref:System.Windows.Forms.DataGridView> управления, а затем снимите **разрешить добавление** и **Разрешить удаление** флажки.  
  
    > [!NOTE]
    >  Чтобы сделать элемент управления доступным только для чтения, снимите **Разрешить изменение** также флажок.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 [Как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
