---
title: Обзор меню
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 3d5cfba0734e684349f7d73b7242f4b69089b94d
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124654"
---
# <a name="menu-overview"></a>Обзор меню
Класс <xref:System.Windows.Controls.Menu> позволяет упорядочивать элементы, связанные с командами и обработчиками событий, в иерархическом порядке. Каждый элемент <xref:System.Windows.Controls.Menu> содержит коллекцию элементов <xref:System.Windows.Controls.MenuItem>.  

<a name="menu_control"></a>   
## <a name="menu-control"></a>Элемент управления меню  
 Элемент управления <xref:System.Windows.Controls.Menu> представляет список элементов, которые указывают команды или параметры для приложения. Как правило, щелчок <xref:System.Windows.Controls.MenuItem> открывает подменю или заставляет приложение выполнить команду.  
  
<a name="creating_menus"></a>   
## <a name="creating-menus"></a>Создание меню  
 В следующем примере создается <xref:System.Windows.Controls.Menu> для обработки текста в <xref:System.Windows.Controls.TextBox>. <xref:System.Windows.Controls.Menu> содержит объекты <xref:System.Windows.Controls.MenuItem>, в которых используются свойства <xref:System.Windows.Controls.MenuItem.Command%2A>, <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>и <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>, а также события <xref:System.Windows.Controls.MenuItem.Checked>, <xref:System.Windows.Controls.MenuItem.Unchecked>и <xref:System.Windows.Controls.MenuItem.Click>.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>   
## <a name="menuitems-with-keyboard-shortcuts"></a>Элементы MenuItems с сочетаниями клавиш  
 Сочетания клавиш — это сочетания символов, которые можно указать с помощью клавиатуры, чтобы вызвать <xref:System.Windows.Controls.Menu> команды. Например, сочетание клавиш для **копирования** — CTRL+C. С сочетаниями клавиш и элементами меню можно использовать два свойства:<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> или <xref:System.Windows.Controls.MenuItem.Command%2A>.  
  
<a name="menus_inputgesturetext"></a>   
### <a name="inputgesturetext"></a>InputGestureText  
 В следующем примере показано использование свойства <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> для назначения сочетаний клавиш для <xref:System.Windows.Controls.MenuItem> элементов управления. Таким образом можно лишь поместить сочетания клавиш в элемент меню.  Она не связывает команду с <xref:System.Windows.Controls.MenuItem>. Приложение должно обработать введенные пользователем данные для выполнения действия.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>   
### <a name="command"></a>Get-Help  
 В следующем примере показано, как использовать свойство <xref:System.Windows.Controls.MenuItem.Command%2A>, чтобы связать команды **открытия** и **сохранения** с элементами управления <xref:System.Windows.Controls.MenuItem>. Свойство Command не только связывает команду с <xref:System.Windows.Controls.MenuItem>, но также предоставляет текст жеста ввода для использования в качестве ярлыка.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 Класс <xref:System.Windows.Controls.MenuItem> также имеет свойство <xref:System.Windows.Controls.MenuItem.CommandTarget%2A>, которое указывает элемент, где выполняется команда. Если <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> не задано, элемент, имеющий фокус клавиатуры, получает команду. Дополнительные сведения о командах см. в разделе [Общие сведения о системе команд](../advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>   
## <a name="menu-styling"></a>Задание стиля меню  
 Благодаря стилю элементов управления можно значительно изменить внешний вид и поведение элементов управления <xref:System.Windows.Controls.Menu> без необходимости написания пользовательского элемента управления. Помимо настройки визуальных свойств, можно также применить <xref:System.Windows.Style> к отдельным частям элемента управления, изменить поведение частей элемента управления с помощью свойств или добавить дополнительные части или изменить макет элемента управления. В следующих примерах демонстрируются несколько способов добавления <xref:System.Windows.Style> в элемент управления <xref:System.Windows.Controls.Menu>.  
  
 В первом примере кода определяется <xref:System.Windows.Style> с именем `Simple`, в котором показано, как использовать текущие параметры системы в вашем стиле. Код назначает `MenuHighlightBrush` цвет в качестве цвета фона меню и `MenuTextBrush` цвет в качестве цвета текста меню. Обратите внимание на использование ключей ресурсов для назначения кистей.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 В следующем примере используются элементы <xref:System.Windows.Trigger>, позволяющие изменять внешний вид <xref:System.Windows.Controls.MenuItem> в ответ на события, происходящие в <xref:System.Windows.Controls.Menu>. При наведении указателя мыши на <xref:System.Windows.Controls.Menu>изменяется цвет переднего плана и характеристики шрифта пунктов меню.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>См. также раздел

- [Пример коллекции элементов управления WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
