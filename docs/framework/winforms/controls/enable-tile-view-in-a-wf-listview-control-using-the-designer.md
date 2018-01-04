---
title: "Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 36b20f4ee5bed6f81c42225f35083d51fb2a6308
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора
Функция мозаичного представления элемента <xref:System.Windows.Forms.ListView> позволяет обеспечить визуальный баланс между графическими и текстовыми представлениями информации. Текстовые данные, отображаемые для мозаичного представления элемента совпадают с данными о столбцах, определенных для подробного представления. Вид мозаики работает в сочетании с группирования или вставки метки возможности <xref:System.Windows.Forms.ListView> элемента управления.  
  
 Мозаичное представление использует значок 32 x 32 и несколько строк текста, как показано на следующем рисунке.  
  
 ![Мозаичное представление в элементе управления ListView](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Мозаичное представление, свойства и методы позволяют указать, какие поля столбцов для отображения для каждого элемента и управлять размером и внешним видом всех элементов в окно представления плитки. Для ясности первая строка текста заголовка всегда является имя элемента; его нельзя изменить.  
  
 В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.ListView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Функция мозаичного представления доступна только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)], когда приложение вызывает метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. В предыдущих версиях операционных систем код, связанный с мозаичным представлением, не оказывает никакого влияния, элемент управления <xref:System.Windows.Forms.ListView> отображается в представлении крупных значков. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.  
>   
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-tile-view-in-the-designer"></a>Выбор мозаичного представления в конструкторе  
  
1.  Выберите <xref:System.Windows.Forms.ListView> элемент управления в форме.  
  
2.  В **свойства** выберите <xref:System.Windows.Forms.ListView.View%2A> свойство и выберите **плитки**.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [Возможности Windows XP и элементы управления Windows Forms](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Общие сведения об элементе управления ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
