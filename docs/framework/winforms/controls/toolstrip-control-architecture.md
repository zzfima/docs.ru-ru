---
title: "Архитектура элемента управления ToolStrip | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolStrip - элемент управления [Windows Forms], архитектура"
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# Архитектура элемента управления ToolStrip
Классы <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.ToolStripItem> предоставляют гибкую, расширяемую систему для отображения пунктов меню, панели инструментов и строки состояния.  Все эти классы содержатся в пространстве имен <xref:System.Windows.Forms> и обычно именуются с префиксом "ToolStrip" \(например, <xref:System.Windows.Forms.ToolStripOverflow>\) или суффиксом "Strip" \(например, <xref:System.Windows.Forms.MenuStrip>\).  
  
## ToolStrip  
 В следующих разделах описывается <xref:System.Windows.Forms.ToolStrip> и производные от него элементы управления.  
  
 <xref:System.Windows.Forms.ToolStrip> является абстрактным базовым классом для <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip> и <xref:System.Windows.Forms.ContextMenuStrip>.  В следующей объектной модели показана иерархия наследования <xref:System.Windows.Forms.ToolStrip>.  
  
 ![Модель объекта ToolStrip](../../../../docs/framework/winforms/controls/media/toolstripobjectmodel.png "ToolStripObjectModel")  
Модель объекта ToolStrip  
  
 Можно получить доступ ко всем элементам <xref:System.Windows.Forms.ToolStrip> с помощью коллекции <xref:System.Windows.Forms.ToolStrip.Items%2A>.  Можно получить доступ ко всем элементам <xref:System.Windows.Forms.ToolStripDropDownItem> с помощью коллекции <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A>.  В классе, производном от <xref:System.Windows.Forms.ToolStrip>, свойство <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> можно использовать только для доступа к элементам, отображаемым в данный момент.  Это элементы, которые не находятся в настоящий момент в меню переполнения.  
  
 Следующие элементы специально предназначены для универсального применения с объектами <xref:System.Windows.Forms.ToolStripSystemRenderer> и <xref:System.Windows.Forms.ToolStripProfessionalRenderer> во всех ориентациях.  По умолчанию они доступны во время разработки для элемента управления <xref:System.Windows.Forms.ToolStrip>:  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### MenuStrip  
 <xref:System.Windows.Forms.MenuStrip> является контейнером верхнего уровня, замещающим <xref:System.Windows.Forms.MainMenu>.  Он также предоставляет возможности управления ключами и возможности интерфейса MDI.  Функционально <xref:System.Windows.Forms.ToolStripDropDownItem> и <xref:System.Windows.Forms.ToolStripMenuItem> работают вместе с <xref:System.Windows.Forms.MenuStrip>, несмотря на то, что являются производными от <xref:System.Windows.Forms.ToolStripItem>.  
  
 Следующие элементы специально предназначены для универсального применения с объектами <xref:System.Windows.Forms.ToolStripSystemRenderer> и <xref:System.Windows.Forms.ToolStripProfessionalRenderer> во всех ориентациях.  По умолчанию они доступны во время разработки для элемента управления <xref:System.Windows.Forms.MenuStrip>:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### StatusStrip  
 <xref:System.Windows.Forms.StatusStrip> заменяет элемент управления <xref:System.Windows.Forms.StatusBar>.  Специальные возможности <xref:System.Windows.Forms.StatusStrip> включают пользовательскую структуру таблицы, поддержку изменения размера формы и перемещения захватов, а также свойство `Spring` позволяющее <xref:System.Windows.Forms.ToolStripStatusLabel> автоматически заполнять доступное место.  
  
 Следующие элементы специально предназначены для универсального применения с объектами <xref:System.Windows.Forms.ToolStripSystemRenderer> и <xref:System.Windows.Forms.ToolStripProfessionalRenderer> во всех ориентациях.  По умолчанию они доступны во время разработки для элемента управления <xref:System.Windows.Forms.StatusStrip>:  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### ContextMenuStrip  
 Объект <xref:System.Windows.Forms.ContextMenuStrip> заменяет <xref:System.Windows.Forms.ContextMenu>.  <xref:System.Windows.Forms.ContextMenuStrip> можно привязать к любому элементу управления. Щелчок правой кнопкой мыши будет автоматически выводить на экран всплывающее меню \(или контекстное меню\).  Объект <xref:System.Windows.Forms.ContextMenuStrip> можно отобразить программным путем с помощью метода <xref:System.Windows.Forms.ToolStripDropDown.Show%2A>.  <xref:System.Windows.Forms.ContextMenuStrip> поддерживает события <xref:System.Windows.Forms.ToolStripDropDown.Opening> и <xref:System.Windows.Forms.ToolStripDropDown.Closing> с возможностью отмены, чтобы обрабатывать динамическое заполнение и ситуации с несколькими щелчками.  <xref:System.Windows.Forms.ContextMenuStrip> поддерживает изображения, установку флажков для элементов меню, текст, клавиши доступа, сочетания клавиш и вложенные меню.  
  
 Следующие элементы специально предназначены для универсального применения с объектами <xref:System.Windows.Forms.ToolStripSystemRenderer> и <xref:System.Windows.Forms.ToolStripProfessionalRenderer> во всех ориентациях.  По умолчанию они доступны во время разработки для элемента управления <xref:System.Windows.Forms.ContextMenuStrip>:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### Общие возможности ToolStrip  
 В следующих разделах описываются возможности и поведение, являющиеся общими для <xref:System.Windows.Forms.ToolStrip> и производных элементов управления.  
  
#### Рисование  
 Пользовательское рисование в элементе управления <xref:System.Windows.Forms.ToolStrip> можно выполнять несколькими способами.  Как и другие элементы управления Windows Forms, <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.ToolStripItem> обладают переопределяемыми методами `OnPaint` и событиями `Paint`.  Как и в стандартной отрисовке, система координат привязана к клиентской области элемента управления, и началом координат \(0, 0\) служит левый верхний угол элемента управления.  Событие `Paint` и метод `OnPaint` для элементов <xref:System.Windows.Forms.ToolStripItem> работают аналогично другим событиям отрисовки элементов управления.  
  
 Элемент управления <xref:System.Windows.Forms.ToolStrip> также предоставляет более подробный доступ к отрисовке элементов и контейнера с помощью класса <xref:System.Windows.Forms.ToolStripRenderer>, который обеспечивает переопределяемые методы рисования фона, фона элемента, изображения элемента, стрелки элемента, текста элемента и границы <xref:System.Windows.Forms.ToolStrip>.  Аргументы события таких методов предоставляют доступ к ряду свойств, таких как прямоугольники, цвета и текстовые форматы, которые можно настраивать нужным образом.  
  
 Чтобы настроить только некоторые аспекты рисования элемента, обычно переопределяется класс <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Если при написании нового элемента требуется управление всеми аспектами рисования, можно переопределить метод `OnPaint`.  В методе `OnPaint` можно использовать методы из класса <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Для <xref:System.Windows.Forms.ToolStrip> по умолчанию включена двойная буферизация для получения всех преимуществ параметра <xref:System.Windows.Forms.ControlStyles>.  
  
#### Родительские связи  
 Понятия родительских связей и владения контейнером в элементах управления <xref:System.Windows.Forms.ToolStrip> более сложны, чем в других элементах управления контейнером Windows Forms.  Это требуется для поддержки динамических сценариев, например переполнения, совместного использования раскрывающихся элементов несколькими элементами <xref:System.Windows.Forms.ToolStrip> и поддержки генерации <xref:System.Windows.Forms.ContextMenuStrip> из элемента управления.  
  
 В следующем списке приводится описание членов, связанных родительскими связями, с объяснением их использования.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A> осуществляет доступ к элементу, который является источником раскрывающегося элемента.  Это похоже на <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, но вместо элемента управления возвращается <xref:System.Windows.Forms.ToolStripItem>.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> определяет, какой из элементов управления является источником для <xref:System.Windows.Forms.ContextMenuStrip> при совместном использовании <xref:System.Windows.Forms.ContextMenuStrip> несколькими элементами управления.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A> является методом доступа только для чтения к свойству <xref:System.Windows.Forms.ToolStripItem.Parent%2A>.  Родительский элемент отличается от владельца тем, что родительский элемент обозначает возвращенный текущий <xref:System.Windows.Forms.ToolStrip>, в котором отображается элемент \(это может производиться в области переполнения\).  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A> возвращает <xref:System.Windows.Forms.ToolStrip>, коллекция элементов которого содержит текущий <xref:System.Windows.Forms.ToolStripItem>.  Это лучший способ создания ссылки на <xref:System.Windows.Forms.ToolStrip.ImageList%2A> или на другие свойства в <xref:System.Windows.Forms.ToolStrip> верхнего уровня, не требующий написания специальных кодов обработки переполнения.  
  
#### Поведение унаследованных элементов управления  
 Следующие элементы управления блокируются при каждом использовании в наследовании:  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel> содержит в <xref:System.Windows.Forms.ToolStripContainer> панели, а также отдельные элементы управления <xref:System.Windows.Forms.ToolStripPanel>.  
  
 Например, создайте новое приложение Windows Forms, используя один или несколько элементов управления из приведенного выше списка.  Задайте `public` или `protected` в качестве значения модификатора доступа одного или нескольких элементов управления, затем выполните построение проекта.  Добавьте форму, наследуемую из первой формы, затем выберите наследуемый элемент управления.  Элемент управления станет заблокированным, как если бы модификатору доступа было установлено значение `private`.  
  
#### Поддержка наследования ToolStripContainer  
 Элемент управления <xref:System.Windows.Forms.ToolStripContainer> поддерживает ограниченные сценарии наследования, подобные приведенным в следующем примере:  
  
1.  Создание нового приложения Windows Forms.  
  
2.  Добавьте элемент <xref:System.Windows.Forms.ToolStripContainer> в форму.  
  
3.  Задайте для модификатора доступа к <xref:System.Windows.Forms.ToolStripContainer> значение `public` или `protected`.  
  
4.  Добавьте любую комбинацию элементов управления <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> в области <xref:System.Windows.Forms.ToolStripPanel> для <xref:System.Windows.Forms.ToolStripContainer>.  
  
5.  Выполните построение проекта.  
  
6.  Добавьте форму, которая наследуется из первой формы.  
  
7.  Выберите унаследованный <xref:System.Windows.Forms.ToolStripContainer> в форме.  
  
#### Унаследованное поведение дочерних элементов управления  
 После выполнения предыдущих шагов будет наблюдаться следующее унаследованное поведение:  
  
-   Элемент управления появится в конструкторе с унаследованным значком.  
  
-   Элементы управления <xref:System.Windows.Forms.ToolStripPanel> блокируются, выбирать или изменять порядок их содержимого невозможно.  
  
-   Можно добавлять элементы управления к <xref:System.Windows.Forms.ToolStripContentPanel>, перемещать элементы управления и делать их дочерними элементами управления элемента <xref:System.Windows.Forms.ToolStripContentPanel>.  
  
-   Изменения сохранятся после сборки формы.  
  
    > [!NOTE]
    >  Удалите модификатор доступа из всех элементов управления <xref:System.Windows.Forms.ToolStripPanel>, являющихся частью <xref:System.Windows.Forms.ToolStripContainer>.  Модификатор доступа к <xref:System.Windows.Forms.ToolStripContainer> управляет всем элементом управления.  
  
#### Частичное доверие  
 Ограничения `ToolStrip` при частичном доверии позволяют предотвратить случайный ввод личных сведений, которые могут быть использованы неавторизованными пользователями или службами.  Используются следующие защитные меры:  
  
-   Элементам управления `ToolStripDropDown` требуется <xref:System.Security.Permissions.UIPermissionWindow> для отображения элементов в <xref:System.Windows.Forms.ToolStripControlHost>.  Это относится как ко встроенным элементам управления, например, <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox> и <xref:System.Windows.Forms.ToolStripProgressBar>, так и к элементам управления, созданным пользователем.  Если данное требование не удовлетворяется, эти элементы не отображаются.  Исключение не создается.  
  
-   Задание свойству <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> значения `false` не разрешается, а отменяемый параметр события <xref:System.Windows.Forms.ToolStripDropDown.Closing> игнорируется.  Это не позволяет вводить более одного нажатия клавиш без отключения раскрывающегося элемента.  Если данное требование не удовлетворяется, такие элементы не отображаются.  Исключение не создается.  
  
-   Многие элементы обработки нажатий клавиш не вызываются, если они появляются в контексте с частичным доверием, отличном от <xref:System.Security.Permissions.UIPermissionWindow>.  
  
-   Клавиши доступа не обрабатываются, если не получено <xref:System.Security.Permissions.UIPermissionWindow>.  
  
#### Использование  
 Следующие шаблоны использования влияют на структуру <xref:System.Windows.Forms.ToolStrip>, взаимодействие с клавиатурой и пользовательское поведение:  
  
-   Объединение в <xref:System.Windows.Forms.ToolStripPanel>  
  
     Положение <xref:System.Windows.Forms.ToolStrip> можно изменять внутри <xref:System.Windows.Forms.ToolStripPanel> и между панелями <xref:System.Windows.Forms.ToolStripPanel>.  Свойство `Dock` игнорируется, а если свойство <xref:System.Windows.Forms.ToolStrip.Stretch%2A> равняется `false`, размер <xref:System.Windows.Forms.ToolStrip> увеличивается по мере добавления элементов на <xref:System.Windows.Forms.ToolStripPanel>.  Обычно <xref:System.Windows.Forms.ToolStrip> не участвует в последовательности перехода.  
  
-   Закрепление  
  
     <xref:System.Windows.Forms.ToolStrip> помещается с одной стороны контейнера в фиксированном положении, а его размер увеличивается по всему краю закрепления.  Обычно <xref:System.Windows.Forms.ToolStrip> не участвует в последовательности перехода.  
  
-   Абсолютное положение  
  
     <xref:System.Windows.Forms.ToolStrip> аналогичен другим элементам управления. При размещении свойством <xref:System.Windows.Forms.Control.Location%2A> он приобретает фиксированный размер и обычно участвует в последовательности перехода.  
  
#### Взаимодействие с клавиатурой  
  
##### Клавиши доступа  
 Сочетания клавиш позволяют активировать элемент управления с клавиатуры нажатием вместе с клавишей ALT или после нее.  <xref:System.Windows.Forms.ToolStrip> поддерживает как явные, так и неявные сочетания клавиш.  Явное определение использует символ амперсанда \(&\) перед буквой.  Неявное определение использует алгоритм, который пытается найти соответствующий элемент на основании порядка символов в данном свойстве `Text`.  
  
##### Сочетания клавиш  
 Для определения сочетания клавиш, используемого <xref:System.Windows.Forms.MenuStrip>, применяется комбинация перечисления <xref:System.Windows.Forms.Keys> \(не зависящая от порядка\).  Также можно использовать свойство <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> для отображения сочетания клавиш только с текстом, например, для отображения "Del" вместо "Delete".  
  
##### Навигация  
 Клавиша ALT активирует <xref:System.Windows.Forms.MenuStrip> на который указывает <xref:System.Windows.Forms.Form.MainMenuStrip%2A>.  Затем сочетание клавиш CTRL\+TAB используется для перехода между элементами управления <xref:System.Windows.Forms.ToolStrip> внутри `ToolStripPanel`.  Клавиша TAB и клавиши со стрелками на цифровой клавиатуре используются для перехода между элементами в <xref:System.Windows.Forms.ToolStrip>.  Специальный алгоритм обрабатывает навигацию в области переполнения.  Пробел используется для выбора <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton> или <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
##### Фокус и проверки  
 При активации клавишей ALT, <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.ToolStrip> обычно не переключает фокус с элемента управления, на котором в данный момент находится фокус.  Если имеется элемент управления, размещенный в <xref:System.Windows.Forms.MenuStrip> или в раскрывающемся элементе <xref:System.Windows.Forms.MenuStrip>, то фокус переходит на элемент управления, когда пользователь нажимает клавишу TAB.  В общем случае события <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter> и <xref:System.Windows.Forms.Control.Leave>, относящиеся к <xref:System.Windows.Forms.MenuStrip>, могут быть не вызваны при активации с клавиатуры.  В таких случаях вместо них следует использовать события <xref:System.Windows.Forms.MenuStrip.MenuActivate> и <xref:System.Windows.Forms.MenuStrip.MenuDeactivate>.  
  
 По умолчанию параметр <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> имеет значение `false`.  Чтобы выполнить проверку, явно вызовите <xref:System.Windows.Forms.ContainerControl.Validate%2A> на форме.  
  
#### Макет  
 Чтобы управлять структурой <xref:System.Windows.Forms.ToolStrip>, выберите один из членов <xref:System.Windows.Forms.ToolStripLayoutStyle> со свойством <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>.  
  
##### Макеты "Стопка"  
 Размещение в стопку — это расположение элементов рядом друг с другом между концами <xref:System.Windows.Forms.ToolStrip>.  В следующем списке описываются типы размещения в стопку.  
  
-   По умолчанию — <xref:System.Windows.Forms.ToolStripLayoutStyle>.  Эта настройка приводит к автоматическому изменению макета <xref:System.Windows.Forms.ToolStrip> в соответствии со свойством <xref:System.Windows.Forms.ToolStrip.Orientation%2A> для обработки скриптов перетаскивания и закрепления.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle> отображает элементы <xref:System.Windows.Forms.ToolStrip> по вертикали рядом друг с другом.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle> отображает элементы <xref:System.Windows.Forms.ToolStrip> по горизонтали рядом друг с другом.  
  
##### Другие функции макетов "стопка"  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> определяет конец объекта <xref:System.Windows.Forms.ToolStrip>, по которому выравнивается элемент.  
  
 Если элементы не помещаются внутри <xref:System.Windows.Forms.ToolStrip>, автоматически появляется кнопка переполнения.  Значение свойства <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> определяет, отображается ли элемент в области переполнения при необходимости.  
  
 В событии <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> можно проверить свойство <xref:System.Windows.Forms.ToolStripItem.Placement%2A>, чтобы определить, расположен элемент в основном <xref:System.Windows.Forms.ToolStrip>, в области переполнения <xref:System.Windows.Forms.ToolStrip>, или не отображается в данный момент.  Обычно элемент может не отображаться, если он не помещается в основном <xref:System.Windows.Forms.ToolStrip> и его свойству <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> было задано значение <xref:System.Windows.Forms.ToolStripItemOverflow>.  
  
 Сделайте <xref:System.Windows.Forms.ToolStrip> перемещаемым, поместив в <xref:System.Windows.Forms.ToolStripPanel> и задав его <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> значение <xref:System.Windows.Forms.ToolStripGripStyle>.  
  
##### Другие параметры макетов  
 Другими параметрами макетов являются <xref:System.Windows.Forms.ToolStripLayoutStyle> и <xref:System.Windows.Forms.ToolStripLayoutStyle>.  
  
##### Последовательное размещение  
 Макет <xref:System.Windows.Forms.ToolStripLayoutStyle> является макетом по умолчанию для <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> и <xref:System.Windows.Forms.ToolStripOverflow>.  Такой макет аналогичен <xref:System.Windows.Forms.FlowLayoutPanel>.  Возможности макета <xref:System.Windows.Forms.ToolStripLayoutStyle> приведены ниже:  
  
-   Все возможности <xref:System.Windows.Forms.FlowLayoutPanel> предоставляются свойством <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>.  Класс <xref:System.Windows.Forms.LayoutSettings> необходимо привести к классу <xref:System.Windows.Forms.FlowLayoutSettings>.  
  
-   Свойства <xref:System.Windows.Forms.ToolStripItem.Dock%2A> и <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> можно использовать в коде для выравнивания элементов внутри строки.  
  
-   Свойство <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> игнорируется.  
  
-   В событии <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> можно проверить свойство <xref:System.Windows.Forms.ToolStripItem.Placement%2A>, чтобы определить, был элемент расположен в основном <xref:System.Windows.Forms.ToolStrip> или не поместился.  
  
-   Захват не отображается, и поэтому расположение <xref:System.Windows.Forms.ToolStrip> в стиле макета <xref:System.Windows.Forms.ToolStripLayoutStyle> в <xref:System.Windows.Forms.ToolStripPanel> нельзя изменить.  
  
-   Кнопка переполнения <xref:System.Windows.Forms.ToolStrip> не отображается, а <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> игнорируется.  
  
##### Табличный макет  
 Макет <xref:System.Windows.Forms.ToolStripLayoutStyle> является макетом по умолчанию для <xref:System.Windows.Forms.StatusStrip>.  Он аналогичен <xref:System.Windows.Forms.TableLayoutPanel>.  Возможности макета <xref:System.Windows.Forms.ToolStripLayoutStyle> приведены ниже:  
  
-   Все возможности <xref:System.Windows.Forms.TableLayoutPanel> предоставляются свойством <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>.  Класс <xref:System.Windows.Forms.LayoutSettings> необходимо привести к классу <xref:System.Windows.Forms.TableLayoutSettings>.  
  
-   Свойства <xref:System.Windows.Forms.ToolStripItem.Dock%2A> и <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> можно использовать в коде для выравнивания элементов пределах ячейки таблицы.  
  
-   Свойство <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> игнорируется.  
  
-   В событии <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> можно проверить свойство <xref:System.Windows.Forms.ToolStripItem.Placement%2A>, чтобы определить, был элемент расположен в основном <xref:System.Windows.Forms.ToolStrip> или не поместился.  
  
-   Захват не отображается, и поэтому расположение <xref:System.Windows.Forms.ToolStrip> в стиле структуры <xref:System.Windows.Forms.ToolStripLayoutStyle> в <xref:System.Windows.Forms.ToolStripPanel> нельзя изменить.  
  
-   Кнопка переполнения <xref:System.Windows.Forms.ToolStrip> не отображается, а <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> игнорируется.  
  
## Элемент ToolStrip  
 В следующих разделах описывается <xref:System.Windows.Forms.ToolStripItem> и производные от него элементы управления.  
  
 <xref:System.Windows.Forms.ToolStripItem> является абстрактным базовым классом для всех элементов, входящих в <xref:System.Windows.Forms.ToolStrip>.  В следующей объектной модели показана иерархия наследования <xref:System.Windows.Forms.ToolStripItem>.  
  
 ![Модель объекта ToolStripItem](../../../../docs/framework/winforms/controls/media/toolstripitemobjectmodel.png "ToolStripItemObjectModel")  
Модель объекта ToolStripItem  
  
 Классы <xref:System.Windows.Forms.ToolStripItem> наследуются напрямую из <xref:System.Windows.Forms.ToolStripItem>, или косвенно из <xref:System.Windows.Forms.ToolStripItem> с помощью <xref:System.Windows.Forms.ToolStripControlHost> или <xref:System.Windows.Forms.ToolStripDropDownItem>.  
  
 Элементы управления <xref:System.Windows.Forms.ToolStripItem> должны содержаться в <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip> или <xref:System.Windows.Forms.ContextMenuStrip>, они не могут добавляться в форму напрямую.  Различные классы контейнеров предназначены для хранения соответствующего подмножества элементов управления <xref:System.Windows.Forms.ToolStripItem>.  
  
 В следующей таблице перечислены элементы управления хранением <xref:System.Windows.Forms.ToolStripItem> и контейнеры, лучше всего подходящие для их отображения.  Хотя любой элемент <xref:System.Windows.Forms.ToolStrip> может размещаться в любом контейнере, производном от <xref:System.Windows.Forms.ToolStrip>, внешний вид этих элементов был разработан для использования со следующими контейнерами:  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown> не отображается в панели инструментов конструктора.  
  
|Элемент в контейнере|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|  
|--------------------------|---------------|---------------|----------------------|-----------------|-----------------------|  
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
  
### ToolStripButton  
 <xref:System.Windows.Forms.ToolStripButton> является элементом кнопки для <xref:System.Windows.Forms.ToolStrip>.  Этот элемент можно отображать с различными стилями границы и использовать для представления и активирования рабочих состояний.  Также можно определить наличие фокуса на этом элементе по умолчанию.  
  
### ToolStripLabel  
 <xref:System.Windows.Forms.ToolStripLabel> обеспечивает функциональные возможности метки в элементах управления <xref:System.Windows.Forms.ToolStrip>.  <xref:System.Windows.Forms.ToolStripLabel>, как и <xref:System.Windows.Forms.ToolStripButton>, не получает фокус по умолчанию и не отображается в нажатом или выделенном состоянии.  
  
 <xref:System.Windows.Forms.ToolStripLabel> поддерживает клавиши доступа, как размещенный элемент.  
  
 Используйте свойства <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> и <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> на <xref:System.Windows.Forms.ToolStripLabel>, чтобы обеспечить поддержку элемента управления ссылки в <xref:System.Windows.Forms.ToolStrip>.  
  
### ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel> является версией <xref:System.Windows.Forms.ToolStripLabel>, созданной специально для использования в <xref:System.Windows.Forms.StatusStrip>.  Специальные возможности включают <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A> и <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
### ToolStripSeparator  
 <xref:System.Windows.Forms.ToolStripSeparator> добавляет в панель инструментов или в меню вертикальную или горизонтальную линию в зависимости от ориентации.  Такая линия обеспечивает группирование или разделение элементов, например пунктов меню.  
  
 Можно добавить <xref:System.Windows.Forms.ToolStripSeparator> во время разработки, выбрав из раскрывающегося списка.  Однако, <xref:System.Windows.Forms.ToolStripSeparator> также можно создать, введя дефис \(\-\) в узел шаблона конструктора или в метод <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A>.  
  
### ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost> является абстрактным базовым классом для <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox> и <xref:System.Windows.Forms.ToolStripProgressBar>.  Другие элементы управления, включая пользовательские элементы управления, можно разместить в <xref:System.Windows.Forms.ToolStripControlHost> двумя способами:  
  
-   Создайте <xref:System.Windows.Forms.ToolStripControlHost> с помощью класса, производного от <xref:System.Windows.Forms.Control>.  Чтобы получить полный доступ к размещенным элементу управления и свойствам, свойство <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> необходимо привести обратно к реальному классу, который оно представляет.  
  
-   Создайте расширение <xref:System.Windows.Forms.ToolStripControlHost> и в конструкторе унаследованного класса по умолчанию вызовите конструктор базового класса, передающий класс, который является производным от <xref:System.Windows.Forms.Control>.  Эта функция позволяет включить общие методы и свойства элементов управления в <xref:System.Windows.Forms.ToolStrip> для облегчения доступа.  
  
### ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox> является <xref:System.Windows.Forms.ComboBox>, оптимизированным для размещения в <xref:System.Windows.Forms.ToolStrip>.  Подмножество свойств и событий размещаемого элемента управления представляется на уровне <xref:System.Windows.Forms.ToolStripComboBox>, однако полный доступ к лежащему в основе элементу управления <xref:System.Windows.Forms.ComboBox> осуществляется с помощью свойства <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A>.  
  
### ToolStripTextBox  
 <xref:System.Windows.Forms.ToolStripTextBox> является <xref:System.Windows.Forms.TextBox>, оптимизированным для размещения в <xref:System.Windows.Forms.ToolStrip>.  Подмножество свойств и событий размещаемого элемента управления представляется на уровне <xref:System.Windows.Forms.ToolStripTextBox>, однако полный доступ к лежащему в основе элементу управления <xref:System.Windows.Forms.TextBox> осуществляется с помощью свойства <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A>.  
  
### ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar> является <xref:System.Windows.Forms.ProgressBar>, оптимизированным для размещения в <xref:System.Windows.Forms.ToolStrip>.  Подмножество свойств и событий размещаемого элемента управления представляется на уровне <xref:System.Windows.Forms.ToolStripProgressBar>, однако полный доступ к лежащему в основе элементу управления <xref:System.Windows.Forms.ProgressBar> осуществляется с помощью свойства <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A>.  
  
### ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem> является абстрактным базовым классом для <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton> и <xref:System.Windows.Forms.ToolStripSplitButton>, в котором можно разместить элементы напрямую или разместить дополнительные элементы в раскрывающемся контейнере.  Это можно сделать, задав свойству <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> значение <xref:System.Windows.Forms.ToolStripDropDown> и свойству <xref:System.Windows.Forms.ToolStrip.Items%2A> значение <xref:System.Windows.Forms.ToolStripDropDown>.  Доступ к этим раскрывающимся элементам осуществляется непосредственно через свойство <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A>.  
  
### ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem> является <xref:System.Windows.Forms.ToolStripDropDownItem>, работающим с <xref:System.Windows.Forms.ToolStripDropDownMenu> и <xref:System.Windows.Forms.ContextMenuStrip> для обработки специального выделения, структуры и расположения столбцов в меню.  
  
### ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton> выглядит аналогично <xref:System.Windows.Forms.ToolStripButton>, но отображает раскрывающуюся область, когда пользователь щелкает по нему.  Скрыть или показать стрелку раскрывающегося списка можно с помощью свойства <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A>.  В элементе <xref:System.Windows.Forms.ToolStripDropDownButton> размещается кнопка <xref:System.Windows.Forms.ToolStripOverflowButton>, отображающая элементы, выходящие за пределы <xref:System.Windows.Forms.ToolStrip>.  
  
### ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton> сочетает функциональные возможности обычной кнопки и кнопки раскрывающегося списка.  
  
 Для синхронизации события <xref:System.Windows.Forms.Control.Click> выбранного раскрывающегося элемента с изображенным на кнопке элементом используйте свойство <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A>.  
  
### Общие возможности ToolStripItem  
 <xref:System.Windows.Forms.ToolStripItem> предоставляет наследующим элементам управления следующие общие возможности и параметры:  
  
-   Основные события  
  
-   Обработка изображений  
  
-   Выравнивание  
  
-   Связь текста и изображений  
  
-   Стиль отображения  
  
#### Основные события  
 Элементы управления <xref:System.Windows.Forms.ToolStripItem> получают собственные события нажатия кнопки, мыши и рисования, а также могут выполнять предварительную обработку клавиатуры.  
  
#### Обработка изображений  
 Свойства <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A> и <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> относятся к различным аспектам обработки изображений.  Чтобы использовать изображения в элементах управления <xref:System.Windows.Forms.ToolStrip>, напрямую задайте эти свойства или задайте свойство <xref:System.Windows.Forms.ToolStrip.ImageList%2A> во время выполнения.  
  
 Масштабирование изображения определяется взаимодействием свойств в <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.ToolStripItem> следующим образом:  
  
-   Масштаб <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A> конечного изображения определяется сочетанием параметра изображения <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> и параметра контейнера <xref:System.Windows.Forms.ToolStrip.AutoSize%2A>.  
  
    -   Если <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> задано значение `true` \(значение по умолчанию\), а <xref:System.Windows.Forms.ToolStripItemImageScaling> задано значение <xref:System.Windows.Forms.ToolStripItemImageScaling>, то масштабирование производиться не будет, а размером <xref:System.Windows.Forms.ToolStrip> будет размер самого большого элемента или предписанный минимальный размер.  
  
    -   Если <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> задано значение `false`, а <xref:System.Windows.Forms.ToolStripItemImageScaling> задано значение <xref:System.Windows.Forms.ToolStripItemImageScaling>, то масштабирование ни изображения, ни <xref:System.Windows.Forms.ToolStrip> производиться не будет.  
  
#### Выравнивание  
 Значение свойства <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> определяет конец объекта <xref:System.Windows.Forms.ToolStrip> около которого отображается элемент.  Свойство <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> работает только тогда, когда в качестве значения стиля структуры <xref:System.Windows.Forms.ToolStrip> задано одно из значений переполнения стека.  
  
 Элементы размещаются на <xref:System.Windows.Forms.ToolStrip> в порядке своего появления коллекции элементов.  Чтобы изменить расположение элемента программным способом, переместите элемент внутри коллекции, используя метод <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A>.  Указанный метод перемещает элемент, но не дублирует его.  
  
#### Связь текста и изображений  
 Свойство <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> определяет относительное расположение изображения относительно текста на <xref:System.Windows.Forms.ToolStripItem>.  Элементы, в которых отсутствует текст, изображение или и то и другое, рассматриваются как особые случаи, чтобы <xref:System.Windows.Forms.ToolStripItem> не отображал пустую область на месте отсутствующего элемента или элементов.  
  
#### Стиль отображения  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> позволяет задать значения свойств текста и изображения элемента. При этом отображаются только требуемые элементы.  Эта возможность обычно используется для изменения только стиля отображения при выводе того же элемента на экран в другом контексте.  
  
## Вспомогательные классы  
 Следующие классы предоставляют различные дополнительные функциональные возможности:  
  
-   <xref:System.Windows.Forms.ToolStripManager> поддерживает задачи, связанные с <xref:System.Windows.Forms.ToolStrip> всего приложения, например определение параметров слияния, настроек и отображения.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> позволяет применить к <xref:System.Windows.Forms.ToolStrip> определенный стиль или тему.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> создает перья и кисти на основании заменяемой таблицы цветов \(<xref:System.Windows.Forms.ProfessionalColorTable>\).  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> применяет системные цвета и плоский визуальный стиль к приложениям <xref:System.Windows.Forms.ToolStrip>.  
  
-   <xref:System.Windows.Forms.ToolStripContainer> аналогичен <xref:System.Windows.Forms.SplitContainer>.  Для создания типового расположения используются четыре закрепленные боковые панели \(экземпляры <xref:System.Windows.Forms.ToolStripPanel>\) и одна центральная панель \(экземпляр <xref:System.Windows.Forms.ToolStripContentPanel>\).  Боковые панели невозможно удалить, но можно скрыть.  Центральную панель невозможно ни удалить, ни скрыть.  Можно упорядочить один или несколько элементов управления <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> или <xref:System.Windows.Forms.StatusStrip> на боковой панели, центральную панель можно использовать для размещения других элементов управления.  Панель <xref:System.Windows.Forms.ToolStripContentPanel> также предоставляет возможность размещения обработчика отображения в форме для получения согласованного внешнего вида.  <xref:System.Windows.Forms.ToolStripContainer> не поддерживает интерфейс MDI.  
  
-   <xref:System.Windows.Forms.ToolStripPanel> предоставляет пространство для перемещения и расположения элементов управления <xref:System.Windows.Forms.ToolStrip>.  Можно использовать только одну панель, причем <xref:System.Windows.Forms.ToolStripPanel> хорошо работает в сценариях MDI.  
  
## См. также  
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)   
 [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)   
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [Элемент управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)   
 [Элемент управления StatusStrip](../../../../docs/framework/winforms/controls/statusstrip-control.md)   
 [Элемент управления ContextMenuStrip](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)   
 [Элемент управления BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)