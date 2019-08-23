---
title: Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms
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
ms.openlocfilehash: eb973497f51592b5d34c22e62da77612aec23c35
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964273"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms
В приложении Windows самый простой способ перемещения по записям в источнике данных — привязать <xref:System.Windows.Forms.BindingSource> компонент к источнику данных, а затем привязать элементы управления <xref:System.Windows.Forms.BindingSource>к. Затем можно использовать встроенный метод <xref:System.Windows.Forms.BindingSource> навигации для <xref:System.Windows.Forms.BindingSource.MoveNext%2A>таких методов, <xref:System.Windows.Forms.BindingSource.MoveLast%2A> <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> и <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>. Используя эти методы, вы измените <xref:System.Windows.Forms.BindingSource.Position%2A> свойства <xref:System.Windows.Forms.BindingSource.Current%2A> <xref:System.Windows.Forms.BindingSource> и соответствующим образом. Можно также найти элемент и установить его как текущий элемент, задав <xref:System.Windows.Forms.BindingSource.Position%2A> свойство.  
  
### <a name="to-increment-the-position-in-a-data-source"></a>Увеличение места в источнике данных  
  
1. Установите для<xref:System.Windows.Forms.BindingSource> привязанных данных свойствообъекта,котороебудетуказывать<xref:System.Windows.Forms.BindingSource.Position%2A> на расположение записи. В следующем примере показано <xref:System.Windows.Forms.BindingSource.MoveNext%2A> использование метода <xref:System.Windows.Forms.BindingSource> объекта для `nextButton` увеличения <xref:System.Windows.Forms.BindingSource.Position%2A> значения свойства при нажатии кнопки. Объект <xref:System.Windows.Forms.BindingSource> `Northwind`связан `Customers` с таблицей набора данных.  
  
    > [!NOTE]
    > Присвоение <xref:System.Windows.Forms.BindingSource.Position%2A> свойству значения, превышающего первую или последнюю запись, не приведет к ошибке, так как .NET Framework не позволит установить в качестве позиции значение вне границ списка. Если важно, чтобы приложение было известно о том, прошло ли вы предыдущую или последнюю запись, включите логику для проверки превышения числа элементов данных.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>Проверка того, пройдена ли конечная или начальная точка  
  
1. Создайте обработчик событий для события <xref:System.Windows.Forms.BindingSource.PositionChanged>. В обработчике можно проверить, превышает ли предлагаемое значение позицией фактическое число элементов данных.  
  
     В следующем примере показано, как можно проверить, достигнут ли последний элемент данных. В этом примере, если вы используете последний элемент, кнопка **Далее** в форме отключается.  
  
    > [!NOTE]
    > Имейте в виду, что при изменении списка, в котором выполняется перемещение по коду, следует повторно включить **следующую** кнопку, чтобы пользователи могли просматривать всю длину нового списка. Кроме того, имейте в виду, <xref:System.Windows.Forms.BindingSource.PositionChanged> что указанное выше событие <xref:System.Windows.Forms.BindingSource> для конкретного пользователя необходимо связать с методом обработки событий. Ниже приведен пример метода для обработки <xref:System.Windows.Forms.BindingSource.PositionChanged> события.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>Поиск элемента и его установка в качестве текущего элемента  
  
1. Найдите запись, которую вы хотите задать в качестве текущего элемента. Это можно сделать с помощью <xref:System.Windows.Forms.BindingSource.Find%2A> метода <xref:System.Windows.Forms.BindingSource>, если ваш источник данных реализует <xref:System.ComponentModel.IBindingList>. Некоторые примеры источников данных, реализующих <xref:System.ComponentModel.IBindingList> , <xref:System.ComponentModel.BindingList%601> являются <xref:System.Data.DataView>и.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Источники данных, поддерживаемые Windows Forms](data-sources-supported-by-windows-forms.md)
- [Уведомления об изменениях в привязке данных Windows Forms](change-notification-in-windows-forms-data-binding.md)
- [Привязка данных и Windows Forms](data-binding-and-windows-forms.md)
- [Привязка данных Windows Forms](windows-forms-data-binding.md)
