---
title: Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 86645396033ca1c3cfb025ba6db42b726f7e7969
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734399"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора
Функция мозаичного представления элемента <xref:System.Windows.Forms.ListView> элемент управления позволяет обеспечивает визуальный баланс между графическими и текстовыми представлениями информации. Текстовые данные, отображаемые для мозаичного представления элемента совпадают с данными о столбцах, определенных для подробного представления. Вид мозаики, работает в сочетании с группирования или вставки метки возможностях <xref:System.Windows.Forms.ListView> элемента управления.  
  
 Мозаичное представление использует значок в виде 32 x 32 и несколько строк текста, как показано на следующем рисунке.  
  
 ![Мозаичное представление в элементе управления ListView](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Мозаичное представление, свойства и методы позволяют указать, какие поля столбца для отображения для каждого элемента и управлять размером и внешним видом всех элементов в окно представления плитки. Для ясности первая часть текста заголовка всегда является имя элемента; его нельзя изменить.  
  
 Следующая процедура требуется **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.ListView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Функция мозаичного представления доступна только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)], когда приложение вызывает метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. В предыдущих версиях операционных систем код, связанный с мозаичным представлением, не оказывает никакого влияния, элемент управления <xref:System.Windows.Forms.ListView> отображается в представлении крупных значков. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.  
>   
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-tile-view-in-the-designer"></a>Выбор мозаичного представления в конструкторе  
  
1.  Выберите <xref:System.Windows.Forms.ListView> элемент управления в форме.  
  
2.  В **свойства** выберите <xref:System.Windows.Forms.ListView.View%2A> свойство и выберите **плитки**.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [Возможности Windows XP и элементы управления Windows Forms](https://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
