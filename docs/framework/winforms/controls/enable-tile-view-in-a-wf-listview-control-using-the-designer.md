---
title: Включение мозаичного представления в элементе управления ListView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: a0429efaab14995ab1e3f3b0dfd91db61de72fbf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745806"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>Практическое руководство. Включение вида мозаики в элементе управления ListView формы Windows Forms с помощью конструктора
Функция мозаичного представления элемента управления <xref:System.Windows.Forms.ListView> позволяет обеспечить визуальный баланс между графическими и текстовыми сведениями. Текстовые данные, отображаемые для мозаичного представления элемента совпадают с данными о столбцах, определенных для подробного представления. Мозаичное представление функции в сочетании с функциями группирования или вставки меток в элементе управления <xref:System.Windows.Forms.ListView>.

 Мозаичное представление использует значок 32 x 32 и несколько строк текста, как показано на следующем рисунке.

 ![Мозаичное представление в элементе управления ListView](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Значки и текст мозаичного представления")

 Свойства и методы мозаичного представления позволяют указать, какие поля столбцов должны отображаться для каждого элемента, а также совокупно управлять размером и внешним видом всех элементов в окне мозаичного представления. Для ясности первая строка текста в плитке всегда является именем элемента. его нельзя изменить.

 Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.ListView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

## <a name="to-set-tile-view-in-the-designer"></a>Задание мозаичного представления в конструкторе

1. В Visual Studio выберите элемент управления <xref:System.Windows.Forms.ListView> в форме.

2. В окне **Свойства** выберите свойство <xref:System.Windows.Forms.ListView.View%2A> и щелкните **плитка**.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [Общие сведения об элементе управления ListView](listview-control-overview-windows-forms.md)
