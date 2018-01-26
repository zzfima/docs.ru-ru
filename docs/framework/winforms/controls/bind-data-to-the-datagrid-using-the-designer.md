---
title: "Практическое руководство. Привязка данных к элементу управления DataGridView в форме Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a3c7422bc83c7ee1f09bac05333799708cd2f2f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Привязка данных к элементу управления DataGridView в форме Windows Forms с помощью конструктора
Конструктор можно использовать для подключения <xref:System.Windows.Forms.DataGridView> управления к источникам данных разных видов, включая базы данных, бизнес-объектов или веб-служб. При привязке элемента управления к источнику данных с помощью конструктора, элемент управления автоматически привязывается к <xref:System.Windows.Forms.BindingSource> компонент, представляющий источник данных. Кроме того, в элементе управления автоматически создаются столбцы для сопоставления данных о схеме, предоставляемых источником данных.  
  
 После этого созданные столбцы можно будет изменить с учетом ваших потребностей. Например, можно удалить или скрыть столбцы, которые вас не интересуют, изменить порядок или типы столбцов. Дополнительные сведения об изменении столбцов см. в разделах, перечисленных в разделе "См. также".  
  
 Можно также привязать несколько <xref:System.Windows.Forms.DataGridView> элементов управления со связанными таблицами, создание иерархического отношения. В данной конфигурации один элемент управления отображает родительскую таблицу, а другой — только те строки из дочерней таблицы, которые связаны с текущей строкой в родительской таблице. Дополнительные сведения см. в разделе [Практическое руководство. Отображение связанных данные в приложении Windows Forms](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
 Следующая процедура требуется **приложение Windows** проект с формой, содержащей <xref:System.Windows.Forms.DataGridView> управления или двух элементов управления для связи «основной/подробности». Сведения о создании такого проекта см. в разделах [Практическое руководство. Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-bind-the-control-to-a-data-source"></a>Привязка элемента управления к источнику данных  
  
1.  Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
2.  Щелкните стрелку раскрывающегося списка рядом с параметром **Выбор источника данных**.  
  
3.  Если у проекта еще нет источника данных, нажмите **Добавить источник данных проекта** и следуйте указаниям мастера.  
  
     Дополнительные сведения см. в разделе [Мастер настройки источника данных](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f). Новый источник данных появится в раскрывающемся окне **Выбор источника данных**. Если источник данных содержит только один элемент, например только одну таблицу баз данных, элемент управления будет автоматически привязан к этому элементу. В противном случае перейдите к следующему этапу.  
  
4.  Разверните узлы **Другие источники данных** и **Источники данных проекта**, если они еще не развернуты, и выберите источник данных, к которому нужно привязать элемент управления.  
  
5.  Если источник данных содержит несколько элементов, например, если вы создали <xref:System.Data.DataSet?displayProperty=nameWithType> , содержащего несколько таблиц, разверните источник данных и затем выберите конкретный элемент для привязки.  
  
6.  Для создания отношения главного и подчиненного представлений в **Выбор источника данных** раскрывающемся окне секунды <xref:System.Windows.Forms.DataGridView> управления, разверните <xref:System.Windows.Forms.BindingSource> создан для родительской таблицы, а затем выберите соответствующую дочернюю таблицу из списка отобразить.  
  
    > [!NOTE]
    >  Если в вашем проекте уже есть источник данных, форму данных можно также создать в окне **Источники данных**. Дополнительные сведения см. в разделе [Окно источников данных](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 [Практическое руководство. Подключение к данным в базе данных](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)  
 [Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 [Практическое руководство. Изменение типа столбца DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 [Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 [Практическое руководство. Скрытие столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 [Практическое руководство. Предоставления доступа только для чтения к столбцам элемента управления DataGridView в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 [Как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Окно "Источники данных"](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)  
 [Практическое руководство. Отображение связанных данные в приложении Windows Forms](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)
