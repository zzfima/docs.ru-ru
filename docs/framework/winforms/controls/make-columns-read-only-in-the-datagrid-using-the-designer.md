---
title: Практическое руководство. Предоставления доступа только для чтения к столбцам элемента управления DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 5d9c978f69b2dcfd91c1af6e80391852ed69da12
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466852"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Предоставления доступа только для чтения к столбцам элемента управления DataGridView в формах Windows Forms с помощью конструктора
По умолчанию, пользователи могут изменять текст и числовые данные, отображаемые в формах Windows <xref:System.Windows.Forms.DataGridView> элемента управления. Если вы хотите отображать данные, не предназначенные для редактирования, убедитесь в столбцы, содержащие данные только для чтения. Сведения о том, как сделать элемент управления доступным только для чтения, см. в разделе [как: Предотвращение добавления и удаления строк в Windows Forms DataGridView элемента управления с помощью конструктора](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).  
  
 Следующая процедура требуется **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-make-a-column-read-only-by-using-the-designer"></a>Чтобы сделать столбец только для чтения с помощью конструктора  
  
1.  Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу <xref:System.Windows.Forms.DataGridView> управления, а затем выберите **Правка столбцов**.  
  
2.  Выберите столбец из **выбранные столбцы** списка.  
  
3.  В **свойства столбца** сетки, задайте <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> свойства `true`.  
  
    > [!NOTE]
    >  Вы также можете столбец только для чтения при добавлении, выбрав **только для чтения** флажок в **добавить столбец** диалоговое окно.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 [Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 [Практическое: Создание проекта приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
