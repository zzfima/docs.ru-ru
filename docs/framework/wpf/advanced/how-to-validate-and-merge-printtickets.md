---
title: Практическое руководство. Проверка и слияние PrintTickets
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: 9e5242c07179501e6b39840a36f8dd6364d65b84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918350"
---
# <a name="how-to-validate-and-merge-printtickets"></a>Практическое руководство. Проверка и слияние PrintTickets
[Схема печати](https://go.microsoft.com/fwlink/?LinkId=186397) [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] включает гибкие и расширяемые элементы <xref:System.Printing.PrintCapabilities> и <xref:System.Printing.PrintTicket>. Первый элемент перечисляет возможности устройства печати, а второй указывает, как устройство должно использовать эти возможности в отношении определенной последовательности документов, отдельного документа или отдельной страницы.  
  
 Типичная последовательность задач для приложения, поддерживающего печать, будет выглядеть следующим образом.  
  
1. Определите возможности принтера.  
  
2. <xref:System.Printing.PrintTicket> Настройте для использования этих возможностей.  
  
3. <xref:System.Printing.PrintTicket>Проверьте.  
  
 В этой статье показано, как это сделать.  
  
## <a name="example"></a>Пример  
 В простом примере ниже мы заинтересованы только в том, поддерживает ли принтер двустороннюю печать. Ниже приведены основные шаги.  
  
1. <xref:System.Printing.PrintCapabilities> Получите объект <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> с помощью метода.  
  
2. Проверьте наличие нужных возможностей. В приведенном ниже примере мы проверяем <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> свойство <xref:System.Printing.PrintCapabilities> объекта на наличие возможности печати на обеих сторонах листа бумаги с «поворотом страницы» на длинной стороне листа. Поскольку <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> является коллекцией, мы `Contains` используем метод <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    > Этот шаг не является обязательным. Метод, использованный ниже, будет проверять каждый запрос <xref:System.Printing.PrintTicket> в на соответствие возможностям принтера. <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> Если запрошенная возможность не поддерживается принтером, драйвер принтера заменит альтернативный запрос в, <xref:System.Printing.PrintTicket> возвращенном методом.  
  
3. Если принтер поддерживает двустороннюю печать, в примере кода создается <xref:System.Printing.PrintTicket> запрос, запрашивающий двустороннюю печать. Но в приложении не указываются все возможные параметры принтера, <xref:System.Printing.PrintTicket> доступные в элементе. Это будет непроизводительна как программиста, так и программного времени. Вместо этого код устанавливает только дуплексный запрос, а затем объединяет его <xref:System.Printing.PrintTicket> с существующим, полностью настроенным и <xref:System.Printing.PrintTicket>проверенным, в данном случае, по умолчанию <xref:System.Printing.PrintTicket>пользователем.  
  
4. Соответственно, в примере вызывается <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> метод для слияния нового, минимального и <xref:System.Printing.PrintTicket> пользовательского по умолчанию <xref:System.Printing.PrintTicket>. Он возвращает объект <xref:System.Printing.ValidationResult> , который содержит новый <xref:System.Printing.PrintTicket> как одно из его свойств.  
  
5. Затем в примере проверяется, что <xref:System.Printing.PrintTicket> новые запросы являются дуплексными. Если это так, пример делает его новым билетом печати по умолчанию для пользователя. Если приведенный выше шаг 2 был недоступен и принтер не поддерживал двустороннюю печать вдоль длинной стороны, то проверка привела `false`бы к выполнению. (См. примечание выше.)  
  
6. Последний важный шаг — фиксация изменения <xref:System.Printing.PrintQueue.UserPrintTicket%2A> свойства <xref:System.Printing.PrintQueue> объекта с помощью <xref:System.Printing.PrintQueue.Commit%2A> метода.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Чтобы быстро протестировать этот пример, его оставшаяся часть представлена ниже. Создайте проект и пространство имен, а затем вставьте фрагменты кода из этой статьи в блок пространства имен.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о печати](printing-overview.md)
- [Схема печати](https://go.microsoft.com/fwlink/?LinkId=186397)
