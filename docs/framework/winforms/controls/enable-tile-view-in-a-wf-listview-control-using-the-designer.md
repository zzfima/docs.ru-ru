---
title: "Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора | Microsoft Docs"
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
  - "ListView - элемент управления [Windows Forms], мозаичное представление"
  - "функция мозаичного представления"
  - "мозаика, Windows Forms, элементы управления"
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора
Вид мозаики элемента управления <xref:System.Windows.Forms.ListView> позволяет обеспечить баланс между графическими и текстовыми сведениями.  В мозаичном представлении отображаются те же текстовые сведения об элементе, что и сведения в столбцах табличного отображения.  Вид мозаики работает в сочетании с возможностями группирования или метки вставки в элементе управления <xref:System.Windows.Forms.ListView>.  
  
 В представлении мозаики используются значки размером 32 х 32 точки и несколько строк текста, как показано на следующем рисунке.  
  
 ![Мозаичное представление в элементе управления ListView](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Свойства и методы вида мозаики позволяют указать, какие поля столбцов следует отображать для каждого элемента и управлять размером и внешним видом всех элементов в окне.  Первой строкой текста заголовка для ясности всегда является название элемента, первую строку нельзя изменить.  
  
 Для следующей процедуры требуется проект **Приложение Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.ListView>.  Сведения о создании такого проекта см. в разделах [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa) и [Практическое руководство. Добавление элементов управления в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Представление мозаики доступно только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] при вызове приложением метода <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>.  В предыдущих версиях операционных систем код, связанный с представлением в виде мозаики, не действовал, а элемент управления <xref:System.Windows.Forms.ListView> отображается в представлении крупных значков.  Дополнительные сведения см. в разделе <xref:System.Windows.Forms.ListView.View%2A?displayProperty=fullName>.  
>   
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Для выбора представления в виде мозаики в конструкторе  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.ListView> в форме.  
  
2.  В окне **Свойства** выберите свойство <xref:System.Windows.Forms.ListView.View%2A> и выберите **Рядом**.  
  
## См. также  
 <xref:System.Windows.Forms.ListView.TileSize%2A>   
 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/ru-ru/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)