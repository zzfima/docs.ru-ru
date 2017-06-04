---
title: "Практическое руководство. Проверка и слияние PrintTickets | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "слияние объектов PrintTicket"
  - "PrintTicket, слияние"
  - "PrintTicket, проверка"
  - "проверка PrintTicket"
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Проверка и слияние PrintTickets
[Схема печати](http://go.microsoft.com/fwlink/?LinkId=186397) [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] включает гибкие и расширяемые элементы <xref:System.Printing.PrintCapabilities> и <xref:System.Printing.PrintTicket>.  Первый элемент перечисляет возможности устройства печати, а второй указывает, как устройство должно использовать эти возможности по отношению к конкретной последовательности документов, отдельному документу или странице.  
  
 Обычная последовательность задач для приложений, поддерживающих печать, выглядит следующим образом.  
  
1.  Определение возможностей принтера.  
  
2.  Настройка <xref:System.Printing.PrintTicket> для использования этих возможностей.  
  
3.  Проверка <xref:System.Printing.PrintTicket>.  
  
 В данной статье показано, как это сделать.  
  
## Пример  
 В простом примере, приведенном ниже, важно только может ли принтер поддерживать дуплексирование — двустороннюю печать.  Для этого необходимо выполнить следующие шаги.  
  
1.  Получить объект <xref:System.Printing.PrintCapabilities> методом <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>.  
  
2.  Проверить его на наличие требуемой возможности.  В приведенном ниже примере мы проверяем свойство <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> объекта <xref:System.Printing.PrintCapabilities> на наличие возможности печати на обоих сторонах листа бумаги с "переворачиванием страницы" вдоль длинной стороны листа.  Поскольку свойство <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> является коллекцией, используется метод `Contains` класса <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    >  Этот шаг необязателен.  Метод <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>, используемый ниже, будет проверять каждый запрос в <xref:System.Printing.PrintTicket> по возможностям принтера.  Если запрошенная возможность не поддерживается принтером, драйвер принтера заменит альтернативный запрос в <xref:System.Printing.PrintTicket>, возвращаемый при помощи метода.  
  
3.  Если принтер поддерживает дуплексирование, образец кода создает <xref:System.Printing.PrintTicket>, запрашивающий дуплексирование.  Но приложение не указывает каждый возможный параметр принтера, доступный в элементе <xref:System.Printing.PrintTicket>.  Это привело бы к потере времени для программиста и программы.  Вместо этого код устанавливает только запрос дуплексирования, а затем объединяет этот <xref:System.Printing.PrintTicket> с существующим, полностью настроенным и проверенным <xref:System.Printing.PrintTicket>, в этом случае — с <xref:System.Printing.PrintTicket> пользователя по умолчанию.  
  
4.  Соответствующим образом образец вызывает метод <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> для слияния нового, минимального <xref:System.Printing.PrintTicket> с <xref:System.Printing.PrintTicket> пользователя по умолчанию.  Это действие возвращает <xref:System.Printing.ValidationResult>, содержащий новый <xref:System.Printing.PrintTicket> в качестве одного из своих свойств.  
  
5.  Затем образец проверяет, что новый <xref:System.Printing.PrintTicket> запрашивает дуплексирование.  Если это выполняется, то образец делает его новым билетом печати для пользователя по умолчанию.  Если шаг 2 был пропущен, и принтер не поддерживает дуплексирование вдоль длинной стороны, проверка вернет результат `false`.  \(См. примечание выше.\)  
  
6.  Последним значительным шагом является фиксация изменения свойства <xref:System.Printing.PrintQueue.UserPrintTicket%2A> из <xref:System.Printing.PrintQueue> при помощи метода<xref:System.Printing.PrintQueue.Commit%2A>.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 Для быстрой проверки этого примера его оставшаяся часть представлена ниже.  Создайте проект и пространство имен, а затем вставьте фрагменты кода из этого раздела в блок пространства имен.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## См. также  
 <xref:System.Printing.PrintCapabilities>   
 <xref:System.Printing.PrintTicket>   
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>   
 <xref:System.Printing.PrintServer>   
 <xref:System.Printing.EnumeratedPrintQueueTypes>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Print Schema](http://go.microsoft.com/fwlink/?LinkId=186397)