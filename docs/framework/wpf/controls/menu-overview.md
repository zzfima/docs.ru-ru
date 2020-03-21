---
title: Обзор меню
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 53bc8f10e61b6e4e9e1f3b9a484340d9e2ec2a85
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186975"
---
# <a name="menu-overview"></a>Обзор меню
Класс <xref:System.Windows.Controls.Menu> позволяет организовывать элементы, связанные с командами и обработчиками событий, в иерархическом порядке. Каждый <xref:System.Windows.Controls.Menu> элемент содержит <xref:System.Windows.Controls.MenuItem> набор элементов.  

<a name="menu_control"></a>
## <a name="menu-control"></a>Элемент управления меню  
 Элемент <xref:System.Windows.Controls.Menu> представляет список элементов, которые указывают команды или варианты приложения. Обычно нажатие <xref:System.Windows.Controls.MenuItem> кнопки открывает подменю или вызывает выполнение команды приложением.  
  
<a name="creating_menus"></a>
## <a name="creating-menus"></a>Создание меню  
 Следующий пример <xref:System.Windows.Controls.Menu> создает для манипулирования <xref:System.Windows.Controls.TextBox>текстом в . Содержит <xref:System.Windows.Controls.Menu> <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Controls.MenuItem.Command%2A>объекты, которые <xref:System.Windows.Controls.MenuItem.IsCheckable%2A>используют, <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> и <xref:System.Windows.Controls.MenuItem.Checked> <xref:System.Windows.Controls.MenuItem.Unchecked>свойства <xref:System.Windows.Controls.MenuItem.Click> и , и, и события.  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>
## <a name="menuitems-with-keyboard-shortcuts"></a>Элементы MenuItems с сочетаниями клавиш  
 Сочетания клавиш являются комбинациями символов, которые могут <xref:System.Windows.Controls.Menu> быть введены с клавиатурой для вызывать команды. Например, сочетание клавиш для **копирования** — CTRL+C. Есть два свойства для использования с клавиатурой<xref:System.Windows.Controls.MenuItem.InputGestureText%2A> <xref:System.Windows.Controls.MenuItem.Command%2A>ярлыки и пункты меню - или .  
  
<a name="menus_inputgesturetext"></a>
### <a name="inputgesturetext"></a>InputGestureText  
 Ниже приводится, как <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> использовать свойство для присвоения текста ярлыка клавиатуры элементам <xref:System.Windows.Controls.MenuItem> управления. Таким образом можно лишь поместить сочетания клавиш в элемент меню.  Он не связывает команду <xref:System.Windows.Controls.MenuItem>с . Приложение должно обработать введенные пользователем данные для выполнения действия.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>
### <a name="command"></a>Get-Help  
 В следующем примере показано, как <xref:System.Windows.Controls.MenuItem.Command%2A> использовать свойство для ассоциировать команды **Open** и **Сохранить** с <xref:System.Windows.Controls.MenuItem> элементами управления. Свойство команды не только связывает <xref:System.Windows.Controls.MenuItem>команду с , но и поставляет текст жеста ввода для использования в качестве ярлыка.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 Класс <xref:System.Windows.Controls.MenuItem> также имеет <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> свойство, которое определяет элемент, в котором происходит команда. Если <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> не установлен, элемент, который имеет фокус клавиатуры получает команду. Дополнительные сведения о командах см. в разделе [Общие сведения о системе команд](../advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>
## <a name="menu-styling"></a>Задание стиля меню  
 С помощью укладки управления вы можете кардинально <xref:System.Windows.Controls.Menu> изменить внешний вид и поведение элементов управления без необходимости написания пользовательского элемента управления. В дополнение к настройке визуальных <xref:System.Windows.Style> свойств, можно также применить к отдельным частям элемента управления, изменить поведение частей элемента управления через свойства, или добавить дополнительные части или изменить расположение элемента управления. Следующие примеры демонстрируют несколько <xref:System.Windows.Controls.Menu> способов добавления элемента <xref:System.Windows.Style> управления.  
  
 Первый пример кода <xref:System.Windows.Style> определяет `Simple` вызов, который показывает, как использовать текущие настройки системы в вашем стиле. Код назначает `MenuHighlightBrush` цвет в качестве цвета фона меню и `MenuTextBrush` цвет в качестве цвета текста меню. Обратите внимание на использование ключей ресурсов для назначения кистей.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 В следующем <xref:System.Windows.Trigger> примере используются элементы, <xref:System.Windows.Controls.MenuItem> которые позволяют изменить внешний вид в ответ на события, происходящие <xref:System.Windows.Controls.Menu>на . При перемещении мыши <xref:System.Windows.Controls.Menu>над цветом переднего плана и изменятся характеристики шрифта элементов меню.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>См. также раздел

- [Пример коллекции элементов управления WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
