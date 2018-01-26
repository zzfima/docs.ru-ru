---
title: "Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fdb57cf2134ee4f221a26db61cfdcc48dc92548
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
Windows Forms <xref:System.Windows.Forms.DataGridView> элемент управления должен содержать столбцы для отображения данных. Если вы планируете вручную заполнить элемент управления, необходимо добавить столбцы самостоятельно. Кроме того можно привязать элемент управления к источнику данных, который создает и заполняет столбцы автоматически. Если источник данных содержит больше столбцов, чем требуется отобразить, можно удалить ненужные столбцы.  
  
 Следующие процедуры требуют **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-a-column-using-the-designer"></a>Чтобы добавить столбец с помощью конструктора  
  
1.  Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу <xref:System.Windows.Forms.DataGridView> управления, а затем выберите **добавить столбец**.  
  
2.  В **добавить столбец** диалогового окна выберите **с привязкой к данным столбца** и выберите столбец из источника данных или выберите **несвязанного столбца** параметр и для определения столбца с помощью соответствующих полях.  
  
3.  Нажмите кнопку **добавить** кнопку для добавления столбца, который отображается в конструкторе, если существующие столбцы не заполняет область отображения элемента управления.  
  
    > [!NOTE]
    >  Можно изменить свойства столбца в **Правка столбцов** диалоговое окно можно открыть из смарт-тега элемента управления.  
  
### <a name="to-remove-a-column-using-the-designer"></a>Чтобы удалить столбец, с помощью конструктора  
  
1.  Выберите **Правка столбцов** смарт-теге элемента управления.  
  
2.  Выберите столбец из **выбранные столбцы** списка.  
  
3.  Нажмите кнопку **удалить** кнопку, чтобы удалить столбец, чего он исчезнет из конструктора.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 [Как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
