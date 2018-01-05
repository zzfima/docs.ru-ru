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
ms.workload: dotnet
ms.openlocfilehash: e5cf2091d50433bb936b3d4976d1c3eabea73edc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="78456-102">Практическое руководство. Проверка и слияние PrintTickets</span><span class="sxs-lookup"><span data-stu-id="78456-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="78456-103">[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Схеме печати](http://go.microsoft.com/fwlink/?LinkId=186397) включает гибкой и расширяемой <xref:System.Printing.PrintCapabilities> и <xref:System.Printing.PrintTicket> элементы.</span><span class="sxs-lookup"><span data-stu-id="78456-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](http://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="78456-104">Первый элемент перечисляет возможности устройства печати, а второй указывает, как устройство должно использовать эти возможности по отношению к конкретная последовательность документов, отдельного документа или отдельных страниц.</span><span class="sxs-lookup"><span data-stu-id="78456-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="78456-105">Типичная последовательность задач для приложений, поддерживающий печать будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="78456-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1.  <span data-ttu-id="78456-106">Определите возможности принтера.</span><span class="sxs-lookup"><span data-stu-id="78456-106">Determine a printer's capabilities.</span></span>  
  
2.  <span data-ttu-id="78456-107">Настройка <xref:System.Printing.PrintTicket> для использования этих возможностей.</span><span class="sxs-lookup"><span data-stu-id="78456-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3.  <span data-ttu-id="78456-108">Проверка <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="78456-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="78456-109">В этой статье показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="78456-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78456-110">Пример</span><span class="sxs-lookup"><span data-stu-id="78456-110">Example</span></span>  
 <span data-ttu-id="78456-111">В простом примере нас интересуют только ли принтер может поддерживать двусторонней — двусторонней печати.</span><span class="sxs-lookup"><span data-stu-id="78456-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="78456-112">Ниже приведены основные шаги.</span><span class="sxs-lookup"><span data-stu-id="78456-112">The major steps are as follows.</span></span>  
  
1.  <span data-ttu-id="78456-113">Получить <xref:System.Printing.PrintCapabilities> объекта с <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="78456-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2.  <span data-ttu-id="78456-114">Для проверки наличия возможности, которые нужно.</span><span class="sxs-lookup"><span data-stu-id="78456-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="78456-115">В приведенном ниже примере мы тестируем <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> свойство <xref:System.Printing.PrintCapabilities> объекта на наличие возможности печати на обеих сторонах листа бумаги с «Включение страницы» вдоль длинной стороны листа.</span><span class="sxs-lookup"><span data-stu-id="78456-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="78456-116">Поскольку <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> — это коллекция мы используем `Contains` метод <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="78456-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="78456-117">Этот шаг не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="78456-117">This step is not strictly necessary.</span></span> <span data-ttu-id="78456-118"><xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> Метод, используемый ниже будет проверять каждый запрос <xref:System.Printing.PrintTicket> от возможностей используемого принтера.</span><span class="sxs-lookup"><span data-stu-id="78456-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="78456-119">Если запрошенная возможность не поддерживается принтером, драйвер принтера заменит альтернативный запрос в <xref:System.Printing.PrintTicket> возвращаемая этим методом.</span><span class="sxs-lookup"><span data-stu-id="78456-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3.  <span data-ttu-id="78456-120">Если принтер поддерживает двусторонней печати, в примере кода создается <xref:System.Printing.PrintTicket> , запрашивающий двусторонней печати.</span><span class="sxs-lookup"><span data-stu-id="78456-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="78456-121">Но приложение не указывает каждый возможный параметр принтера, доступных в <xref:System.Printing.PrintTicket> элемент.</span><span class="sxs-lookup"><span data-stu-id="78456-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="78456-122">Это было бы затратные программист и программа время.</span><span class="sxs-lookup"><span data-stu-id="78456-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="78456-123">Вместо этого код устанавливает только запрос двусторонней печати, а затем объединяет этот <xref:System.Printing.PrintTicket> с существующим, полностью настроена и проверки <xref:System.Printing.PrintTicket>в данном случае пользователя по умолчанию <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="78456-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4.  <span data-ttu-id="78456-124">Соответственно, в образце вызывается <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> метод для слияния нового, минимальное количество — <xref:System.Printing.PrintTicket> пользователя по умолчанию <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="78456-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="78456-125">Возвращает <xref:System.Printing.ValidationResult> , содержащий новый <xref:System.Printing.PrintTicket> как один из его свойств.</span><span class="sxs-lookup"><span data-stu-id="78456-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5.  <span data-ttu-id="78456-126">Затем проверяет образец, новый <xref:System.Printing.PrintTicket> запрашивает двусторонней печати.</span><span class="sxs-lookup"><span data-stu-id="78456-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="78456-127">Если это так, то в этом образце он новый билет печати по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="78456-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="78456-128">Если шаг 2 был пропущен и принтер не поддерживает дублирование вдоль длинной стороны, а затем теста могло привести к `false`.</span><span class="sxs-lookup"><span data-stu-id="78456-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="78456-129">(См. Примечание выше).</span><span class="sxs-lookup"><span data-stu-id="78456-129">(See the note above.)</span></span>  
  
6.  <span data-ttu-id="78456-130">Значительные осталось для фиксации изменений к <xref:System.Printing.PrintQueue.UserPrintTicket%2A> свойство <xref:System.Printing.PrintQueue> с <xref:System.Printing.PrintQueue.Commit%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="78456-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="78456-131">Чтобы быстро проверкой этого примера его оставшаяся часть представлена ниже.</span><span class="sxs-lookup"><span data-stu-id="78456-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="78456-132">Создайте проект и пространство имен и затем вставить фрагменты кода в этой статье в блок пространства имен.</span><span class="sxs-lookup"><span data-stu-id="78456-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="78456-133">См. также</span><span class="sxs-lookup"><span data-stu-id="78456-133">See Also</span></span>  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="78456-134">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="78456-134">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="78456-135">Общие сведения о печати</span><span class="sxs-lookup"><span data-stu-id="78456-135">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="78456-136">Схема печати</span><span class="sxs-lookup"><span data-stu-id="78456-136">Print Schema</span></span>](http://go.microsoft.com/fwlink/?LinkId=186397)
