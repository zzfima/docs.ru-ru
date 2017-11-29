---
title: "Указатели мыши в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4fb0e193ccbced719f30ede91cb59cd51dd349a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="mouse-pointers-in-windows-forms"></a>Указатели мыши в Windows Forms
Мышь *указатель*, которые иногда называют курсор является точечного рисунка, который задает точку фокуса на экране для ввода данных пользователем с помощью мыши. В этом разделе содержится обзор указатель мыши в формах Windows Forms и описываются некоторые из способов изменения и управления указатель мыши.  
  
## <a name="accessing-the-mouse-pointer"></a>Обращение к указателю мыши  
 Указатель мыши представлен <xref:System.Windows.Forms.Cursor> класса и каждая <xref:System.Windows.Forms.Control> имеет <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> свойство, которое указывает указатель для этого элемента управления. <xref:System.Windows.Forms.Cursor> Класс содержит свойства, описывающие указателя, такие как <xref:System.Windows.Forms.Cursor.Position%2A> и <xref:System.Windows.Forms.Cursor.HotSpot%2A> свойства и методы, которые можно изменить внешний вид указателя, такие как <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>, и <xref:System.Windows.Forms.Cursor.DrawStretched%2A> методы.  
  
## <a name="controlling-the-mouse-pointer"></a>Управление указателем мыши  
 Иногда может потребоваться ограничить область, в котором указатель мыши, можно использовать или изменение положения указателя мыши. Можно получить или задать текущее расположение мыши с помощью <xref:System.Windows.Forms.Cursor.Position%2A> свойство <xref:System.Windows.Forms.Cursor>. Кроме того, можно ограничить область, можно использовать указатель мыши режим <xref:System.Windows.Forms.Cursor.Clip%2A> свойство. Области отсечения по умолчанию является весь экран.  
  
## <a name="changing-the-mouse-pointer"></a>Изменение указателя мыши  
 Изменение указателя мыши является важным способом предоставления отклика для пользователя. Например, можно изменить указатель мыши в обработчиках <xref:System.Windows.Forms.Control.MouseEnter> и <xref:System.Windows.Forms.Control.MouseLeave> событий, чтобы сообщить пользователю о выполнении вычислений и ограничить взаимодействие с пользователем в элементе управления. Иногда указатель мыши изменяется из-за системных событий, например когда приложение участвует в операции перетаскивания и вставки.  
  
 — Это основной способ изменение указателя мыши, задав <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.Control.DefaultCursor%2A> свойства элемента управления в новую <xref:System.Windows.Forms.Cursor>. Примеры изменения указателя мыши, см. в примере кода в <xref:System.Windows.Forms.Cursor> класса. Кроме того <xref:System.Windows.Forms.Cursors> класс предоставляет набор <xref:System.Windows.Forms.Cursor> объектов для различных типов указателей, таких как указатель в виде руки. Для отображения указателя ожидания, который имеет вид песочных часов, каждый раз, когда указатель мыши находится на элементе управления, используйте <xref:System.Windows.Forms.Control.UseWaitCursor%2A> свойство <xref:System.Windows.Forms.Control> класса.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Cursor>  
 [Ввод данных мышью в приложении Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 [Функциональная возможность перетаскивания в Windows Forms](../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)
