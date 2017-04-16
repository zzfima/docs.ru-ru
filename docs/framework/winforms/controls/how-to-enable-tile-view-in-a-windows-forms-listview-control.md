---
title: "Практическое руководство. Отображение содержимого элемента управления ListView в Windows Forms в виде мозаичного представления | Microsoft Docs"
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
  - "мозаика"
  - "Windows Forms, элементы управления"
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Практическое руководство. Отображение содержимого элемента управления ListView в Windows Forms в виде мозаичного представления
Функция мозаичного представления элемента управления <xref:System.Windows.Forms.ListView> обеспечивает визуальный баланс между графическими и текстовыми представлениями информации.  Текстовые данные, отображаемые для мозаичного представления элемента совпадают с данными о столбцах, определенных для подробного представления.  Мозаичное представление работает в сочетании с возможностями группирования или вставки метки элемента управления <xref:System.Windows.Forms.ListView>.  
  
 Мозаичное представление использует значок размером 32 x 32 пикселя и несколько строк текста, как показано на следующих рисунках.  
  
 ![Мозаичное представление в элементе управления ListView](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
Значки и текст мозаичного представления  
  
 Чтобы включить мозаичное представление, присвойте свойству <xref:System.Windows.Forms.ListView.View%2A> значение <xref:System.Windows.Forms.View>.  Размер элементов мозаики можно настроить, задав свойство <xref:System.Windows.Forms.ListView.TileSize%2A> и количество отображаемых строк текста в плитке путем настройки коллекции <xref:System.Windows.Forms.ListView.Columns%2A>.  
  
> [!NOTE]
>  Функция мозаичного представления доступна только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)], когда приложение вызывает метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>.  В предыдущих версиях операционных систем код, связанный с мозаичным представлением, не оказывает никакого влияния, элемент управления <xref:System.Windows.Forms.ListView> отображается в представлении крупных значков.  Для получения дополнительной информации см. <xref:System.Windows.Forms.ListView.View%2A?displayProperty=fullName>.  
  
### Выбор мозаичного представления программными средствами  
  
1.  Используйте перечисление <xref:System.Windows.Forms.View> элемента управления <xref:System.Windows.Forms.ListView>.  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## Пример  
 В завершенном примере кода ниже показано мозаичное представление с плиткой, в которой отображаются три строки текста.  Размер мозаики был подобран для предотвращения переноса строк.  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System и System.Windows.Forms.  
  
-   файл значка с именем book.ico в том же каталоге, что и исполняемый файл.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], можно также вставить код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.TileSize%2A>   
 [Элемент управления ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Windows XP Features and Windows Forms Controls](http://msdn.microsoft.com/ru-ru/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)