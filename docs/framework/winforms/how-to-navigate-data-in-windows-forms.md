---
title: Как перемещаться по данным
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: 2dd900b652b0ff21ea0eb0dbc5463b22c869ec7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739397"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms
В приложении Windows самый простой способ перемещения по записям в источнике данных — привязать <xref:System.Windows.Forms.BindingSource> компонент к источнику данных, а затем привязать элементы управления к <xref:System.Windows.Forms.BindingSource>. Затем можно использовать встроенный метод навигации на <xref:System.Windows.Forms.BindingSource> такие <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> и <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>. Используя эти методы, измените свойства <xref:System.Windows.Forms.BindingSource.Position%2A> и <xref:System.Windows.Forms.BindingSource.Current%2A> <xref:System.Windows.Forms.BindingSource> соответствующим образом. Можно также найти элемент и установить его как текущий элемент, задав свойство <xref:System.Windows.Forms.BindingSource.Position%2A>.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>Увеличение места в источнике данных  
  
1. Установите свойство <xref:System.Windows.Forms.BindingSource.Position%2A> <xref:System.Windows.Forms.BindingSource> для привязанных данных к расположению записи, куда следует переходить. В следующем примере показано использование метода <xref:System.Windows.Forms.BindingSource.MoveNext%2A> <xref:System.Windows.Forms.BindingSource> для увеличения свойства <xref:System.Windows.Forms.BindingSource.Position%2A> при нажатии `nextButton`. <xref:System.Windows.Forms.BindingSource> связан с `Customers` таблицей `Northwind`набора данных.  
  
    > [!NOTE]
    > Присвоение свойству <xref:System.Windows.Forms.BindingSource.Position%2A> значения, превышающего первую или последнюю запись, не приведет к ошибке, так как .NET Framework не позволит задать для позиции значение вне границ списка. Если важно, чтобы приложение было известно о том, прошло ли вы предыдущую или последнюю запись, включите логику для проверки превышения числа элементов данных.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>Проверка того, пройдена ли конечная или начальная точка  
  
1. Создайте обработчик событий для события <xref:System.Windows.Forms.BindingSource.PositionChanged>. В обработчике можно проверить, превышает ли предлагаемое значение позицией фактическое число элементов данных.  
  
     В следующем примере показано, как можно проверить, достигнут ли последний элемент данных. В этом примере, если вы используете последний элемент, кнопка **Далее** в форме отключается.  
  
    > [!NOTE]
    > Имейте в виду, что при изменении списка, в котором выполняется перемещение по коду, следует повторно включить **следующую** кнопку, чтобы пользователи могли просматривать всю длину нового списка. Кроме того, имейте в виду, что описанное выше событие <xref:System.Windows.Forms.BindingSource.PositionChanged> для конкретных <xref:System.Windows.Forms.BindingSource>, с которым вы работаете, должно быть связано с методом обработки событий. Ниже приведен пример метода обработки события <xref:System.Windows.Forms.BindingSource.PositionChanged>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>Поиск элемента и его установка в качестве текущего элемента  
  
1. Найдите запись, которую вы хотите задать в качестве текущего элемента. Это можно сделать с помощью метода <xref:System.Windows.Forms.BindingSource.Find%2A> <xref:System.Windows.Forms.BindingSource>, если ваш источник данных реализует <xref:System.ComponentModel.IBindingList>. Некоторые примеры источников данных, реализующих <xref:System.ComponentModel.IBindingList>, <xref:System.ComponentModel.BindingList%601> и <xref:System.Data.DataView>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>См. также:

- [Источники данных, поддерживаемые Windows Forms](data-sources-supported-by-windows-forms.md)
- [Уведомления об изменениях в привязке данных Windows Forms](change-notification-in-windows-forms-data-binding.md)
- [Привязка данных и Windows Forms](data-binding-and-windows-forms.md)
- [Привязка данных Windows Forms](windows-forms-data-binding.md)
