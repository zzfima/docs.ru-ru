---
title: Архитектура элемента управления ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: d0a1441e9bae8d2c1f938e7399c11e736708da4d
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363827"
---
# <a name="toolstrip-control-architecture"></a>Архитектура элемента управления ToolStrip

Классы <xref:System.Windows.Forms.ToolStrip> и<xref:System.Windows.Forms.ToolStripItem> предоставляют гибкую, расширяемую систему для отображения элементов панели инструментов, состояния и меню. Все эти классы содержатся в <xref:System.Windows.Forms> пространстве имен, и им обычно присваиваются имена с префиксом ToolStrip (например, <xref:System.Windows.Forms.ToolStripOverflow>) или с суффиксом "полоск" (например, <xref:System.Windows.Forms.MenuStrip>).

## <a name="toolstrip"></a>ToolStrip

В следующих разделах описываются <xref:System.Windows.Forms.ToolStrip> и элементы управления, производные от него.

<xref:System.Windows.Forms.ToolStrip>является абстрактным базовым классом <xref:System.Windows.Forms.StatusStrip>для <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>и. В следующей объектной модели показана <xref:System.Windows.Forms.ToolStrip> иерархия наследования.

![Схема, на которой показана объектная модель ToolStrip.](./media/toolstrip-control-architecture/toolstrip-object-model.gif)

Доступ ко всем элементам в <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip.Items%2A> коллекции можно получить через коллекцию. Доступ ко всем элементам в <xref:System.Windows.Forms.ToolStripDropDownItem> <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> коллекции можно получить через коллекцию. В классе, производном <xref:System.Windows.Forms.ToolStrip>от, можно также <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> использовать свойство для доступа только к отображаемым в данный момент элементам. Это элементы, которые в настоящее время не находятся в меню переполнения.

Следующие элементы специально предназначены для эффективной работы с обоими <xref:System.Windows.Forms.ToolStripSystemRenderer> <xref:System.Windows.Forms.ToolStripProfessionalRenderer> ориентациями. Они доступны по умолчанию во время разработки для <xref:System.Windows.Forms.ToolStrip> элемента управления:

- <xref:System.Windows.Forms.ToolStripButton>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="menustrip"></a>MenuStrip

<xref:System.Windows.Forms.MenuStrip>— это контейнер верхнего уровня, который заменяется <xref:System.Windows.Forms.MainMenu>. Он также обеспечивает обработку ключей и возможности многодокументного интерфейса (MDI). <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ToolStripItem>Функционально и работает<xref:System.Windows.Forms.ToolStripMenuItem> вместе с, хотя они являются производными от. <xref:System.Windows.Forms.ToolStripDropDownItem>

Следующие элементы специально предназначены для эффективной работы с обоими <xref:System.Windows.Forms.ToolStripSystemRenderer> <xref:System.Windows.Forms.ToolStripProfessionalRenderer> ориентациями. Они доступны по умолчанию во время разработки для <xref:System.Windows.Forms.MenuStrip> элемента управления:

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="statusstrip"></a>StatusStrip

<xref:System.Windows.Forms.StatusStrip><xref:System.Windows.Forms.StatusBar> заменяет элемент управления. Специальные функции <xref:System.Windows.Forms.StatusStrip> включают в себя пользовательский макет таблицы, поддержку размеров формы и перемещение освоиться, а также `Spring` <xref:System.Windows.Forms.ToolStripStatusLabel> свойство, которое позволяет автоматически заполнять доступное пространство.

Следующие элементы специально предназначены для эффективной работы с обоими <xref:System.Windows.Forms.ToolStripSystemRenderer> <xref:System.Windows.Forms.ToolStripProfessionalRenderer> ориентациями. Они доступны по умолчанию во время разработки для <xref:System.Windows.Forms.StatusStrip> элемента управления:

- <xref:System.Windows.Forms.ToolStripStatusLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripProgressBar>

### <a name="contextmenustrip"></a>ContextMenuStrip

<xref:System.Windows.Forms.ContextMenuStrip> заменяет <xref:System.Windows.Forms.ContextMenu>. Можно связать <xref:System.Windows.Forms.ContextMenuStrip> с любым элементом управления, а щелчок правой кнопкой мыши автоматически выводит контекстное меню (или контекстное меню). Можно отобразить <xref:System.Windows.Forms.ContextMenuStrip> программно с <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> помощью метода. <xref:System.Windows.Forms.ContextMenuStrip>поддерживает <xref:System.Windows.Forms.ToolStripDropDown.Opening> отменяемые <xref:System.Windows.Forms.ToolStripDropDown.Closing> и события для управления динамическим заполнением и сценариями с несколькими щелчками. <xref:System.Windows.Forms.ContextMenuStrip>поддерживает изображения, элементы меню, флажки, текст, клавиши доступа, ярлыки и каскадные меню.

Следующие элементы специально предназначены для эффективной работы с обоими <xref:System.Windows.Forms.ToolStripSystemRenderer> <xref:System.Windows.Forms.ToolStripProfessionalRenderer> ориентациями. Они доступны по умолчанию во время разработки для <xref:System.Windows.Forms.ContextMenuStrip> элемента управления:

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="toolstrip-generic-features"></a>Универсальные функции ToolStrip

В следующих разделах описываются функции и поведение, являющиеся универсальными для <xref:System.Windows.Forms.ToolStrip> элементов управления и, производных от.

#### <a name="painting"></a>Оформленные

Пользовательское рисование в <xref:System.Windows.Forms.ToolStrip> элементах управления можно выполнять несколькими способами. Как <xref:System.Windows.Forms.ToolStrip> и в случае с другими элементами управления <xref:System.Windows.Forms.ToolStripItem> Windows Forms, у и `OnPaint` обоих имеются `Paint` переопределяемые методы и события. Как и при обычном рисовании, система координат определяется относительно клиентской области элемента управления. то есть верхний левый угол элемента управления равен 0, 0. Событие и `OnPaint` метод<xref:System.Windows.Forms.ToolStripItem> ведут себя так же, как и другие события рисования элемента управления. `Paint`

Элементы управления также обеспечивают более точный доступ к отрисовке элементов и контейнеров <xref:System.Windows.Forms.ToolStripRenderer> с помощью класса, который имеет переопределяемые методы для рисования фона, фона элемента, изображения элемента, стрелки элемента, текста элемента и границы <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStrip>. Аргументы события для этих методов предоставляют несколько свойств, таких как прямоугольники, цвета и текстовые форматы, которые можно настроить по желанию.

Чтобы настроить лишь несколько аспектов рисования элемента, обычно следует переопределить <xref:System.Windows.Forms.ToolStripRenderer>.

Если вы пишете новый элемент и хотите управлять всеми аспектами рисования, переопределите `OnPaint` метод. В можно использовать методы <xref:System.Windows.Forms.ToolStripRenderer>из. `OnPaint`

По умолчанию <xref:System.Windows.Forms.ToolStrip> используется двойная буферизация с использованием <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> параметра.

#### <a name="parenting"></a>Родительские связи

Концепция владения контейнером и родительских элементов более сложна в <xref:System.Windows.Forms.ToolStrip> элементах управления, чем в других Windows Forms контейнерных элементах управления. Это необходимо для поддержки динамических сценариев, таких как переполнение, совместное использование раскрывающихся элементов <xref:System.Windows.Forms.ToolStrip> в нескольких элементах и поддержка создания <xref:System.Windows.Forms.ContextMenuStrip> элемента из элемента управления.

В следующем списке описываются элементы, связанные с родительским элементом, и объясняется их использование.

- <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A>обращается к элементу, который является источником раскрывающегося элемента. Это похоже на <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, но вместо возврата элемента управления <xref:System.Windows.Forms.ToolStripItem>возвращается.

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>Определяет, какой элемент управления является источником, <xref:System.Windows.Forms.ContextMenuStrip> когда несколько элементов управления совместно используют <xref:System.Windows.Forms.ContextMenuStrip>один и тот же объект.

- <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A>метод является методом доступа только для чтения к <xref:System.Windows.Forms.ToolStripItem.Parent%2A> свойству. Родительский объект отличается от владельца тем, что родительский элемент обозначает <xref:System.Windows.Forms.ToolStrip> возвращенный текущий объект, который может находиться в области переполнения.

- <xref:System.Windows.Forms.ToolStripItem.Owner%2A>Возвращает объект <xref:System.Windows.Forms.ToolStrip> , коллекция элементов которого содержит текущий <xref:System.Windows.Forms.ToolStripItem>объект. Это лучший способ ссылки <xref:System.Windows.Forms.ToolStrip.ImageList%2A> на или другие свойства верхнего уровня <xref:System.Windows.Forms.ToolStrip> без написания специального кода для управления переполнением.

#### <a name="behavior-of-inherited-controls"></a>Поведение наследуемых элементов управления

Следующие элементы управления блокируются всякий раз, когда они используются при наследовании:

- <xref:System.Windows.Forms.ToolStrip>

- <xref:System.Windows.Forms.MenuStrip>

- <xref:System.Windows.Forms.ContextMenuStrip>

- <xref:System.Windows.Forms.StatusStrip>

- <xref:System.Windows.Forms.ToolStripPanel>включает панели в <xref:System.Windows.Forms.ToolStripContainer> , а также отдельные <xref:System.Windows.Forms.ToolStripPanel> элементы управления.

Например, создайте новое Windows Forms приложение с помощью одного или нескольких элементов управления из предыдущего списка. Установите модификатор доступа одного или нескольких элементов управления в `public` значение или `protected`, а затем выполните сборку проекта. Добавьте форму, которая наследуется от первой формы, а затем выберите наследуемый элемент управления. Элемент управления отображается как заблокированный, как если бы его модификатор доступа `private`имел значение.

#### <a name="toolstripcontainer-support-of-inheritance"></a>Поддержка наследования в ToolStripContainer

<xref:System.Windows.Forms.ToolStripContainer> Элемент управления поддерживает ограниченные наследуемые сценарии, как показано в следующем примере:

1. Создайте новое приложение Windows Forms.

2. Добавьте на форму элемент <xref:System.Windows.Forms.ToolStripContainer>.

3. Установите модификатор <xref:System.Windows.Forms.ToolStripContainer> доступа для объекта в `public` или `protected`.

4. <xref:System.Windows.Forms.ToolStrip>Добавьте любое сочетание элементов управления <xref:System.Windows.Forms.MenuStrip>, и <xref:System.Windows.Forms.ContextMenuStrip> в <xref:System.Windows.Forms.ToolStripPanel> регионы <xref:System.Windows.Forms.ToolStripContainer>.

5. Выполните построение проекта.

6. Добавьте форму, которая наследуется от первой формы.

7. Выберите наследуемый <xref:System.Windows.Forms.ToolStripContainer> в форме.

#### <a name="inherited-behavior-of-child-controls"></a>Унаследованное поведение дочерних элементов управления

После выполнения описанных выше действий происходит следующее наследуемое поведение:

- В конструкторе элемент управления отображается с наследуемым значком.

- <xref:System.Windows.Forms.ToolStripPanel> Элементы управления заблокированы; нельзя выбирать или переупорядочивать их содержимое.

- Можно добавить элементы управления <xref:System.Windows.Forms.ToolStripContentPanel>в, переместить элементы управления и сделать их дочерними элементами управления. <xref:System.Windows.Forms.ToolStripContentPanel>

- Изменения сохраняются после создания формы.

  > [!NOTE]
  > Удалите модификаторы доступа из всех <xref:System.Windows.Forms.ToolStripPanel> элементов управления, входящих в <xref:System.Windows.Forms.ToolStripContainer>состав. Модификатор доступа объекта <xref:System.Windows.Forms.ToolStripContainer> управляет всем элементом управления.

#### <a name="partial-trust"></a>Частичное доверие

Ограничения `ToolStrip`в случае частичного доверия предназначены для предотвращения случайного ввода персональных данных, которые могут использоваться неавторизованными лицами или службами. Ниже приведены защитные меры.

- `ToolStripDropDown`элементы управления <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> должны отображать элементы <xref:System.Windows.Forms.ToolStripControlHost>в. Это относится как к встроенным элементам управления <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>таким как <xref:System.Windows.Forms.ToolStripProgressBar> ,, так и к элементам управления, созданным пользователем. Если это требование не соблюдается, эти элементы не отображаются. Исключение не возникает.

- Задание значения для `false` <xref:System.Windows.Forms.ToolStripDropDown.Closing> свойства недопустимо, а параметр события Canceled <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> игнорируется. Это делает невозможным ввод более одного нажатия клавиши без закрытия раскрывающегося элемента. Если это требование не соблюдается, такие элементы не отображаются. Исключение не возникает.

- Многие события обработки нажатия клавиши не будут вызываться, если они происходят в контекстах с частичным доверием, отличным от <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>.

- Ключи доступа не обрабатываются <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> , если не предоставлено.

#### <a name="usage"></a>Использование

Следующие шаблоны использования влияют на <xref:System.Windows.Forms.ToolStrip> макет, взаимодействие с клавиатурой и поведение конечных пользователей.

- Соединено в<xref:System.Windows.Forms.ToolStripPanel>

  Может перемещаться в <xref:System.Windows.Forms.ToolStripPanel> и <xref:System.Windows.Forms.ToolStripPanel>в пределах. <xref:System.Windows.Forms.ToolStrip> `false` <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripPanel>Свойство игнорируется, и <xref:System.Windows.Forms.ToolStrip.Stretch%2A> если свойство имеет значение, размер увеличивается по мере добавления элементов в. `Dock` Как правило, <xref:System.Windows.Forms.ToolStrip> объект не участвует в последовательности табуляции.

- Закрепленное

  Объект <xref:System.Windows.Forms.ToolStrip> размещается на одной стороне контейнера в фиксированной положении, а его размер расширяется по всему краю, к которому он прикреплен. Как правило, <xref:System.Windows.Forms.ToolStrip> объект не участвует в последовательности табуляции.

- Абсолютное позиционирование

  Аналогично другим элементам управления, в том, что он размещается <xref:System.Windows.Forms.Control.Location%2A> свойством, имеет фиксированный размер и обычно участвует в последовательности табуляции. <xref:System.Windows.Forms.ToolStrip>

#### <a name="keyboard-interaction"></a>Взаимодействие с клавиатурой

##### <a name="access-keys"></a>Ключи доступа

В сочетании с клавишей ALT или после нее клавиши доступа — это один из способов активации элемента управления с помощью клавиатуры. <xref:System.Windows.Forms.ToolStrip>поддерживает явные и неявные ключи доступа. В явном определении используется символ амперсанда (&), предшествующий букве. Неявное определение использует алгоритм, который пытается найти соответствующий элемент на основе порядка символов в заданном `Text` свойстве.

##### <a name="shortcut-keys"></a>Сочетания клавиш

Сочетания клавиш, используемые <xref:System.Windows.Forms.MenuStrip> , используют сочетание <xref:System.Windows.Forms.Keys> перечислений (не зависящее от порядка) для определения сочетания клавиш. Можно также использовать <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> свойство для отображения сочетания клавиш только с текстом, например для отображения «Del» вместо «DELETE».

##### <a name="navigation"></a>Навигация

Клавиша Alt активирует объект <xref:System.Windows.Forms.MenuStrip> , <xref:System.Windows.Forms.Form.MainMenuStrip%2A>на который указывает. После этого с помощью клавиш CTRL + TAB осуществляется <xref:System.Windows.Forms.ToolStrip> переход между `ToolStripPanel`элементами управления в s. Клавиша TAB и клавиши со стрелками на цифровой клавиатуре переходят между элементами <xref:System.Windows.Forms.ToolStrip>в. Специальный алгоритм обрабатывает навигацию в области переполнения. Пробел выбирает <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>или. <xref:System.Windows.Forms.ToolStripSplitButton>

##### <a name="focus-and-validation"></a>Фокус и проверка

При активации с помощью клавиши <xref:System.Windows.Forms.MenuStrip> Alt или <xref:System.Windows.Forms.ToolStrip> , как правило, не принимает фокус с элемента управления, в котором в данный момент находится фокус. Если имеется элемент управления <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MenuStrip>, размещенный в или раскрывающемся списке, элемент управления получает фокус, когда пользователь нажимает клавишу TAB. Как правило <xref:System.Windows.Forms.Control.GotFocus>, события, <xref:System.Windows.Forms.Control.LostFocus> <xref:System.Windows.Forms.Control.Enter> <xref:System.Windows.Forms.Control.Leave>,и могутневызыватьсяприихактивацииспомощьюклавиатуры.<xref:System.Windows.Forms.MenuStrip> В таких случаях используйте <xref:System.Windows.Forms.MenuStrip.MenuActivate> вместо него события и. <xref:System.Windows.Forms.MenuStrip.MenuDeactivate>

По умолчанию <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> имеет `false`значение. Вызовите <xref:System.Windows.Forms.ContainerControl.Validate%2A> явную форму, чтобы выполнить проверку.

#### <a name="layout"></a>Макет

Вы управляете <xref:System.Windows.Forms.ToolStrip> макетом, выбрав один из <xref:System.Windows.Forms.ToolStripLayoutStyle> членов со <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> свойством.

##### <a name="stack-layouts"></a>Макеты стеков

Стек — это расположение элементов рядом друг с другом в обоих концах <xref:System.Windows.Forms.ToolStrip>. В следующем списке описываются макеты стеков.

- Значение по умолчанию — <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow>. Этот параметр приводит <xref:System.Windows.Forms.ToolStrip> к автоматическому изменению макета в соответствии <xref:System.Windows.Forms.ToolStrip.Orientation%2A> со свойством для управления сценариями перетаскивания и закрепления.

- <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow><xref:System.Windows.Forms.ToolStrip> отображает элементы рядом друг с другом по вертикали.

- <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow><xref:System.Windows.Forms.ToolStrip> отображает элементы рядом друг с другом по горизонтали.

##### <a name="other-features-of-stack-layouts"></a>Другие функции макетов стеков

<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>Определяет конец, <xref:System.Windows.Forms.ToolStrip> на который выдается элемент.

Если элементы не помещаются <xref:System.Windows.Forms.ToolStrip>в, автоматически отображается кнопка переполнения. Параметр <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> свойства определяет, отображается ли элемент в области переполнения всегда (при необходимости) или никогда.

В событии можно <xref:System.Windows.Forms.ToolStripItem.Placement%2A> проверить свойство, чтобы определить, был ли элемент помещен в главное <xref:System.Windows.Forms.ToolStrip>, переполнение <xref:System.Windows.Forms.ToolStrip>или если в настоящий момент он не отображается. <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> Типичными причинами, по которым элемент не отображается, является то, что элемент не поместился <xref:System.Windows.Forms.ToolStrip> в основной <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> объект, а его <xref:System.Windows.Forms.ToolStripItemOverflow.Never>свойство было установлено в значение.

Сделайте его <xref:System.Windows.Forms.ToolStripPanel> <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> <xref:System.Windows.Forms.ToolStripGripStyle.Visible>перемещаемым, поместив его в и задав для свойства значение. <xref:System.Windows.Forms.ToolStrip>

##### <a name="other-layout-options"></a>Другие параметры макета

Другие параметры макета: <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> и. <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>

##### <a name="flow-layout"></a>Потоковый макет

<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>Макет является значением по умолчанию <xref:System.Windows.Forms.ToolStripDropDownMenu>для <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripOverflow>и. Он аналогичен <xref:System.Windows.Forms.FlowLayoutPanel>. Существуют следующие функции <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> макета.

- Все функции <xref:System.Windows.Forms.FlowLayoutPanel> предоставляются <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> свойством. Необходимо привести <xref:System.Windows.Forms.LayoutSettings> класс <xref:System.Windows.Forms.FlowLayoutSettings> к классу.

- Для выровняйте элементы <xref:System.Windows.Forms.ToolStripItem.Dock%2A> в <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> строке можно использовать свойства и в коде.

- Свойство <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> не учитывается.

- В событии можно <xref:System.Windows.Forms.ToolStripItem.Placement%2A> проверить свойство, чтобы определить, был ли элемент помещен в основной <xref:System.Windows.Forms.ToolStrip> или не помещается. <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>

- Захват не готовится к просмотру, поэтому <xref:System.Windows.Forms.ToolStrip> в <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> стиле макета в <xref:System.Windows.Forms.ToolStripPanel> нельзя перемещаться.

- Кнопка <xref:System.Windows.Forms.ToolStrip> переполнения не подготавливается к <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> просмотру и игнорируется.

##### <a name="table-layout"></a>Табличный макет

<xref:System.Windows.Forms.ToolStripLayoutStyle.Table>Макет является значением по умолчанию для <xref:System.Windows.Forms.StatusStrip>. Он аналогичен <xref:System.Windows.Forms.TableLayoutPanel>. Существуют следующие функции <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> макета.

- Все функции <xref:System.Windows.Forms.TableLayoutPanel> предоставляются <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> свойством. Необходимо привести <xref:System.Windows.Forms.LayoutSettings> класс <xref:System.Windows.Forms.TableLayoutSettings> к классу.

- Для выровняйте элементы <xref:System.Windows.Forms.ToolStripItem.Dock%2A> в <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> ячейке таблицы можно использовать свойства и в коде.

- Свойство <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> не учитывается.

- В событии можно <xref:System.Windows.Forms.ToolStripItem.Placement%2A> проверить свойство, чтобы определить, был ли элемент помещен в основной <xref:System.Windows.Forms.ToolStrip> или не помещается. <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>

- Захват не готовится к просмотру, поэтому <xref:System.Windows.Forms.ToolStrip> в <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> стиле макета в <xref:System.Windows.Forms.ToolStripPanel> нельзя перемещаться.

- Кнопка <xref:System.Windows.Forms.ToolStrip> переполнения не подготавливается к <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> просмотру и игнорируется.

## <a name="toolstripitem"></a>ToolStripItem

В следующих разделах описываются <xref:System.Windows.Forms.ToolStripItem> и элементы управления, производные от него.

<xref:System.Windows.Forms.ToolStripItem>является абстрактным базовым классом для всех элементов, которые переходят в <xref:System.Windows.Forms.ToolStrip>. В следующей объектной модели показана <xref:System.Windows.Forms.ToolStripItem> иерархия наследования.

![Схема, на которой показана объектная модель ToolStripItem.](./media/toolstrip-control-architecture/toolstripitem-object-model.gif)

<xref:System.Windows.Forms.ToolStripItem>классы либо наследуются <xref:System.Windows.Forms.ToolStripItem>непосредственно от, либо неявно наследуются <xref:System.Windows.Forms.ToolStripDropDownItem>от <xref:System.Windows.Forms.ToolStripItem> с помощью <xref:System.Windows.Forms.ToolStripControlHost> или.

<xref:System.Windows.Forms.ToolStripItem>элементы управления должны содержаться <xref:System.Windows.Forms.ToolStrip>в <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, или <xref:System.Windows.Forms.ContextMenuStrip> и не могут быть добавлены непосредственно в форму. Различные классы контейнеров предназначены для размещения соответствующего подмножества <xref:System.Windows.Forms.ToolStripItem> элементов управления.

В следующей таблице перечислены стандартные <xref:System.Windows.Forms.ToolStripItem> элементы управления и контейнеры, в которых они выглядят лучше. Хотя любой <xref:System.Windows.Forms.ToolStrip> элемент может размещаться в любом <xref:System.Windows.Forms.ToolStrip>контейнере, производном от, эти элементы были спроектированы для лучшего поиска в следующих контейнерах:

> [!NOTE]
> <xref:System.Windows.Forms.ToolStripDropDown>не отображается в панели элементов конструктора.

|Вложенный элемент|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|
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

<xref:System.Windows.Forms.ToolStripButton>— Это элемент кнопки для <xref:System.Windows.Forms.ToolStrip>. Его можно отобразить с помощью различных стилей границ, и вы можете использовать его для представления и активации рабочих состояний. Вы также можете определить, что он имеет фокус по умолчанию.

### <a name="toolstriplabel"></a>тулстриплабел

Предоставляет функциональные возможности меток в <xref:System.Windows.Forms.ToolStrip> элементах управления. <xref:System.Windows.Forms.ToolStripLabel> Объект <xref:System.Windows.Forms.ToolStripLabel> похож на <xref:System.Windows.Forms.ToolStripButton> , который не получает фокус по умолчанию и не отображается как помещенный или выделенный.

<xref:System.Windows.Forms.ToolStripLabel>так как размещенный элемент поддерживает ключи доступа.

<xref:System.Windows.Forms.LinkLabel.LinkColor%2A>Используйте свойства, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>и <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> в<xref:System.Windows.Forms.ToolStripLabel>для поддержки элемента управления Link в. <xref:System.Windows.Forms.ToolStrip>

### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel

<xref:System.Windows.Forms.ToolStripStatusLabel>— Это версия <xref:System.Windows.Forms.ToolStripLabel> , разработанная специально для использования <xref:System.Windows.Forms.StatusStrip>в. К специальным возможностям относятся <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>и <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.

### <a name="toolstripseparator"></a>тулстрипсепаратор

<xref:System.Windows.Forms.ToolStripSeparator> Добавляет вертикальную или горизонтальную линию на панель инструментов или в меню в зависимости от ориентации. Он обеспечивает группирование или различие между элементами, например, в меню.

Вы можете добавить <xref:System.Windows.Forms.ToolStripSeparator> во время разработки, выбрав его из раскрывающегося списка. Однако можно также автоматически создать <xref:System.Windows.Forms.ToolStripSeparator> , введя дефис (-) в узле шаблона конструктора или <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> в методе.

### <a name="toolstripcontrolhost"></a>ToolStripControlHost

<xref:System.Windows.Forms.ToolStripControlHost>является абстрактным базовым классом <xref:System.Windows.Forms.ToolStripTextBox>для <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripProgressBar>и. <xref:System.Windows.Forms.ToolStripControlHost>может размещать другие элементы управления, включая пользовательские элементы управления, двумя способами:

- Создайте объект <xref:System.Windows.Forms.ToolStripControlHost> с классом, производным от <xref:System.Windows.Forms.Control>. Для полного доступа к размещенному элементу управления и свойствам необходимо <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> привести свойство к реальному классу, который он представляет.

- Расширьте <xref:System.Windows.Forms.ToolStripControlHost>и в конструкторе без параметров унаследованного класса вызовите конструктор базового класса, передав класс, производный от <xref:System.Windows.Forms.Control>. Этот параметр позволяет заключить общие методы управления и свойства для упрощения доступа <xref:System.Windows.Forms.ToolStrip>в.

### <a name="toolstripcombobox"></a>ToolStripComboBox

<xref:System.Windows.Forms.ToolStripComboBox>оптимизирован для размещения <xref:System.Windows.Forms.ToolStrip>в. <xref:System.Windows.Forms.ComboBox> Подмножество свойств и событий размещаемого элемента управления предоставляется на <xref:System.Windows.Forms.ToolStripComboBox> уровне, но базовый <xref:System.Windows.Forms.ComboBox> элемент управления полностью доступен через <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> свойство.

### <a name="toolstriptextbox"></a>тулстриптекстбокс

<xref:System.Windows.Forms.ToolStripTextBox>оптимизирован для размещения <xref:System.Windows.Forms.ToolStrip>в. <xref:System.Windows.Forms.TextBox> Подмножество свойств и событий размещаемого элемента управления предоставляется на <xref:System.Windows.Forms.ToolStripTextBox> уровне, но базовый <xref:System.Windows.Forms.TextBox> элемент управления полностью доступен через <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> свойство.

### <a name="toolstripprogressbar"></a>ToolStripProgressBar

<xref:System.Windows.Forms.ToolStripProgressBar>оптимизирован для размещения <xref:System.Windows.Forms.ToolStrip>в. <xref:System.Windows.Forms.ProgressBar> Подмножество свойств и событий размещаемого элемента управления предоставляется на <xref:System.Windows.Forms.ToolStripProgressBar> уровне, но базовый <xref:System.Windows.Forms.ProgressBar> элемент управления полностью доступен через <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> свойство.

### <a name="toolstripdropdownitem"></a>тулстрипдропдовнитем

<xref:System.Windows.Forms.ToolStripDropDownItem>является абстрактным базовым классом <xref:System.Windows.Forms.ToolStripDropDownButton>для <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripSplitButton>и, который может размещать элементы напрямую или размещать дополнительные элементы в раскрывающемся контейнере. Для этого нужно задать <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> для свойства <xref:System.Windows.Forms.ToolStripDropDown>значение <xref:System.Windows.Forms.ToolStrip.Items%2A>изадать свойство объекта. <xref:System.Windows.Forms.ToolStripDropDown> Доступ к этим раскрывающимся элементам осуществляется непосредственно <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> через свойство.

### <a name="toolstripmenuitem"></a>ToolStripMenuItem

<xref:System.Windows.Forms.ToolStripMenuItem>Объект <xref:System.Windows.Forms.ToolStripDropDownItem> , работающий с <xref:System.Windows.Forms.ToolStripDropDownMenu> и <xref:System.Windows.Forms.ContextMenuStrip> для управления специальным выделением, макетом и упорядочением столбцов для меню.

### <a name="toolstripdropdownbutton"></a>тулстрипдропдовнбуттон

<xref:System.Windows.Forms.ToolStripDropDownButton>выглядит, <xref:System.Windows.Forms.ToolStripButton>как, но отображается раскрывающийся список, когда пользователь щелкает его. Скройте или отобразите стрелку раскрывающегося списка, задав <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> свойство. <xref:System.Windows.Forms.ToolStripDropDownButton>размещает <xref:System.Windows.Forms.ToolStripOverflowButton> объект, отображающий элементы, <xref:System.Windows.Forms.ToolStrip>которые переполняют.

### <a name="toolstripsplitbutton"></a>тулстрипсплитбуттон

<xref:System.Windows.Forms.ToolStripSplitButton>объединяет функциональные возможности кнопки и кнопки с раскрывающимся списком.

Используйте свойство, чтобы синхронизировать событие выбранного раскрывающегося элемента с элементом, показанным на кнопке. <xref:System.Windows.Forms.Control.Click> <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A>

### <a name="toolstripitem-generic-features"></a>Обобщенные функции ToolStripItem

<xref:System.Windows.Forms.ToolStripItem>предоставляет следующие общие функции и параметры для наследования элементов управления.

- Основные события

- Обработка изображений

- Выравнивание

- Связь Text and Image

- Стиль экрана

#### <a name="core-events"></a>Основные события

<xref:System.Windows.Forms.ToolStripItem>элементы управления получают собственные события щелчка, мыши и рисования, а также могут выполнять некоторую предварительную обработку клавиатуры.

#### <a name="image-handling"></a>Обработка изображений

<xref:System.Windows.Forms.ToolStripItem.Image%2A>Свойства ,<xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> ,,<xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> и относятся к различным аспектам обработки изображений. <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A> <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A> Используйте изображения в <xref:System.Windows.Forms.ToolStrip> элементах управления, задав эти свойства напрямую или задав <xref:System.Windows.Forms.ToolStrip.ImageList%2A> свойство времени выполнения.

Масштабирование изображений определяется взаимодействием свойств как <xref:System.Windows.Forms.ToolStrip> в, так и <xref:System.Windows.Forms.ToolStripItem>следующим образом.

- <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A>— Это масштаб окончательного изображения, определяемый сочетанием <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> параметров изображения и <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> параметра контейнера.

  - Если <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> параметр `true` имеет значение (по умолчанию <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>) и <xref:System.Windows.Forms.ToolStripItemImageScaling> имеет значение, масштабирование изображения <xref:System.Windows.Forms.ToolStrip> не происходит, а размер равен размеру самого крупного элемента или предписанному минимальному размеру.

  - Если <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> имеет `false` значение и<xref:System.Windows.Forms.ToolStripItemImageScaling> имеет <xref:System.Windows.Forms.ToolStrip> значение <xref:System.Windows.Forms.ToolStripItemImageScaling.None>, то не происходит ни изображение, ни масштабирование.

#### <a name="alignment"></a>Выравнивание

Значение <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> свойства определяет конец элемента, <xref:System.Windows.Forms.ToolStrip> на котором отображается элемент. Свойство работает, только если в качестве стиля <xref:System.Windows.Forms.ToolStrip> макета для задано одно из значений переполнения стека. <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>

Элементы помещаются <xref:System.Windows.Forms.ToolStrip> в в порядке, в котором элементы отображаются в коллекции Items. Чтобы программно изменить место расположения элемента, используйте <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> метод для перемещения элемента в коллекции. Этот метод перемещает элемент, но не дублирует его.

#### <a name="text-and-image-relationship"></a>Связь Text and Image

Свойство определяет относительное расположение изображения по отношению к тексту <xref:System.Windows.Forms.ToolStripItem>в. <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> Элементы, в которых отсутствует изображение, текст или и то, и другое, обрабатываются <xref:System.Windows.Forms.ToolStripItem> как особые случаи, в которых не отображается пустое место для отсутствующих элементов или элементов.

#### <a name="display-style"></a>Стиль экрана

<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>позволяет задать значения свойств Text и Image элемента, выполняя отображение только нужных значений. Обычно это используется для изменения только стиля отображения при отображении одного и того же элемента в другом контексте.

## <a name="accessory-classes"></a>Классы аксессуаров

Ниже перечислены классы, предоставляющие различные другие функции.

- <xref:System.Windows.Forms.ToolStripManager>поддерживает <xref:System.Windows.Forms.ToolStrip>задачи, связанные со всеми приложениями, такие как объединение, параметры и параметры модуля подготовки отчетов.

- <xref:System.Windows.Forms.ToolStripRenderer>позволяет <xref:System.Windows.Forms.ToolStrip> легко применять определенный стиль или тему.

- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>создает перья и кисти на основе заменяемой таблицы цветов (<xref:System.Windows.Forms.ProfessionalColorTable>).

- <xref:System.Windows.Forms.ToolStripSystemRenderer>применяет системные цвета и плоский визуальный <xref:System.Windows.Forms.ToolStrip> стиль к приложениям.

- <xref:System.Windows.Forms.ToolStripContainer>Аналогично <xref:System.Windows.Forms.SplitContainer>. Для создания типичной схемы используется четыре закрепленных боковых панели (экземпляры <xref:System.Windows.Forms.ToolStripPanel>) и одна центральная панель ( <xref:System.Windows.Forms.ToolStripContentPanel>экземпляр). Боковые панели нельзя удалить, но их можно скрыть. Вы не можете ни удалить, ни скрыть центральную панель. Можно разместить один или несколько <xref:System.Windows.Forms.ToolStrip>элементов управления, <xref:System.Windows.Forms.MenuStrip>или <xref:System.Windows.Forms.StatusStrip> на боковых панелях, а также использовать центральную панель для других элементов управления. Кроме <xref:System.Windows.Forms.ToolStripContentPanel> того, позволяет получить поддержку модуля подготовки отчетов в тексте формы для согласованного внешнего вида. <xref:System.Windows.Forms.ToolStripContainer>не поддерживает многодокументный интерфейс (MDI).

- <xref:System.Windows.Forms.ToolStripPanel>предоставляет пространство для перемещения и упорядочения <xref:System.Windows.Forms.ToolStrip> элементов управления. Вы можете использовать только одну панель, если это необходимо, и <xref:System.Windows.Forms.ToolStripPanel> хорошо работает в сценариях MDI.

## <a name="see-also"></a>См. также

- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Технологии, положенные в основу работы элемента управления ToolStrip](toolstrip-technology-summary.md)
- [Элемент управления ToolStrip](toolstrip-control-windows-forms.md)
- [Элемент управления MenuStrip](menustrip-control-windows-forms.md)
- [Элемент управления StatusStrip](statusstrip-control.md)
- [Элемент управления ContextMenuStrip](contextmenustrip-control.md)
- [Элемент управления BindingNavigator](bindingnavigator-control-windows-forms.md)
