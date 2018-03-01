---
title: "Архитектура элемента управления ToolStrip"
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
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b112cb1e383b092c1bcc4403e04938b3b83c5ecc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="toolstrip-control-architecture"></a>Архитектура элемента управления ToolStrip
<xref:System.Windows.Forms.ToolStrip> И <xref:System.Windows.Forms.ToolStripItem> классы предоставляют гибкую расширяемую систему для отображения элементов на панели инструментов, меню и строки состояния. Эти классы содержатся в <xref:System.Windows.Forms> пространство имен и они обычно именуются с префиксом «ToolStrip» (такие как <xref:System.Windows.Forms.ToolStripOverflow>) или с суффиксом «Полосы» (например, <xref:System.Windows.Forms.MenuStrip>).  
  
## <a name="toolstrip"></a>ToolStrip  
 В следующих разделах описываются <xref:System.Windows.Forms.ToolStrip> и элементов управления, производных от него.  
  
 <xref:System.Windows.Forms.ToolStrip>— Абстрактный базовый класс для <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, и <xref:System.Windows.Forms.ContextMenuStrip>. Следующие объектной модели показана <xref:System.Windows.Forms.ToolStrip> иерархии наследования.  
  
 ![Модель объекта ToolStrip](../../../../docs/framework/winforms/controls/media/toolstripobjectmodel.gif "ToolStripObjectModel")  
Объектная модель элемента управления ToolStrip  
  
 Доступны все элементы в <xref:System.Windows.Forms.ToolStrip> через <xref:System.Windows.Forms.ToolStrip.Items%2A> коллекции. Доступны все элементы в <xref:System.Windows.Forms.ToolStripDropDownItem> через <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> коллекции. В классе, производном от <xref:System.Windows.Forms.ToolStrip>, можно также использовать <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> свойство для доступа к только элементов, отображаемых в текущий момент. Ниже перечислены элементы, которые в настоящее время не находятся в меню переполнения.  
  
 Следующие элементы специально предназначены для интегрированной работы с <xref:System.Windows.Forms.ToolStripSystemRenderer> и <xref:System.Windows.Forms.ToolStripProfessionalRenderer> во всех направлениях. Они доступны по умолчанию во время разработки для <xref:System.Windows.Forms.ToolStrip> управления:  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="menustrip"></a>MenuStrip  
 <xref:System.Windows.Forms.MenuStrip>является контейнером верхнего уровня, которое заменяет <xref:System.Windows.Forms.MainMenu>. Он также предоставляет управления ключами и несколько документов возможности интерфейса (MDI). С функциональной <xref:System.Windows.Forms.ToolStripDropDownItem> и <xref:System.Windows.Forms.ToolStripMenuItem> работают вместе с <xref:System.Windows.Forms.MenuStrip>, несмотря на то, что они являются производными от <xref:System.Windows.Forms.ToolStripItem>.  
  
 Следующие элементы специально предназначены для интегрированной работы с <xref:System.Windows.Forms.ToolStripSystemRenderer> и <xref:System.Windows.Forms.ToolStripProfessionalRenderer> во всех направлениях. Они доступны по умолчанию во время разработки для <xref:System.Windows.Forms.MenuStrip> управления:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="statusstrip"></a>StatusStrip  
 <xref:System.Windows.Forms.StatusStrip>заменяет <xref:System.Windows.Forms.StatusBar> элемента управления. Специальные возможности <xref:System.Windows.Forms.StatusStrip> включают пользовательскую структуру таблицы, поддержку изменения размера и перемещения захватов, формы и `Spring` свойство, которое обеспечивает <xref:System.Windows.Forms.ToolStripStatusLabel> для автоматического заполнения доступного пространства.  
  
 Следующие элементы специально предназначены для интегрированной работы с <xref:System.Windows.Forms.ToolStripSystemRenderer> и <xref:System.Windows.Forms.ToolStripProfessionalRenderer> во всех направлениях. Они доступны по умолчанию во время разработки для <xref:System.Windows.Forms.StatusStrip> управления:  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### <a name="contextmenustrip"></a>ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip>заменяет <xref:System.Windows.Forms.ContextMenu>. Можно связать <xref:System.Windows.Forms.ContextMenuStrip> с любым элементом управления и правой кнопкой мыши щелкните автоматически отображает контекстное меню (или контекстное меню). Можно показать <xref:System.Windows.Forms.ContextMenuStrip> программно с помощью <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> метод. <xref:System.Windows.Forms.ContextMenuStrip>поддерживает отменяемого <xref:System.Windows.Forms.ToolStripDropDown.Opening> и <xref:System.Windows.Forms.ToolStripDropDown.Closing> событий для обработки динамическое заполнение и ситуации с несколькими щелчками. <xref:System.Windows.Forms.ContextMenuStrip>поддерживает изображения, состояние пометки элемента меню, текст, клавиши доступа, сочетания клавиш и вложенные меню.  
  
 Следующие элементы специально предназначены для интегрированной работы с <xref:System.Windows.Forms.ToolStripSystemRenderer> и <xref:System.Windows.Forms.ToolStripProfessionalRenderer> во всех направлениях. Они доступны по умолчанию во время разработки для <xref:System.Windows.Forms.ContextMenuStrip> управления:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="toolstrip-generic-features"></a>Функции универсального элемента управления ToolStrip  
 Описываются возможности и поведение, являющиеся общими для <xref:System.Windows.Forms.ToolStrip> и производных элементов управления.  
  
#### <a name="painting"></a>Рисование  
 Можно сделать пользовательское оформление в <xref:System.Windows.Forms.ToolStrip> элементы управления несколькими способами. Как и для других элементов управления Windows Forms, <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.ToolStripItem> обладают переопределяемыми `OnPaint` методы и `Paint` события. Как при обычном рисовании система координат определяется относительно клиентской области элемента управления; левый верхний угол элемента управления является 0, 0. `Paint` Событий и `OnPaint` метод <xref:System.Windows.Forms.ToolStripItem> ведут себя как другие события рисования элемента управления.  
  
 <xref:System.Windows.Forms.ToolStrip> Элементов управления также предоставляет более подробный доступ к отрисовке элементов и контейнера с помощью <xref:System.Windows.Forms.ToolStripRenderer> класс, имеющий переопределяемые методы рисования фона, фоновый цвет элемента, изображения элемента, стрелки элемента, текста элемента и границей <xref:System.Windows.Forms.ToolStrip>. Аргументы событий для этих методов предоставляют несколько свойств, таких как прямоугольники, цвета и текстовые форматы, которые можно настроить желаемым образом.  
  
 Чтобы настроить некоторые аспекты способ рисования элемента, обычно переопределяется <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 При написании нового элемента и для управления всеми аспектами рисования, переопределить `OnPaint` метод. Изнутри `OnPaint`, можно использовать методы из <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 По умолчанию <xref:System.Windows.Forms.ToolStrip> включена двойная буферизация преимуществами <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> параметр.  
  
#### <a name="parenting"></a>Родительские связи  
 Концепция родительских связей и владения контейнером является более сложными <xref:System.Windows.Forms.ToolStrip> определяет, чем в других контейнерных элементов управления Windows Forms. Это требуется для поддержки динамических сценариев, например переполнения, совместного использования элементов раскрывающегося списка в нескольких <xref:System.Windows.Forms.ToolStrip> элементов, а также для поддержки создания <xref:System.Windows.Forms.ContextMenuStrip> из элемента управления.  
  
 В следующем списке описываются элементы, связанные с родительских связей и объясняет их использование.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A>Получает элемент, который является источником раскрывающегося элемента. Это похоже на <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, но вместо возвращения элемента управления, он возвращает <xref:System.Windows.Forms.ToolStripItem>.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>Определяет, какой элемент управления является источником для <xref:System.Windows.Forms.ContextMenuStrip> при нескольких элементов управления имеют одинаковое <xref:System.Windows.Forms.ContextMenuStrip>.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A>метод доступа только для чтения к <xref:System.Windows.Forms.ToolStripItem.Parent%2A> свойство. Родительский элемент отличается от владельца, что родительский элемент обозначает возвращенный текущий <xref:System.Windows.Forms.ToolStrip> , в котором отображается элемент, который может быть в области переполнения.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A>Возвращает <xref:System.Windows.Forms.ToolStrip> коллекция элементов которого содержит текущий <xref:System.Windows.Forms.ToolStripItem>. Это лучший способ ссылки <xref:System.Windows.Forms.ToolStrip.ImageList%2A> или других свойств на верхнем уровне <xref:System.Windows.Forms.ToolStrip> без написания специального кода обработки переполнения.  
  
#### <a name="behavior-of-inherited-controls"></a>Поведение унаследованных элементов управления  
 Следующие элементы управления блокируются при каждом использовании в наследовании:  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel>включающий панелей в <xref:System.Windows.Forms.ToolStripContainer> а также отдельные <xref:System.Windows.Forms.ToolStripPanel> элементов управления.  
  
 Например создайте новое приложение Windows Forms с помощью одного или нескольких элементов управления из приведенного выше списка. Задайте модификатор доступа одного или нескольких элементов управления для `public` или `protected`, а затем постройте проект. Добавьте форму, которая наследуется из первой формы, а затем выберите наследуемый элемент управления. Элемент управления выглядит заблокированным, как если бы модификатору доступа было `private`.  
  
#### <a name="toolstripcontainer-support-of-inheritance"></a>Поддержка ToolStripContainer наследования  
 <xref:System.Windows.Forms.ToolStripContainer> Элемент управления поддерживает ограниченные сценарии наследования, аналогичный приведенному ниже:  
  
1.  Создайте новое приложение Windows Forms.  
  
2.  Добавьте на форму элемент <xref:System.Windows.Forms.ToolStripContainer>.  
  
3.  Задайте модификатор доступа для <xref:System.Windows.Forms.ToolStripContainer> для `public` или `protected`.  
  
4.  Добавьте любое сочетание <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, и <xref:System.Windows.Forms.ContextMenuStrip> элементы управления <xref:System.Windows.Forms.ToolStripPanel> областей <xref:System.Windows.Forms.ToolStripContainer>.  
  
5.  Выполните построение проекта.  
  
6.  Добавьте форму, которая наследуется из первой формы.  
  
7.  Выберите наследуемого <xref:System.Windows.Forms.ToolStripContainer> в форме.  
  
#### <a name="inherited-behavior-of-child-controls"></a>Унаследованное поведение дочерних элементов управления  
 После выполнения предыдущих шагов, наследуемые происходит следующее:  
  
-   В конструкторе отображается элемент управления с унаследованным значком.  
  
-   <xref:System.Windows.Forms.ToolStripPanel> Заблокированные элементы управления, недоступны для выбора или изменения порядка их содержимое.  
  
-   Можно добавить элементы управления для <xref:System.Windows.Forms.ToolStripContentPanel>, перемещать элементы управления и сделать их дочерние элементы управления <xref:System.Windows.Forms.ToolStripContentPanel>.  
  
-   Изменения сохранятся после сборки формы.  
  
    > [!NOTE]
    >  Удалите модификатор доступа из всех <xref:System.Windows.Forms.ToolStripPanel> элементов управления, которые являются частью <xref:System.Windows.Forms.ToolStripContainer>. Модификатор доступа для <xref:System.Windows.Forms.ToolStripContainer> управляет весь элемент управления.  
  
#### <a name="partial-trust"></a>Частичное доверие  
 Ограничения `ToolStrip`при частичном доверии позволяют предотвратить случайный ввод личных сведений, которые могут быть использованы неавторизованными пользователями или службами. Защитные меры, как показано ниже:  
  
-   `ToolStripDropDown`элементы управления требуют <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> для отображения элементов в <xref:System.Windows.Forms.ToolStripControlHost>. Это относится к обоих встроенные элементы управления, такие как <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>, и <xref:System.Windows.Forms.ToolStripProgressBar> как хорошо созданным пользователем элементы управления. Если это требование не выполнено, эти элементы не отображаются. Исключение не возникает.  
  
-   Установка <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> свойства `false` не разрешен, а Отменяемый <xref:System.Windows.Forms.ToolStripDropDown.Closing> событие параметр учитывается. Это делает невозможным ввод более одного нажатия клавиш без отключения раскрывающегося элемента. Если это требование не соблюдается, то такие элементы не отображаются. Исключение не возникает.  
  
-   Многие нажатие клавиши, обработка событий не вызываются, если они встречаются в контексте с частичным доверием, отличный от <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>.  
  
-   Клавиши доступа не обрабатываются, если <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> не предоставляется.  
  
#### <a name="usage"></a>Использование  
 Следующие шаблоны использования иметь влияют на <xref:System.Windows.Forms.ToolStrip> макет, взаимодействие с клавиатурой и пользовательское поведение:  
  
-   Объединить<xref:System.Windows.Forms.ToolStripPanel>  
  
     <xref:System.Windows.Forms.ToolStrip> Может быть перемещен в пределах <xref:System.Windows.Forms.ToolStripPanel> и через <xref:System.Windows.Forms.ToolStripPanel>s. `Dock` Свойство игнорируется и если <xref:System.Windows.Forms.ToolStrip.Stretch%2A> свойство `false`, размер <xref:System.Windows.Forms.ToolStrip> увеличивается по мере добавления элементов <xref:System.Windows.Forms.ToolStripPanel>. Как правило <xref:System.Windows.Forms.ToolStrip> не участвует в последовательности табуляции.  
  
-   Закрепленное  
  
     <xref:System.Windows.Forms.ToolStrip> Помещается на одной стороне контейнера в фиксированном положении, а его размер увеличивается по всему краю, к которой она закреплена. Как правило <xref:System.Windows.Forms.ToolStrip> не участвует в последовательности табуляции.  
  
-   Абсолютное позиционирование  
  
     <xref:System.Windows.Forms.ToolStrip> — Как и другие элементы управления, в том, что он помещает <xref:System.Windows.Forms.Control.Location%2A> , имеет фиксированный размер и обычно участвует в последовательности табуляции.  
  
#### <a name="keyboard-interaction"></a>Взаимодействие с клавиатурой  
  
##### <a name="access-keys"></a>Клавиши доступа  
 Клавиши доступа, вместе с или после клавишу ALT, это единственный способ активации элемента управления с помощью клавиатуры. <xref:System.Windows.Forms.ToolStrip>поддерживает явные и неявные клавиш. Явное определение использует символ амперсанда (&) перед буквой. Неявное определение использует алгоритм, который пытается найти соответствующий элемент на основании порядка символов в данной `Text` свойство.  
  
##### <a name="shortcut-keys"></a>Сочетания клавиш  
 Сочетания клавиш, используемые <xref:System.Windows.Forms.MenuStrip> используется сочетание <xref:System.Windows.Forms.Keys> перечисления (который не зависящая от порядка) для определения сочетания клавиш. Можно также использовать <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> свойство для отображения сочетания клавиш только с текстом, например, отображение «Del» вместо «Удалить».  
  
##### <a name="navigation"></a>Навигация  
 Клавиша ALT активирует <xref:System.Windows.Forms.MenuStrip> , на который указывает <xref:System.Windows.Forms.Form.MainMenuStrip%2A>. Здесь сочетание клавиш CTRL + TAB переходит между <xref:System.Windows.Forms.ToolStrip> управления внутри `ToolStripPanel`s. Нажатие клавиши TAB и клавиш со стрелками на цифровой клавиатуре переходить между элементами в <xref:System.Windows.Forms.ToolStrip>. Специальный алгоритм обрабатывает навигацию в области переполнения. Выбирает пробел <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, или <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
##### <a name="focus-and-validation"></a>Фокус и проверки  
 При активации клавишей ALT <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.ToolStrip> обычно не переключает фокус с элемента управления, который в настоящее время находится в фокусе. Если имеется элемент управления, размещенные на <xref:System.Windows.Forms.MenuStrip> или раскрывающемся <xref:System.Windows.Forms.MenuStrip>, элемент управления получает фокус, когда пользователь нажимает клавишу TAB. Как правило <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter>, и <xref:System.Windows.Forms.Control.Leave> события <xref:System.Windows.Forms.MenuStrip> могут не возникать при активации с помощью клавиатуры. В таких случаях использовать <xref:System.Windows.Forms.MenuStrip.MenuActivate> и <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> события вместо него.  
  
 По умолчанию <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> — `false`. Вызовите <xref:System.Windows.Forms.ContainerControl.Validate%2A> явным образом в форме для выполнения проверки.  
  
#### <a name="layout"></a>Макет  
 Вы управляете <xref:System.Windows.Forms.ToolStrip> макета, выбрав один из членов <xref:System.Windows.Forms.ToolStripLayoutStyle> с <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> свойство.  
  
##### <a name="stack-layouts"></a>Макеты стека  
 Размещения — это расположение элементов рядом друг с другом на обоих концах <xref:System.Windows.Forms.ToolStrip>. Следующий список описывает макеты стека.  
  
-   Значение по умолчанию — <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow>. Этот параметр вызывает <xref:System.Windows.Forms.ToolStrip> изменять его макет автоматически в соответствии с <xref:System.Windows.Forms.ToolStrip.Orientation%2A> свойства для обработки скриптов перетаскивания и закрепления.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>Подготавливает к просмотру <xref:System.Windows.Forms.ToolStrip> элементы рядом друг с другом по вертикали.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow>Подготавливает к просмотру <xref:System.Windows.Forms.ToolStrip> элементы рядом друг с другом по горизонтали.  
  
##### <a name="other-features-of-stack-layouts"></a>Другие функции макетов стека  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>Определяет конец <xref:System.Windows.Forms.ToolStrip> выравнивание элемента.  
  
 Если элементы не соответствуют размерам <xref:System.Windows.Forms.ToolStrip>, автоматически появляется кнопка переполнения. <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> Значение свойства определяет, отображается ли элемент в области переполнения при необходимости или никогда.  
  
 В <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> событий, вы можете проверить <xref:System.Windows.Forms.ToolStripItem.Placement%2A> свойства, чтобы определить, был ли элемент расположен в основном <xref:System.Windows.Forms.ToolStrip>, переполнения <xref:System.Windows.Forms.ToolStrip>, или если она не отображается в данный момент вообще. Типичные причины, почему элемент не отображается, что он не помещается в основном <xref:System.Windows.Forms.ToolStrip> и его <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> было задано значение <xref:System.Windows.Forms.ToolStripItemOverflow.Never>.  
  
 Сделать <xref:System.Windows.Forms.ToolStrip> перемещаемым, поместив <xref:System.Windows.Forms.ToolStripPanel> и присвоения его <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> для <xref:System.Windows.Forms.ToolStripGripStyle.Visible>.  
  
##### <a name="other-layout-options"></a>Другие параметры структуры  
 Параметры макета, являются <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> и <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>.  
  
##### <a name="flow-layout"></a>Последовательное размещение  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>разметка используется по умолчанию для <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, и <xref:System.Windows.Forms.ToolStripOverflow>. Это похоже на <xref:System.Windows.Forms.FlowLayoutPanel>. Функции <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> макета, следующим образом:  
  
-   Все функции <xref:System.Windows.Forms.FlowLayoutPanel> предоставляемых <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> свойство. Необходимо привести <xref:System.Windows.Forms.LayoutSettings> класса <xref:System.Windows.Forms.FlowLayoutSettings> класса.  
  
-   Можно использовать <xref:System.Windows.Forms.ToolStripItem.Dock%2A> и <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> свойства в коде для выравнивания элементов внутри строки.  
  
-   Свойство <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> не учитывается.  
  
-   В <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> событий, вы можете проверить <xref:System.Windows.Forms.ToolStripItem.Placement%2A> свойства, чтобы определить, был ли элемент расположен в основном <xref:System.Windows.Forms.ToolStrip> или не соответствующие.  
  
-   Захват не отображается и поэтому <xref:System.Windows.Forms.ToolStrip> в <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> стиля макета в <xref:System.Windows.Forms.ToolStripPanel> не может быть перемещен.  
  
-   <xref:System.Windows.Forms.ToolStrip> Кнопки переполнения, не отображается, и <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> учитывается.  
  
##### <a name="table-layout"></a>Табличный макет  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>разметка используется по умолчанию для <xref:System.Windows.Forms.StatusStrip>. Это похоже на <xref:System.Windows.Forms.TableLayoutPanel>. Функции <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> макета, следующим образом:  
  
-   Все функции <xref:System.Windows.Forms.TableLayoutPanel> предоставляемых <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> свойство. Необходимо привести <xref:System.Windows.Forms.LayoutSettings> класса <xref:System.Windows.Forms.TableLayoutSettings> класса.  
  
-   Можно использовать <xref:System.Windows.Forms.ToolStripItem.Dock%2A> и <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> свойствам в коде для выравнивания элементов в пределах ячейки таблицы.  
  
-   Свойство <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> не учитывается.  
  
-   В <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> событий, вы можете проверить <xref:System.Windows.Forms.ToolStripItem.Placement%2A> свойства, чтобы определить, был ли элемент расположен в основном <xref:System.Windows.Forms.ToolStrip> или не соответствующие.  
  
-   Захват не отображается и поэтому <xref:System.Windows.Forms.ToolStrip> в <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> стиля макета в <xref:System.Windows.Forms.ToolStripPanel> не может быть перемещен.  
  
-   <xref:System.Windows.Forms.ToolStrip> Кнопки переполнения, не отображается, и <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> учитывается.  
  
## <a name="toolstripitem"></a>ToolStripItem  
 В следующих разделах описываются <xref:System.Windows.Forms.ToolStripItem> и элементов управления, производных от него.  
  
 <xref:System.Windows.Forms.ToolStripItem>— Абстрактный базовый класс для всех элементов, входящих в <xref:System.Windows.Forms.ToolStrip>. Следующие объектной модели показана <xref:System.Windows.Forms.ToolStripItem> иерархии наследования.  
  
 ![Модель объекта ToolStripItem](../../../../docs/framework/winforms/controls/media/toolstripitemobjectmodel.gif "ToolStripItemObjectModel")  
Модель объекта ToolStripItem  
  
 <xref:System.Windows.Forms.ToolStripItem>классы наследуются напрямую из <xref:System.Windows.Forms.ToolStripItem>, или они неявно наследуют от <xref:System.Windows.Forms.ToolStripItem> через <xref:System.Windows.Forms.ToolStripControlHost> или <xref:System.Windows.Forms.ToolStripDropDownItem>.  
  
 <xref:System.Windows.Forms.ToolStripItem>элементы управления, содержащиеся в <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, или <xref:System.Windows.Forms.ContextMenuStrip> и не может быть добавлен непосредственно в форму. Различные классы контейнеров предназначены для хранения соответствующего подмножества <xref:System.Windows.Forms.ToolStripItem> элементов управления.  
  
 В следующей таблице перечислены акции <xref:System.Windows.Forms.ToolStripItem> элементов управления и контейнеры, в которых они выглядят рекомендации. Хотя любой <xref:System.Windows.Forms.ToolStrip> элемент можно разместить в любом <xref:System.Windows.Forms.ToolStrip>-контейнере, производном этих элементов был разработан для поиска наиболее в следующих контейнерах:  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown>не отображается в области элементов конструктора.  
  
|Элемент в контейнере|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|  
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|  
|<xref:System.Windows.Forms.ToolStripButton>|Да|Нет|Нет|Нет|Да|  
|<xref:System.Windows.Forms.ToolStripComboBox>|Да|Да|Да|Нет|Да|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|Да|Нет|Нет|Да|Да|  
|<xref:System.Windows.Forms.ToolStripLabel>|Да|Нет|Нет|Да|Да|  
|<xref:System.Windows.Forms.ToolStripSeparator>|Да|Да|Да|Нет|Да|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|Да|Нет|Нет|Да|Да|  
|<xref:System.Windows.Forms.ToolStripTextBox>|Да|Да|Да|Нет|Да|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Нет|Да|Да|Нет|Нет|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|Нет|Нет|Нет|Да|Нет|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|Да|Нет|Нет|Да|Нет|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Да|Да|Нет|Да|Да|  
  
### <a name="toolstripbutton"></a>ToolStripButton  
 <xref:System.Windows.Forms.ToolStripButton>является элементом кнопки для <xref:System.Windows.Forms.ToolStrip>. Его можно вывести на экран с различными стилями границы, и его можно использовать для представления и активирования рабочих состояний. Можно также определить, он должен иметь фокус по умолчанию.  
  
### <a name="toolstriplabel"></a>ToolStripLabel  
 <xref:System.Windows.Forms.ToolStripLabel> Обеспечивает функциональные возможности метки в <xref:System.Windows.Forms.ToolStrip> элементов управления. <xref:System.Windows.Forms.ToolStripLabel> Подобно <xref:System.Windows.Forms.ToolStripButton> , не получает фокус по умолчанию и не отображается в нажатом или выделенном.  
  
 <xref:System.Windows.Forms.ToolStripLabel>как размещенный элемент поддерживает ключи доступа.  
  
 Используйте <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>, и <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> свойства <xref:System.Windows.Forms.ToolStripLabel> для поддержки элемента управления ссылки в <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel>— Это версия <xref:System.Windows.Forms.ToolStripLabel> разработан специально для использования в <xref:System.Windows.Forms.StatusStrip>. Специальные возможности включают <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>, и <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
### <a name="toolstripseparator"></a>ToolStripSeparator  
 <xref:System.Windows.Forms.ToolStripSeparator> Добавляет вертикальной или горизонтальной линией в панели инструментов или меню, в зависимости от ориентации. Он обеспечивает группирование или разделение элементов, например пунктов меню.  
  
 Можно добавить <xref:System.Windows.Forms.ToolStripSeparator> во время разработки, выбрав его из раскрывающегося списка. Тем не менее, можно автоматически создать <xref:System.Windows.Forms.ToolStripSeparator> , введя дефис (-) в узел шаблона конструктора или в <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> метод.  
  
### <a name="toolstripcontrolhost"></a>Руководство.  
 <xref:System.Windows.Forms.ToolStripControlHost>— Абстрактный базовый класс для <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox>, и <xref:System.Windows.Forms.ToolStripProgressBar>. <xref:System.Windows.Forms.ToolStripControlHost>можно размещать другие элементы управления, включая пользовательские элементы управления двумя способами:  
  
-   Создать <xref:System.Windows.Forms.ToolStripControlHost> с классом, который является производным от <xref:System.Windows.Forms.Control>. Для полного доступа к размещенным элементом управления и свойств, необходимо привести <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> свойство обратно к реальному классу, который оно представляет.  
  
-   Расширить <xref:System.Windows.Forms.ToolStripControlHost>и в конструкторе унаследованного класса по умолчанию, вызывает конструктор базового класса, передающий класс, производный от <xref:System.Windows.Forms.Control>. Этот параметр позволяет включить общие методы управления и свойства для упрощения доступа в <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripcombobox"></a>ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox>— <xref:System.Windows.Forms.ComboBox> оптимизированным для размещения в <xref:System.Windows.Forms.ToolStrip>. Подмножество свойств размещенного элемента управления и события представлены на <xref:System.Windows.Forms.ToolStripComboBox> уровень, но базовый <xref:System.Windows.Forms.ComboBox> управления полностью доступна с помощью <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> свойство.  
  
### <a name="toolstriptextbox"></a>ToolStripTextBox  
 <xref:System.Windows.Forms.ToolStripTextBox>— <xref:System.Windows.Forms.TextBox> оптимизированным для размещения в <xref:System.Windows.Forms.ToolStrip>. Подмножество свойств размещенного элемента управления и события представлены на <xref:System.Windows.Forms.ToolStripTextBox> уровень, но базовый <xref:System.Windows.Forms.TextBox> управления полностью доступна с помощью <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> свойство.  
  
### <a name="toolstripprogressbar"></a>ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar>— <xref:System.Windows.Forms.ProgressBar> оптимизированным для размещения в <xref:System.Windows.Forms.ToolStrip>. Подмножество свойств размещенного элемента управления и события представлены на <xref:System.Windows.Forms.ToolStripProgressBar> уровень, но базовый <xref:System.Windows.Forms.ProgressBar> управления полностью доступна с помощью <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> свойство.  
  
### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem>— Абстрактный базовый класс для <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton>, и <xref:System.Windows.Forms.ToolStripSplitButton>, который можно разместить элементы непосредственно или узла дополнительные элементы в контейнере раскрывающегося списка. Это можно сделать, задав <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> свойства <xref:System.Windows.Forms.ToolStripDropDown> и параметр <xref:System.Windows.Forms.ToolStrip.Items%2A> свойство <xref:System.Windows.Forms.ToolStripDropDown>. Доступ к этим напрямую с помощью раскрывающегося списка элементам <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> свойство.  
  
### <a name="toolstripmenuitem"></a>ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem>— <xref:System.Windows.Forms.ToolStripDropDownItem> , которые работают с <xref:System.Windows.Forms.ToolStripDropDownMenu> и <xref:System.Windows.Forms.ContextMenuStrip> для обработки особым соглашением выделение, макет и столбец для меню.  
  
### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton>выглядит как <xref:System.Windows.Forms.ToolStripButton>, но он демонстрирует раскрывающейся области, когда пользователь нажимает кнопку. Скрыть или отобразить стрелку раскрывающегося списка, установив <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> свойство. <xref:System.Windows.Forms.ToolStripDropDownButton>узлы <xref:System.Windows.Forms.ToolStripOverflowButton> , отображающая элементы, выходящие за пределы <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripsplitbutton"></a>ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton>объединяет кнопки и функциональности кнопки раскрывающегося списка.  
  
 Используйте <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> свойств для синхронизации <xref:System.Windows.Forms.Control.Click> событие выбранный элемент списка с элемента, показанное на кнопке.  
  
### <a name="toolstripitem-generic-features"></a>ToolStripItem универсальные функции  
 <xref:System.Windows.Forms.ToolStripItem>предоставляет следующие общие возможности и параметры для наследуемого элемента управления.  
  
-   Основные события  
  
-   Обработка изображений  
  
-   Выравнивание  
  
-   Связь текста и изображений  
  
-   Стиль отображения  
  
#### <a name="core-events"></a>Основные события  
 <xref:System.Windows.Forms.ToolStripItem>элементы управления получать свои собственные нажмите кнопку мыши и событиями рисования и можно выполнить предварительную обработку также клавиатуры.  
  
#### <a name="image-handling"></a>Обработка изображений  
 <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>, И <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> свойства относится к различным аспектам обработки изображений. Использование изображений в <xref:System.Windows.Forms.ToolStrip> элементов управления, настройка этих свойств напрямую или задав выполнения времени — только <xref:System.Windows.Forms.ToolStrip.ImageList%2A> свойство.  
  
 Масштабирование изображения определяется взаимодействием свойств в обоих <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.ToolStripItem>, как показано ниже:  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A>Масштаб конечного изображения определяется сочетанием изображения <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> и параметра контейнера <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> параметр.  
  
    -   Если <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> — `true` (по умолчанию) и <xref:System.Windows.Forms.ToolStripItemImageScaling> — <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>, то масштабирование производиться и <xref:System.Windows.Forms.ToolStrip> является размер самого большого элемента или предписанный минимальный размер.  
  
    -   Если <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> — `false` и <xref:System.Windows.Forms.ToolStripItemImageScaling> — <xref:System.Windows.Forms.ToolStripItemImageScaling.None>, ни изображения, ни <xref:System.Windows.Forms.ToolStrip> масштабирование происходит.  
  
#### <a name="alignment"></a>Выравнивание  
 Значение <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> свойство определяет конец <xref:System.Windows.Forms.ToolStrip> в которой появляется элемент. <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Работает только если свойство стиля макета <xref:System.Windows.Forms.ToolStrip> имеет одно из значений переполнения стека.  
  
 Элементы размещаются на <xref:System.Windows.Forms.ToolStrip> в том порядке, в котором отображаются элементы в коллекции элементов. Для программного изменения, где располагается элемент, используйте <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> метод, чтобы переместить элемент в коллекции. Этот метод перемещает элемент, но не происходит дублирования.  
  
#### <a name="text-and-image-relationship"></a>Текст и изображение связи  
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> Свойство определяет относительный положение изображения относительно текста на <xref:System.Windows.Forms.ToolStripItem>. Элементы, которых не хватает изображения и текст, рассматриваются как особые случаи, чтобы <xref:System.Windows.Forms.ToolStripItem> не отображает пустую область на месте отсутствующего элемента или элементов.  
  
#### <a name="display-style"></a>Стиль отображения  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>позволяет задавать значения свойств элемента текста и изображения при отображении сведений, которые требуется. Обычно используется для изменения только стиля отображения при отображении тот же элемент в другом контексте.  
  
## <a name="accessory-classes"></a>Вспомогательные классы  
 Классы, которые предоставляют различные дополнительные функциональные возможности включают:  
  
-   <xref:System.Windows.Forms.ToolStripManager>поддерживает <xref:System.Windows.Forms.ToolStrip>-связанные задачи для всего приложения, такие как слияние, параметры и модуль подготовки отчетов.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>позволяет применять определенный стиль или тему, <xref:System.Windows.Forms.ToolStrip> легко.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer>создает перья и кисти на основании заменяемой таблицы цветов (<xref:System.Windows.Forms.ProfessionalColorTable>).  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer>применяет системные цвета и плоский визуальный стиль к <xref:System.Windows.Forms.ToolStrip> приложений.  
  
-   <xref:System.Windows.Forms.ToolStripContainer>Аналогично <xref:System.Windows.Forms.SplitContainer>. Она использует четыре закрепленные боковые панели (экземпляры <xref:System.Windows.Forms.ToolStripPanel>) и одна центральная панель (экземпляр <xref:System.Windows.Forms.ToolStripContentPanel>) для создания типового расположения. Не удается удалить боковые панели, но их можно скрыть. Можно удалить ни скрыть центральную панель. Можно упорядочить один или несколько <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, или <xref:System.Windows.Forms.StatusStrip> центра панель элементов управления в боковые панели, а также можно использовать для других элементов управления. <xref:System.Windows.Forms.ToolStripContentPanel> Также предоставляет способ для получения поддержки модуля подготовки отчетов в текст для согласованного внешнего вида формы. <xref:System.Windows.Forms.ToolStripContainer>не поддерживает многодокументный интерфейс (MDI).  
  
-   <xref:System.Windows.Forms.ToolStripPanel>Предоставляет место для перемещения и расположения <xref:System.Windows.Forms.ToolStrip> элементов управления. Если это необходимо, можно использовать только одну панель и <xref:System.Windows.Forms.ToolStripPanel> хорошо работает в сценариях MDI.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)  
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [Элемент управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [Элемент управления StatusStrip](../../../../docs/framework/winforms/controls/statusstrip-control.md)  
 [Элемент управления ContextMenuStrip](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)  
 [Элемент управления BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
