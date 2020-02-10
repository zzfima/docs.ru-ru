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
ms.openlocfilehash: bd7f399555b343a52ec6f36aa3b8c706747d8b06
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094531"
---
# <a name="how-to-validate-and-merge-printtickets"></a>Практическое руководство. Проверка и слияние PrintTickets
[Схема печати](/windows/win32/printdocs/printschema) Microsoft Windows включает гибкие и расширяемые элементы <xref:System.Printing.PrintCapabilities> и <xref:System.Printing.PrintTicket>. Первый элемент перечисляет возможности устройства печати, а второй указывает, как устройство должно использовать эти возможности в отношении определенной последовательности документов, отдельного документа или отдельной страницы.  
  
 Типичная последовательность задач для приложения, поддерживающего печать, будет выглядеть следующим образом.  
  
1. Определите возможности принтера.  
  
2. Настройте <xref:System.Printing.PrintTicket> для использования этих возможностей.  
  
3. Проверьте <xref:System.Printing.PrintTicket>.  
  
 В этой статье показано, как это сделать.  
  
## <a name="example"></a>Пример  
 В простом примере ниже мы заинтересованы только в том, поддерживает ли принтер двустороннюю печать. Ниже приведены основные шаги.  
  
1. Получите объект <xref:System.Printing.PrintCapabilities> с помощью метода <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>.  
  
2. Проверьте наличие нужных возможностей. В приведенном ниже примере мы протестируем свойство <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> объекта <xref:System.Printing.PrintCapabilities> на наличие возможности печати на обеих сторонах листа бумаги с «поворотом страницы» на длинной стороне листа. Поскольку <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> является коллекцией, мы используем метод `Contains` <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    > Этот шаг не является обязательным. Используемый ниже метод <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> будет проверять каждый запрос в <xref:System.Printing.PrintTicket> на соответствие возможностям принтера. Если запрошенная возможность не поддерживается принтером, драйвер принтера заменит альтернативный запрос в <xref:System.Printing.PrintTicket>, возвращаемый методом.  
  
3. Если принтер поддерживает двустороннюю печать, в примере кода создается <xref:System.Printing.PrintTicket> с запросом на двустороннюю печать. Но в приложении не указываются все возможные параметры принтера, доступные в элементе <xref:System.Printing.PrintTicket>. Это будет непроизводительна как программиста, так и программного времени. Вместо этого код задает только дуплексный запрос, а затем объединяет этот <xref:System.Printing.PrintTicket> с существующим, полностью настроенным и проверенным, <xref:System.Printing.PrintTicket>в данном случае <xref:System.Printing.PrintTicket>пользователя по умолчанию.  
  
4. Соответственно, в примере вызывается метод <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> для слияния нового, минимального <xref:System.Printing.PrintTicket> с <xref:System.Printing.PrintTicket>ом по умолчанию пользователя. Он возвращает <xref:System.Printing.ValidationResult>, включающий в себя новый <xref:System.Printing.PrintTicket> в качестве одного из его свойств.  
  
5. Затем в примере проверяется, что новый <xref:System.Printing.PrintTicket> запрашивает двустороннюю печать. Если это так, пример делает его новым билетом печати по умолчанию для пользователя. Если приведенный выше шаг 2 был оставлен и принтер не поддерживал двустороннюю печать вдоль длинной стороны, то тест привел бы к `false`у. (См. примечание выше.)  
  
6. Последний важный шаг — фиксация изменения свойства <xref:System.Printing.PrintQueue.UserPrintTicket%2A> <xref:System.Printing.PrintQueue> с помощью метода <xref:System.Printing.PrintQueue.Commit%2A>.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Чтобы быстро протестировать этот пример, его оставшаяся часть представлена ниже. Создайте проект и пространство имен, а затем вставьте фрагменты кода из этой статьи в блок пространства имен.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Документы в WPF](documents-in-wpf.md)
- [Общие сведения о печати](printing-overview.md)
- [Схема печати](/windows/win32/printdocs/printschema)
