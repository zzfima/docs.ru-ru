---
title: "Практическое руководство. Проверка и слияние PrintTickets"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a2c2929f37895f0dee5529a5bf90f84146585032
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-and-merge-printtickets"></a>Практическое руководство. Проверка и слияние PrintTickets
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Схеме печати](http://go.microsoft.com/fwlink/?LinkId=186397) включает гибкой и расширяемой <xref:System.Printing.PrintCapabilities> и <xref:System.Printing.PrintTicket> элементы. Первый элемент перечисляет возможности устройства печати, а второй указывает, как устройство должно использовать эти возможности по отношению к конкретная последовательность документов, отдельного документа или отдельных страниц.  
  
 Типичная последовательность задач для приложений, поддерживающий печать будет выглядеть следующим образом.  
  
1.  Определите возможности принтера.  
  
2.  Настройка <xref:System.Printing.PrintTicket> для использования этих возможностей.  
  
3.  Проверка <xref:System.Printing.PrintTicket>.  
  
 В этой статье показано, как это сделать.  
  
## <a name="example"></a>Пример  
 В простом примере нас интересуют только ли принтер может поддерживать двусторонней — двусторонней печати. Ниже приведены основные шаги.  
  
1.  Получить <xref:System.Printing.PrintCapabilities> объекта с <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> метод.  
  
2.  Для проверки наличия возможности, которые нужно. В приведенном ниже примере мы тестируем <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> свойство <xref:System.Printing.PrintCapabilities> объекта на наличие возможности печати на обеих сторонах листа бумаги с «Включение страницы» вдоль длинной стороны листа. Поскольку <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> — это коллекция мы используем `Contains` метод <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    >  Этот шаг не является обязательным. <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> Метод, используемый ниже будет проверять каждый запрос <xref:System.Printing.PrintTicket> от возможностей используемого принтера. Если запрошенная возможность не поддерживается принтером, драйвер принтера заменит альтернативный запрос в <xref:System.Printing.PrintTicket> возвращаемая этим методом.  
  
3.  Если принтер поддерживает двусторонней печати, в примере кода создается <xref:System.Printing.PrintTicket> , запрашивающий двусторонней печати. Но приложение не указывает каждый возможный параметр принтера, доступных в <xref:System.Printing.PrintTicket> элемент. Это было бы затратные программист и программа время. Вместо этого код устанавливает только запрос двусторонней печати, а затем объединяет этот <xref:System.Printing.PrintTicket> с существующим, полностью настроена и проверки <xref:System.Printing.PrintTicket>в данном случае пользователя по умолчанию <xref:System.Printing.PrintTicket>.  
  
4.  Соответственно, в образце вызывается <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> метод для слияния нового, минимальное количество — <xref:System.Printing.PrintTicket> пользователя по умолчанию <xref:System.Printing.PrintTicket>. Возвращает <xref:System.Printing.ValidationResult> , содержащий новый <xref:System.Printing.PrintTicket> как один из его свойств.  
  
5.  Затем проверяет образец, новый <xref:System.Printing.PrintTicket> запрашивает двусторонней печати. Если это так, то в этом образце он новый билет печати по умолчанию для пользователя. Если шаг 2 был пропущен и принтер не поддерживает дублирование вдоль длинной стороны, а затем теста могло привести к `false`. (См. Примечание выше).  
  
6.  Значительные осталось для фиксации изменений к <xref:System.Printing.PrintQueue.UserPrintTicket%2A> свойство <xref:System.Printing.PrintQueue> с <xref:System.Printing.PrintQueue.Commit%2A> метод.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Чтобы быстро проверкой этого примера его оставшаяся часть представлена ниже. Создайте проект и пространство имен и затем вставить фрагменты кода в этой статье в блок пространства имен.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Схема печати](http://go.microsoft.com/fwlink/?LinkId=186397)
