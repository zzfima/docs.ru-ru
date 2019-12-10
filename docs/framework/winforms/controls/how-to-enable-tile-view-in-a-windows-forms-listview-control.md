---
title: Практическое руководство. Отображение содержимого элемента управления ListView в Windows Forms в виде мозаичного представления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tile view feature
- tiling
- Windows Forms, controls
- ListView control [Windows Forms], tile view
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
ms.openlocfilehash: 489b9a9d0341391c756175acb19d962d642eb7b2
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960448"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a>Практическое руководство. Отображение содержимого элемента управления ListView в Windows Forms в виде мозаичного представления
Функция мозаичного представления элемента управления <xref:System.Windows.Forms.ListView> обеспечивает визуальный баланс между графическими и текстовыми представлениями информации. Текстовые данные, отображаемые для мозаичного представления элемента совпадают с данными о столбцах, определенных для подробного представления. Мозаичное представление работает в сочетании с возможностями группирования или вставки метки элемента управления <xref:System.Windows.Forms.ListView>.  
  
 Мозаичное представление использует значок размером 32 x 32 пикселя и несколько строк текста, как показано на следующих рисунках.  
  
 ![Мозаичное представление в элементе управления ListView](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "Значки и текст мозаичного представления")  
 
 Чтобы включить мозаичное представление, присвойте свойству <xref:System.Windows.Forms.ListView.View%2A> значение <xref:System.Windows.Forms.View.Tile>. Размер элементов мозаики можно настроить, задав свойство <xref:System.Windows.Forms.ListView.TileSize%2A> и количество отображаемых строк текста в плитке путем настройки коллекции <xref:System.Windows.Forms.ListView.Columns%2A>.  
  
### <a name="to-set-tile-view-programmatically"></a>Выбор мозаичного представления программными средствами  
  
1. Используйте перечисление <xref:System.Windows.Forms.View> элемента управления <xref:System.Windows.Forms.ListView>.  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a>Пример  
 В завершенном примере кода ниже показано мозаичное представление с плиткой, в которой отображаются три строки текста. Размер мозаики был подобран для предотвращения переноса строк.  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- ссылки на сборки System и System.Windows.Forms;  
  
- файл значка с именем book.ico в том же каталоге, что и исполняемый файл.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
