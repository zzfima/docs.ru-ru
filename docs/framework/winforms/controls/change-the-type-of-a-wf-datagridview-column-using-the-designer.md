---
title: Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: b5d395575ac486307625fbdf2f236b6a588cc3ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527019"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора
Иногда требуется изменить тип столбца, который уже был добавлен в форму Windows Forms <xref:System.Windows.Forms.DataGridView> элемента управления. Например может потребоваться изменить типы некоторых столбцов, которые создаются автоматически при привязке элемента управления к источнику данных. Это полезно в том случае, если таблицы, которые отображены столбцы, содержащие внешние ключи для строк в связанной таблице. В этом случае может потребоваться заменить столбцы с текстовыми полями, в которых отображаются эти внешние ключи, со столбцами поле со списком, которые отображаются более понятные значения из связанной таблицы.  
  
 В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a>Чтобы изменить тип столбца с помощью конструктора  
  
1.  Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу <xref:System.Windows.Forms.DataGridView> управления, а затем выберите **Правка столбцов**.  
  
2.  Выберите столбец из **выбранные столбцы** списка.  
  
3.  В **свойства столбца** сетка, `ColumnType` свойство в тип нового столбца.  
  
    > [!NOTE]
    >  `ColumnType` Свойство является свойством только во время разработки, которое указывает класс, представляющий тип столбца. Это не фактическое свойство, определенное в классе столбца.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [Как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
