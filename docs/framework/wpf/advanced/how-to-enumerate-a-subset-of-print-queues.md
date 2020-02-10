---
title: Практическое руководство. Перечисление подмножества очередей печати
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: aae41931f012f6d34fc057fdd6ee9fc9baab6e7b
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094544"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Практическое руководство. Перечисление подмножества очередей печати
Распространенной ситуацией, с которой сталкиваются специалисты по информационным технологиям, управляющие корпоративным набором принтеров, является создание списка принтеров с определенными характеристиками. Эта функциональность обеспечивается методом <xref:System.Printing.PrintServer.GetPrintQueues%2A> объекта <xref:System.Printing.PrintServer> и перечислением <xref:System.Printing.EnumeratedPrintQueueTypes>.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере код начинается с создания массива флагов, указывающих характеристики очередей печати, которые нужно вывести в список. В этом примере мы ищем очереди печати, которые установлены локально на сервере печати и являются общими. Перечисление <xref:System.Printing.EnumeratedPrintQueueTypes> предоставляет множество других возможностей.  
  
 Затем код создает объект <xref:System.Printing.LocalPrintServer> — класс, производный от <xref:System.Printing.PrintServer>. Локальный сервер печати — это компьютер, на котором работает приложение.  
  
 Последний важный шаг — передать массив методу <xref:System.Printing.PrintServer.GetPrintQueues%2A>.  
  
 В конечном итоге результаты предоставляются пользователю.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Этот пример можно расширить, получив цикл `foreach`, который проходит по каждой очереди печати и выполняет дальнейший отбор. Например, можно вывести на экран принтеры, не поддерживающие двустороннюю печать, вызвав каждый метод <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> очереди печати и протестировать возвращаемое значение для обеспечения двусторонней печати.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о печати](printing-overview.md)
- [Средство записи документов XPS (Майкрософт)](/windows/win32/printdocs/microsoft-xps-document-writer)
