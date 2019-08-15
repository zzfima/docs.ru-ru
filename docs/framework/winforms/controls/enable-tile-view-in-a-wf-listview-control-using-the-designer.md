---
title: Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 8a45a8a484bd373f53585b1b113a51e59b30fca2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040353"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора
Функция мозаичного представления <xref:System.Windows.Forms.ListView> элемента управления позволяет обеспечить визуальный баланс между графическими и текстовыми сведениями. Текстовые данные, отображаемые для мозаичного представления элемента совпадают с данными о столбцах, определенных для подробного представления. Мозаичное представление функции в сочетании с функциями группирования или вставки меток в <xref:System.Windows.Forms.ListView> элементе управления.

 Мозаичное представление использует значок 32 x 32 и несколько строк текста, как показано на следующем рисунке.

 ![Мозаичное представление в элементе управления ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Значки и текст мозаичного представления")

 Свойства и методы мозаичного представления позволяют указать, какие поля столбцов должны отображаться для каждого элемента, а также совокупно управлять размером и внешним видом всех элементов в окне мозаичного представления. Для ясности первая строка текста в плитке всегда является именем элемента. его нельзя изменить.

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.ListView> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

> [!NOTE]
> Функция мозаичного представления доступна только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)], когда приложение вызывает метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. В предыдущих версиях операционных систем код, связанный с мозаичным представлением, не оказывает никакого влияния, элемент управления <xref:System.Windows.Forms.ListView> отображается в представлении крупных значков. Дополнительные сведения см. в разделе <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.

## <a name="to-set-tile-view-in-the-designer"></a>Задание мозаичного представления в конструкторе

1. В Visual Studio выберите <xref:System.Windows.Forms.ListView> элемент управления в форме.

2. В окне **Свойства** выберите <xref:System.Windows.Forms.ListView.View%2A> свойство и щелкните плитка.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
