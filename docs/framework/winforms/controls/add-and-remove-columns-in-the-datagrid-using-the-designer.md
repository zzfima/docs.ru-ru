---
title: Как выполнить  Добавлять и удалять столбцы в элементе управления DataGridView формы Windows с помощью конструктора
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 01ae8987f7a92abf79a758e82ed0ac863fad57ce
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332693"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Как выполнить  Добавлять и удалять столбцы в элементе управления DataGridView формы Windows с помощью конструктора
Windows Forms <xref:System.Windows.Forms.DataGridView> элемент управления должен содержать столбцы для отображения данных. Если вы планируете вручную заполнение элемента управления, необходимо добавить столбцы самостоятельно. Кроме того можно привязать элемент управления к источнику данных, который создает и заполняет столбцы автоматически. Если источник данных содержит больше столбцов, чем требуется отобразить, можно удалить ненужные столбцы.  
  
 Следующие процедуры требуют **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создайте проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-a-column-using-the-designer"></a>Чтобы добавить столбец с помощью конструктора  
  
1.  Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу <xref:System.Windows.Forms.DataGridView> управления, а затем выберите **добавить столбец**.  
  
2.  В **добавить столбец** диалоговое окно, выберите **с привязкой к данным столбца** параметр и выберите столбец из источника данных или выберите **несвязанного столбца** параметр и для определения столбца с помощью соответствующих полях.  
  
3.  Нажмите кнопку **добавить** кнопка для добавления столбца, который отображается в конструкторе, если существующие столбцы не заполняет область отображения элемента управления.  
  
    > [!NOTE]
    >  Можно изменить свойства столбца в **Правка столбцов** диалоговое окно, к которому можно получить из смарт-тега элемента управления.  
  
### <a name="to-remove-a-column-using-the-designer"></a>Чтобы удалить столбец, с помощью конструктора  
  
1.  Выберите **Правка столбцов** смарт-теге элемента управления.  
  
2.  Выберите столбец из **выбранные столбцы** списка.  
  
3.  Нажмите кнопку **удалить** кнопку, чтобы удалить столбец, чего он исчезнет из конструктора.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.DataGridView>
- [Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).
- [Практическое руководство. Добавление элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
