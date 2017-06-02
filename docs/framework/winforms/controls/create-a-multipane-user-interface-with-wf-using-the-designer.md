---
title: "Практическое руководство. Создание пользовательского интерфейса с несколькими областями с использованием форм Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "пользовательский интерфейс с несколькими областями"
  - "SplitContainer - элемент управления [Windows Forms], с помощью конструктора"
  - "пользовательский интерфейс, с несколькими панелями"
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Создание пользовательского интерфейса с несколькими областями с использованием форм Windows Forms с помощью конструктора
В следующей процедуре создается пользовательский интерфейс с несколькими областями, похожий на интерфейс, используемый в Microsoft Outlook, где имеется список **Папка**, область **Сообщения** и область **Предварительный просмотр**.  Такое расположение элементов достигается главным образом за счет закрепления элементов управления внутри форм.  
  
 При закреплении элемента управления необходимо решить, к какому краю родительского контейнера его следует прикрепить.  Таким образом, если для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> задать значение <xref:System.Windows.Forms.DockStyle>, правый край элемента управления закрепляется на правом крае родительского элемента управления.  При этом размер прикрепленного края элемента управления изменяется с учетом размера элемента управления контейнерного типа.  Дополнительные сведения об использовании свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> см. в разделе [Практическое руководство. Закрепление элементов управления в формах Windows Forms.](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Эта процедура предназначена для расположения элемента управления <xref:System.Windows.Forms.SplitContainer> и других элементов в форме, а не для добавления дополнительных функциональных возможностей и имитации Microsoft Outlook.  
  
 Для создания пользовательского интерфейса следует расположить все элементы управления внутри элемента управления <xref:System.Windows.Forms.SplitContainer>, в левой панели которого находится элемент управления <xref:System.Windows.Forms.TreeView>.  В правой панели элемента управления <xref:System.Windows.Forms.SplitContainer> содержится второй элемент управления <xref:System.Windows.Forms.SplitContainer>, причем элемент управления <xref:System.Windows.Forms.ListView> находится выше элемента управления <xref:System.Windows.Forms.RichTextBox>.  Эти элементы управления <xref:System.Windows.Forms.SplitContainer> позволяют независимо изменять размер других элементов управления в форме.  Используемые в данном примере методы можно изменять для создания пользовательских интерфейсов, отвечающих конкретным требованиям.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы создать пользовательский интерфейс типа Outlook на этапе разработки  
  
1.  Создайте новый проект "Приложение Windows".  Дополнительные сведения см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Перетащите элемент управления <xref:System.Windows.Forms.SplitContainer> с **панели элементов** на форму.  В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle>.  
  
3.  Перетащите элемент управления <xref:System.Windows.Forms.TreeView> из **панели элементов** в левую панель элемента управления <xref:System.Windows.Forms.SplitContainer>.  В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle>, щелкнув по левой панели окна редактора значений, которое открывается при нажатии кнопки со стрелкой вниз.  
  
4.  Перетащите другой элемент управления <xref:System.Windows.Forms.SplitContainer> из **панели элементов**; поместите его в правой панели элемента управления <xref:System.Windows.Forms.SplitContainer>, добавленного к форме.  В окне **Свойства** задайте для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle>, а для свойства <xref:System.Windows.Forms.SplitContainer.Orientation%2A> значение <xref:System.Windows.Forms.Orientation>.  
  
5.  Перетащите элемент управления <xref:System.Windows.Forms.ListView> из **панели элементов** на верхнюю панель второго элемента управления <xref:System.Windows.Forms.SplitContainer>, добавленного к форме.  Задайте для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> элемента управления <xref:System.Windows.Forms.ListView> значение <xref:System.Windows.Forms.DockStyle>.  
  
6.  Перетащите элемент управления <xref:System.Windows.Forms.RichTextBox> из **панели элементов** в нижнюю панель второго элемента управления <xref:System.Windows.Forms.SplitContainer>.  Задайте для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> элемента управления <xref:System.Windows.Forms.RichTextBox> значение <xref:System.Windows.Forms.DockStyle>.  
  
     В этот момент при нажатии F5 для запуска приложения в форме отображается пользовательский интерфейс, состоящий из трех частей, аналогичный интерфейсу Microsoft Outlook.  
  
    > [!NOTE]
    >  При наведении указателя мыши на один из разделителей в элементах управления <xref:System.Windows.Forms.SplitContainer> можно изменить внутренние размеры.  
  
     На этом этапе разработки приложения создан сложный пользовательский интерфейс.  На следующем этапе надо переходить к программированию самого приложения, возможно, подключив элемент управления <xref:System.Windows.Forms.TreeView> и элементы управления <xref:System.Windows.Forms.ListView> к какому\-либо источнику данных.  Дополнительные сведения о подключении элементов управления к данным см. в разделе [Связывание данных и Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md).  
  
## См. также  
 <xref:System.Windows.Forms.SplitContainer>   
 [Элемент управления SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)