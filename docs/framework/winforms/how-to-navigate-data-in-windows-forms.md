---
title: "Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "CurrencyManager - класс, перемещение по данным в формах Windows Forms"
  - "курсоры, источники данных"
  - "данные [Windows Forms], переходы"
  - "источники данных, Windows Forms"
  - "Windows Forms, переходы"
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms
Наиболее простым способом перехода по записям источника данных в приложении Windows является привязка компонента <xref:System.Windows.Forms.BindingSource> к источнику данных и последующая привязка элементов управления к компоненту <xref:System.Windows.Forms.BindingSource>.  После этого можно использовать встроенные методы навигации компонента <xref:System.Windows.Forms.BindingSource>, например <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> и <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.  Использование этих методов позволит правильно настроить свойства <xref:System.Windows.Forms.BindingSource.Position%2A> и <xref:System.Windows.Forms.BindingSource.Current%2A> компонента <xref:System.Windows.Forms.BindingSource>.  Можно также найти элемент и сделать его текущим, установив свойство <xref:System.Windows.Forms.BindingSource.Position%2A>.  
  
### Увеличение позиции в источнике данных  
  
1.  Присвойте номер записи связанных данных, на которую следует переместиться, свойству <xref:System.Windows.Forms.BindingSource.Position%2A> компонента <xref:System.Windows.Forms.BindingSource> .  В следующем примере демонстрируется использование метода <xref:System.Windows.Forms.BindingSource.MoveNext%2A> компонента <xref:System.Windows.Forms.BindingSource> для увеличения значения свойства <xref:System.Windows.Forms.BindingSource.Position%2A> при щелчке элемента управления `nextButton`.  Компонент <xref:System.Windows.Forms.BindingSource> связан с таблицей `Customers` набора данных `Northwind`.  
  
    > [!NOTE]
    >  Если для свойства <xref:System.Windows.Forms.BindingSource.Position%2A> задать значение, которое выходит за пределы диапазона, ограниченного первой и последней записями, это не приведет к ошибке, так как платформа [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] не разрешит задать значение положения, выходящее за границы списка.  Если в приложении важно знать, достигнута ли первая или последняя запись, добавьте логику для проверки превышения количества элементов данных.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### Чтобы проверить, достигнута ли первая или последняя запись, выполните следующие действия.  
  
1.  Создайте обработчик событий для события <xref:System.Windows.Forms.BindingSource.PositionChanged>.  В обработчике можно проверить, превысило ли предполагаемое значение положения действительное значение счетчика элементов данных.  
  
     В следующем примере показано, как можно реализовать проверку достижения последнего элемента данных.  В примере при достижении последнего элемента отключается кнопка **Далее**.  
  
    > [!NOTE]
    >  Обратите внимание, что при изменении списка, по которому перемещается пользователь, в коде следует снова включить кнопку **Далее**, чтобы пользователи могли просматривать новый список целиком.  Кроме того, следует учесть, что вышеупомянутое событие <xref:System.Windows.Forms.BindingSource.PositionChanged> используемого компонента <xref:System.Windows.Forms.BindingSource> должно быть связано со своим методом обработки событий.  Ниже приведен пример метода обработки события <xref:System.Windows.Forms.BindingSource.PositionChanged>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### Чтобы найти элемент и сделать его текущим, выполните следующие действия.  
  
1.  Найдите запись, которую необходимо сделать текущим элементом.  Если источник данных реализует интерфейс <xref:System.ComponentModel.IBindingList>, то для поиска элемента можно использовать метод <xref:System.Windows.Forms.BindingSource.Find%2A> компонента <xref:System.Windows.Forms.BindingSource>.  В качестве примеров источников данных, реализующих интерфейс <xref:System.ComponentModel.IBindingList>, можно назвать объекты <xref:System.ComponentModel.BindingList%601> и <xref:System.Data.DataView>.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## См. также  
 [Источники данных, поддерживаемые Windows Forms](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)   
 [Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Связывание данных и Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Связывание элементов управления Windows Forms с данными](../../../docs/framework/winforms/windows-forms-data-binding.md)