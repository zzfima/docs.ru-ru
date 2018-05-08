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
ms.openlocfilehash: 3e616b3b61b4b1b561d5bdb7e51525f391901a22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Практическое руководство. Перечисление подмножества очередей печати
Распространенные ситуации, сталкиваются ИТ-специалистов в области информационных управление всей компании набор принтеры заключается в создании списка принтеров, имеющих определенные характеристики. Эта функциональность обеспечивается <xref:System.Printing.PrintServer.GetPrintQueues%2A> метод <xref:System.Printing.PrintServer> объекта и <xref:System.Printing.EnumeratedPrintQueueTypes> перечисления.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере код начинается с создания массива флагов, определяющих характеристики очередей печати, которые требуется внести в список. В этом примере мы ищем очередей печати, установленные локально на сервере печати и являются общими. <xref:System.Printing.EnumeratedPrintQueueTypes> Перечисление предоставляет множество других возможностей.  
  
 Затем он создает <xref:System.Printing.LocalPrintServer> объекта, класс, производный от <xref:System.Printing.PrintServer>. Локальный сервер печати — компьютер, на котором выполняется приложение.  
  
 Последним значительным шагом является передача массив, в который <xref:System.Printing.PrintServer.GetPrintQueues%2A> метод.  
  
 В конечном итоге результаты предоставляются пользователю.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 Вы можете расширить этот пример, задав `foreach` цикл, который проходит по каждой очереди печати для дальнейшей блокировки. Например, можно блокировать принтеры, которые не поддерживают двусторонней печати, вызвав в цикле каждой очереди печати <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> метод и проверив возвращаемое значение на наличие блока двусторонней печати.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Записи Microsoft XPS-документов](http://go.microsoft.com/fwlink/?LinkId=147319)
