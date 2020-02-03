---
title: Указатели мыши
ms.date: 03/30/2017
helpviewer_keywords:
- pointers [Windows Forms], setting
- mouse pointers
- mouse cursors
- mouse pointers [Windows Forms], setting
- cursors [Windows Forms], setting
- mouse [Windows Forms], cursors
ms.assetid: c3400d85-de5b-42e8-abc3-d6088d69ee53
ms.openlocfilehash: 4e8349effcd9b59045e39b763b4cb8b7d2fceb91
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740955"
---
# <a name="mouse-pointers-in-windows-forms"></a>Указатели мыши в Windows Forms
*Указатель*мыши, который иногда называют курсором, представляет собой точечный рисунок, указывающий на экран точку фокусировки для ввода данных пользователем с помощью мыши. В этом разделе приводится обзор указателя мыши в Windows Forms и описываются некоторые способы изменения и управления указателем мыши.  
  
## <a name="accessing-the-mouse-pointer"></a>Доступ к указателю мыши  
 Указатель мыши представлен классом <xref:System.Windows.Forms.Cursor>, и каждый <xref:System.Windows.Forms.Control> имеет свойство <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType>, которое указывает указатель для этого элемента управления. Класс <xref:System.Windows.Forms.Cursor> содержит свойства, описывающие указатель, например свойства <xref:System.Windows.Forms.Cursor.Position%2A> и <xref:System.Windows.Forms.Cursor.HotSpot%2A>, а также методы, которые могут изменять внешний вид указателя, например <xref:System.Windows.Forms.Cursor.Show%2A>, <xref:System.Windows.Forms.Cursor.Hide%2A>и методы <xref:System.Windows.Forms.Cursor.DrawStretched%2A>.  
  
## <a name="controlling-the-mouse-pointer"></a>Управление указателем мыши  
 Иногда может потребоваться ограничить область, в которой можно использовать указатель мыши, или изменить расположение мыши. Вы можете получить или задать текущее расположение мыши с помощью свойства <xref:System.Windows.Forms.Cursor.Position%2A> <xref:System.Windows.Forms.Cursor>. Кроме того, можно ограничить область, в которой можно использовать указатель мыши, задав свойство <xref:System.Windows.Forms.Cursor.Clip%2A>. По умолчанию областью обрезки является весь экран.  
  
## <a name="changing-the-mouse-pointer"></a>Изменение указателя мыши  
 Изменение указателя мыши является важным способом предоставления отзывов пользователю. Например, указатель мыши можно изменить в обработчиках событий <xref:System.Windows.Forms.Control.MouseEnter> и <xref:System.Windows.Forms.Control.MouseLeave>, чтобы сообщить пользователю о том, что выполняются вычисления, и ограничить взаимодействие с пользователем в элементе управления. Иногда указатель мыши изменится из-за системных событий, например, когда приложение вовлечено в операцию перетаскивания.  
  
 Основной способ изменения указателя мыши заключается в присвоении свойству <xref:System.Windows.Forms.Control.Cursor%2A?displayProperty=nameWithType> или <xref:System.Windows.Forms.Control.DefaultCursor%2A> элемента управления нового <xref:System.Windows.Forms.Cursor>. Примеры изменения указателя мыши см. в примере кода в классе <xref:System.Windows.Forms.Cursor>. Кроме того, класс <xref:System.Windows.Forms.Cursors> предоставляет набор объектов <xref:System.Windows.Forms.Cursor> для многих различных типов указателей, например указатель, напоминающий руки. Чтобы отобразить указатель ожидания, который напоминает Песочные часы, когда указатель мыши находится на элементе управления, используйте свойство <xref:System.Windows.Forms.Control.UseWaitCursor%2A> класса <xref:System.Windows.Forms.Control>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Cursor>
- [Ввод данных мышью в приложении Windows Forms](mouse-input-in-a-windows-forms-application.md)
- [Функциональная возможность перетаскивания в Windows Forms](drag-and-drop-functionality-in-windows-forms.md)
