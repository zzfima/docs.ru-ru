---
title: "Пример. Создание интерфейса в стиле проводника с использованием элементов управления ListView и TreeView с помощью конструктора | Microsoft Docs"
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
  - "приложения в стиле обозревателя"
  - "приложения в стиле обозревателя, пошаговые руководства"
  - "ListView - элемент управления [Windows Forms], интерфейс в стиле проводника"
  - "ListView - элемент управления [Windows Forms], интерфейс в стиле проводника"
  - "ListView - элемент управления [Windows Forms], используемые с ним элементы управления TreeView"
  - "TreeView - элемент управления [Windows Forms], используемые с ним элементы управления ListView"
  - "TreeView - элемент управления [Windows Forms], использование для интерфейса в стиле проводника"
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Пример. Создание интерфейса в стиле проводника с использованием элементов управления ListView и TreeView с помощью конструктора
Одним из преимуществ Visual Studio является возможность создания профессионально выглядящих приложений Windows Forms в короткие сроки.  Обычно создается пользовательский интерфейс с элементами управления <xref:System.Windows.Forms.ListView> и <xref:System.Windows.Forms.TreeView>, который напоминает проводник операционной системы Windows.  Проводник Windows отображает иерархическую структуру файлов и папок, расположенных на компьютере пользователя.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы создать форму с элементами управления ListView и TreeView, выполните следующие действия:  
  
1.  В меню **Файл** последовательно выберите пункты **Создать** и **Проект**.  
  
2.  В диалоговом окне **Новый проект** выполните следующие действия:  
  
    1.  В области категорий выберите **Visual Basic** или **Visual C\#.**  
  
    2.  В списке шаблонов выберите **Приложение Windows Forms**.  
  
3.  Нажмите кнопку **ОК**.  Создается новый проект Windows Forms.  
  
4.  Добавьте к форме элемент управления <xref:System.Windows.Forms.SplitContainer> и присвойте его свойству <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle>.  
  
5.  Добавьте в форму объект <xref:System.Windows.Forms.ImageList> с именем `imageList1` и используйте окно свойств для добавления изображения папки и изображения документа \(в указанном порядке\).  
  
6.  Добавьте к форме элемент управления <xref:System.Windows.Forms.TreeView> с именем `treeview1` и расположите его в левой части элемента управления <xref:System.Windows.Forms.SplitContainer>.  В окне свойств `treeView1` задайте следующие значения свойств.  
  
    1.  Задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle>.  
  
    2.  Задайте для свойства <xref:System.Windows.Forms.TreeView.ImageList%2A> значение `imagelist1.`.  
  
7.  Добавьте к форме элемент управления <xref:System.Windows.Forms.ListView> с именем `listView1` и расположите его в правой части элемента управления <xref:System.Windows.Forms.SplitContainer>.  В окне свойств `listview1` задайте следующие значения свойств.  
  
    1.  Задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle>.  
  
    2.  Задайте для свойства <xref:System.Windows.Forms.ListView.View%2A> значение <xref:System.Windows.Forms.View>.  
  
    3.  Откройте редактор коллекции ColumnHeader, нажав кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) в свойстве <xref:System.Windows.Forms.ListView.Columns%2A>**.** Добавьте три столбца и присвойте их свойству <xref:System.Windows.Forms.ColumnHeader.Text%2A> значения `Name`, `Type` и `Last Modified` соответственно.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.  
  
    4.  Установите для свойства <xref:System.Windows.Forms.ListView.SmallImageList%2A> значение `imageList1.`.  
  
8.  Создайте код для заполнения элемента <xref:System.Windows.Forms.TreeView> узлами и подузлами.  Добавьте следующий код в класс `Form1`.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. Поскольку предыдущий код использует пространство имен System.IO, добавьте соответствующий элемент или импортируйте оператор в начало формы.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. В конструкторе форм вызовите метод настройки из предыдущего шага или метод обработки событий <xref:System.Windows.Forms.Form.Load>.  Добавьте следующий код в конструктор формы.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. Обработайте событие <xref:System.Windows.Forms.TreeView.NodeMouseClick> для значения `treeview1`и создайте код, заполняющий `listview1`содержимым узлапри выборе этого узла.  Добавьте следующий код в класс `Form1`.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     При использовании C\# убедитесь, что событие <xref:System.Windows.Forms.TreeView.NodeMouseClick> связано со своим методом обработки событий.  Добавьте следующий код в конструктор формы.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## Тестирование приложения  
 Теперь можно проверить форму, чтобы убедиться, что она работает так, как ожидалось.  
  
#### Чтобы проверить форму, выполните следующие действия:  
  
-   Нажмите клавишу F5 для запуска приложения.  
  
     На экране появится разделенная форма, содержащая элемент управления <xref:System.Windows.Forms.TreeView>. В левой части формы отображается каталог проекта, а в правой — элемент управления <xref:System.Windows.Forms.ListView> с тремя столбцами.  Выбирая узлы\-каталоги, можно перемещаться по объекту <xref:System.Windows.Forms.TreeView>. При этом объект <xref:System.Windows.Forms.ListView> будет заполняться содержимым выбранного каталога.  
  
## Следующие действия  
 Это приложение служит примером совместного использования элементов управления <xref:System.Windows.Forms.TreeView> и <xref:System.Windows.Forms.ListView>.  Для получения дополнительных сведений об этих элементах управления см. следующие разделы:  
  
-   [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [Практическое руководство. Добавление в элемент управления ListView возможностей поиска](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [Практическое руководство. Подключение контекстного меню к узлу элемента управления TreeView](../../../../docs/framework/winforms/controls/how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## См. также  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.TreeView>   
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)   
 [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)