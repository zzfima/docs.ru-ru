---
title: "Обзор меню | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "элемент управления "Меню""
  - "элементы управления, меню"
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Обзор меню
<xref:System.Windows.Controls.Menu> позволяет упорядочивать элементы, связанные с командами и обработчиками событий, в иерархическом порядке. Каждый <xref:System.Windows.Controls.Menu> элемент содержит коллекцию <xref:System.Windows.Controls.MenuItem> элементы.  
  
   
  
<a name="menu_control"></a>   
## <a name="menu-control"></a>Элемент управления меню  
 <xref:System.Windows.Controls.Menu> элемент управления представляет список элементов, определяющих команды или параметры для приложения. Как правило, щелкнув <xref:System.Windows.Controls.MenuItem> открывает подменю или вызывает приложение для выполнения команды.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>Создание меню  
 В следующем примере создается <xref:System.Windows.Controls.Menu> для операций с текстом в <xref:System.Windows.Controls.TextBox>. <xref:System.Windows.Controls.Menu> содержит <xref:System.Windows.Controls.MenuItem> объектов, использующих <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>, и <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> свойства и <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>, и <xref:System.Windows.Controls.MenuItem.Click> события.  
  
 [!code-xml[MenuItemCommandsAndEvents#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems с помощью сочетаний клавиш  
 Сочетания клавиш являются сочетаниями знаков, которые могут быть введены с помощью клавиатуры для вызова <xref:System.Windows.Controls.Menu> команды. Например, ярлык для **копирования** — CTRL + C. Существует два свойства, которые будут использоваться с сочетаниями клавиш и пункты меню —<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> или <xref:System.Windows.Controls.MenuItem.Command%2A>.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> свойства, чтобы назначить сочетания клавиш для <xref:System.Windows.Controls.MenuItem> элементов управления. Это только помещает сочетания клавиш в элементе меню.  Не связывает команду с <xref:System.Windows.Controls.MenuItem>. Приложение должно обрабатывать ввод пользователя для выполнения действия.  
  
 [!code-xml[MenuEvent#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>Команда  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.MenuItem.Command%2A> для связи **откройте** и **Сохранить** команд с <xref:System.Windows.Controls.MenuItem> элементов управления. Не только свойство command связать команду <xref:System.Windows.Controls.MenuItem>, но также предоставляет жест ввода текста для использования в качестве ярлыка.  
  
 [!code-xml[MenuEvent#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 <xref:System.Windows.Controls.MenuItem> класс также содержит <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> свойство, которое указывает элемент, где происходит команды. Если <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> не задано, команда получает элемент, имеющий фокус. Дополнительные сведения о командах см. в разделе [Общие сведения о командах](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>Применение стилей к меню  
 С помощью стиля элемента управления можно значительно изменить внешний вид и поведение <xref:System.Windows.Controls.Menu> элементов управления без необходимости написания пользовательского элемента управления. В дополнение к установке свойств визуализации также можно применить <xref:System.Windows.Style> к отдельной части элемента управления, изменить поведение части элемента управления через свойства или добавить дополнительные части или изменить макет элемента управления. В следующих примерах демонстрируется несколько способов добавления <xref:System.Windows.Style> для <xref:System.Windows.Controls.Menu> элемента управления.  
  
 Первый пример кода определяет <xref:System.Windows.Style> называется `Simple` , показано, как использовать текущие параметры системы в стиле. Код назначает цвет `MenuHighlightBrush` как цвет фона меню и `MenuTextBrush` как цвет текста меню. Обратите внимание на использование ключей ресурсов для установки кистей.  
  
 [!code-xml[MenuStylesSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 В следующем примере используется <xref:System.Windows.Trigger> элементы, которые позволяют изменять внешний вид <xref:System.Windows.Controls.MenuItem> в ответ на события, происходящие на <xref:System.Windows.Controls.Menu>. При перемещении указателя мыши <xref:System.Windows.Controls.Menu>, цвет текста и изменить характеристики шрифта элементов меню.  
  
 [!code-xml[MenuStylesSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>См. также  
 [Пример коллекции элементов управления WPF](http://go.microsoft.com/fwlink/?LinkID=160053)