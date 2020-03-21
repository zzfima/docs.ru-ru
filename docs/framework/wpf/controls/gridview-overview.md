---
title: Общие сведения о GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 98bc7985172cabeab19469af4b4c21e13a6bce73
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181890"
---
# <a name="gridview-overview"></a>Общие сведения о GridView
<xref:System.Windows.Controls.GridView>режим просмотра является одним из режимов <xref:System.Windows.Controls.ListView> представления для управления. Класс <xref:System.Windows.Controls.GridView> и поддерживающие классы позволяют вам и пользователям просматривать коллекции элементов в таблице, которая обычно использует кнопки в качестве интерактивных заголовков столбцов. Эта тема знакомит с классом <xref:System.Windows.Controls.GridView> и описывает его использование.  

<a name="DefiningaListViewthatusesGridViewView"></a>
## <a name="what-is-a-gridview-view"></a>Что такое представление GridView?  
 Режим <xref:System.Windows.Controls.GridView> представления отображает список элементов данных путем привязки полей данных к столбцов и отображения заголовка столбца для идентификации поля. Стиль <xref:System.Windows.Controls.GridView> по умолчанию реализует кнопки в качестве заголовков столбцов. Используя кнопки для заголовков столбцов, можно реализовать важные возможности взаимодействия с пользователем; например, пользователи могут нажать на <xref:System.Windows.Controls.GridView> заголовок столбца для сортировки данных в соответствии с содержанием определенного столбца.  
  
> [!NOTE]
> Элементы управления <xref:System.Windows.Controls.GridView> кнопками, которые используются <xref:System.Windows.Controls.Primitives.ButtonBase>для заголовков столбцов, получены из.  
  
 Следующая иллюстрация <xref:System.Windows.Controls.GridView> показывает <xref:System.Windows.Controls.ListView> представление содержания.  

 ![Скриншот, отображающие представление содержимого ListView GridView.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView>столбцы представлены <xref:System.Windows.Controls.GridViewColumn> объектами, которые могут автоматически размер их содержания. Дополнительно можно явно установить <xref:System.Windows.Controls.GridViewColumn> определенную ширину. Можно изменить размеры столбцов, перетащив границу между заголовками столбцов. Вы также можете динамически добавлять, удалять, заменять и <xref:System.Windows.Controls.GridView>переупорядокивать столбцы, поскольку эта функциональность встроена в. Тем <xref:System.Windows.Controls.GridView> не менее, не может непосредственно обновить данные, которые он отображает.  
  
 В следующем примере показано, как определить данные <xref:System.Windows.Controls.GridView> сотрудника. В этом <xref:System.Windows.Controls.ListView> примере `EmployeeInfoDataSource` определяется <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>как . Определения свойств <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> привязывания `EmployeeInfoDataSource` <xref:System.Windows.Controls.GridViewColumn> содержимого к категориям данных.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 На следующем рисунке показана таблица, которая создается в предыдущем примере. Элемент управления GridView отображает данные с объекта ItemsSource:

 ![Скриншот, на который показан ListView с выходом GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>
## <a name="gridview-layout-and-style"></a>Макет и стиль GridView  
 Ячейки столбца и заголовок <xref:System.Windows.Controls.GridViewColumn> столбца имеют одинаковую ширину. По умолчанию ширина каждого столбца изменяется в соответствии с шириной содержимого. При необходимости можно установить фиксированную ширину столбца.  
  
 Связанные данные отображаются в горизонтальных строках. Например, на предыдущем рисунке фамилия, имя и идентификационный номер каждого сотрудника отображаются в виде набора, поскольку они отображаются в горизонтальной строке.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>
### <a name="defining-and-styling-columns-in-a-gridview"></a>Определение и применение стилей к столбцам в GridView  
 При определении поля данных <xref:System.Windows.Controls.GridViewColumn>для <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>отображения в, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>используйте, или <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> свойства. Свойство <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> имеет приоритет над любым из свойств шаблона.  
  
 Чтобы указать выравнивание содержимого <xref:System.Windows.Controls.GridView>в <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>столбце, определить . Не используйте <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> свойства <xref:System.Windows.Controls.ListView> и свойства для содержимого, <xref:System.Windows.Controls.GridView>отображаемого с помощью .  
  
 Чтобы указать свойства шаблона и стиля <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.GridViewColumn>для <xref:System.Windows.Controls.GridViewColumnHeader> заголовков столбцов, используйте и классы. Дополнительные сведения см. в разделе [Общие сведения о стилях заголовков столбцов GridView и шаблонах](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>
### <a name="adding-visual-elements-to-a-gridview"></a>Добавление визуальных элементов в GridView  
 Чтобы добавить визуальные <xref:System.Windows.Controls.CheckBox> <xref:System.Windows.Controls.Button> элементы, <xref:System.Windows.Controls.GridView> такие как элементы управления, в режим просмотра, используйте шаблоны или стили.  
  
 Если вы четко определяете визуальный элемент как элемент данных, <xref:System.Windows.Controls.GridView>он может отображаться только один раз в . Это ограничение существует, так как элемент может иметь только один родительский элемент и, таким образом, может появляться, только один раз в визуальном дереве.  
  
<a name="StylingRowsinaGridViewView"></a>
### <a name="styling-rows-in-a-gridview"></a>Применение стилей к строкам в GridView  
 Используйте <xref:System.Windows.Controls.GridViewRowPresenter> <xref:System.Windows.Controls.GridViewHeaderRowPresenter> и классы для формата <xref:System.Windows.Controls.GridView>и отображения строк . Например, как стилизовать строки в режиме <xref:System.Windows.Controls.GridView> представления, см. Стиль [строки в ListView, который реализует GridView.](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md)  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Проблемы выравнивания при использовании ItemContainerStyle  
 Чтобы предотвратить проблемы выравнивания между заголовками столбцов и ячейками, не устанавливайте свойство и не укажите шаблон, который влияет на ширину элемента в . <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Например, <xref:System.Windows.FrameworkElement.Margin%2A> не устанавливайте свойство <xref:System.Windows.Controls.ControlTemplate> и <xref:System.Windows.Controls.CheckBox> не <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> укажите, что <xref:System.Windows.Controls.ListView> добавляет к тому, что определено на элементе управления. Вместо этого укажите свойства и шаблоны, которые влияют на ширину столбца непосредственно на классах, определяющих режим <xref:System.Windows.Controls.GridView> представления.  
  
 Например, чтобы <xref:System.Windows.Controls.CheckBox> добавить к <xref:System.Windows.Controls.GridView> строкам в <xref:System.Windows.Controls.CheckBox> режиме просмотра, добавить в <xref:System.Windows.DataTemplate>, а затем установить <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> свойство к этому. <xref:System.Windows.DataTemplate>  
  
<a name="InteractingwithaGridViewControl"></a>
## <a name="user-interactions-with-a-gridview"></a>Взаимодействие пользователя с GridView  
 При использовании <xref:System.Windows.Controls.GridView> приложения пользователи <xref:System.Windows.Controls.GridView>могут взаимодействовать и изменять форматирование. Например, пользователи могут изменить порядок столбцов, изменить размер столбца, выделить элементы в таблице и прокрутить содержимое. Можно также определить обработчик событий, реагирующий на нажатие пользователем кнопки заголовка столбца. Обработчик событий может выполнять такие операции, как <xref:System.Windows.Controls.GridView> сортировка данных, отображаемых в соответствии с содержанием столбца.  
  
 В следующем списке более подробно рассматриваются возможности использования <xref:System.Windows.Controls.GridView> для взаимодействия с пользователем:  
  
- **Изменение порядка столбцов с помощью перетаскивания**  
  
     Пользователи могут переупорядочить столбцы в <xref:System.Windows.Controls.GridView> нажатии кнопки левой мыши, пока она находится над заголовком столбца, а затем перетащите столбец в новое положение. Пока пользователь перетаскивает заголовок столбца, отображается плавающей версии заголовка, а также сплошная черная линия, показывающая место вставки столбца.  
  
     Если требуется изменить стиль по умолчанию для плавающей версии <xref:System.Windows.Controls.GridViewColumnHeader> заголовка, укажите <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> значение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>типа, который срабатывает при установке свойства. Дополнительные сведения см. в разделе [Как создать стиль для перетаскиваемого заголовка столбца GridView](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
- **Изменение размера столбца по его содержимому**  
  
     Пользователям можно дважды щелкнуть границу справа от заголовка столбца, чтобы изменить размер столбца в соответствии с содержимым.  
  
    > [!NOTE]
    > Можно настроить <xref:System.Windows.Controls.GridViewColumn.Width%2A> свойство `Double.NaN` для получения такого же эффекта.  
  
- **Выбор элементов строк**  
  
     Пользователи могут выбрать один <xref:System.Windows.Controls.GridView>или несколько элементов в .  
  
     Если вы хотите <xref:System.Windows.Style> изменить выбранный элемент, см. [Use Triggers to Style Selected Items in a ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md)  
  
- **Прокрутка для просмотра содержимого, изначально не отображаемого на экране**  
  
     Если размер размера <xref:System.Windows.Controls.GridView> не достаточно велик, чтобы отобразить все элементы, пользователи могут прокручивать горизонтально или вертикально с помощью прокруток, которые обеспечиваются элементом <xref:System.Windows.Controls.ScrollViewer> управления. A <xref:System.Windows.Controls.Primitives.ScrollBar> скрыт, если все содержимое отображается в определенном направлении. При использовании полос прокрутки заголовки столбцов не прокручиваются по вертикали, но могут прокручиваться по горизонтали.  
  
- **Взаимодействие со столбцами путем нажатия кнопок заголовков столбцов**  
  
     При нажатии кнопки заголовка столбца можно отсортировать данные, которые отображаются в столбце, если указан алгоритм сортировки.  
  
     Вы можете <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обрабатывать событие для кнопок заголовка столбцов, чтобы обеспечить функциональность, как алгоритм сортировки. Чтобы справиться с <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событием для одного заголовка <xref:System.Windows.Controls.GridViewColumnHeader>столбца, установите обработчик события на . Чтобы настроить обработчик событий, обрабатывая <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событие для всех заголовков столбцов, установите обработчик на элемент управления. <xref:System.Windows.Controls.ListView>  
  
<a name="Obtaining_Other_Custom_Views"></a>
## <a name="obtaining-other-custom-views"></a>Получение других настраиваемых представлений  
 Класс, <xref:System.Windows.Controls.GridView> который происходит от <xref:System.Windows.Controls.ViewBase> абстрактного класса, является лишь одним <xref:System.Windows.Controls.ListView> из возможных режимов представления для класса. Можно создать другие <xref:System.Windows.Controls.ListView> пользовательские представления, <xref:System.Windows.Controls.ViewBase> вытекающие из класса. Пример настраиваемого режима представления см. в разделе [Создание пользовательского режима представления для ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>
## <a name="gridview-supporting-classes"></a>Вспомогательные классы GridView  
 Следующие классы <xref:System.Windows.Controls.GridView> поддерживают режим представления.  
  
- <xref:System.Windows.Controls.GridViewColumn>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GridViewRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewColumnCollection>  
  
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Controls.GridViewColumn>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.ViewBase>
- [Общие сведения об элементе управления ListView](listview-overview.md)
- [Сортировка столбцов GridView при нажатии на заголовок](how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Как-к темам](listview-how-to-topics.md)
