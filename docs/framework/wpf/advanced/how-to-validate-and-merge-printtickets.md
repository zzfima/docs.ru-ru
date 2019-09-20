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
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="b01e4-102">Практическое руководство. Проверка и слияние PrintTickets</span><span class="sxs-lookup"><span data-stu-id="b01e4-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="b01e4-103">[Схема печати](https://go.microsoft.com/fwlink/?LinkId=186397) [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] включает гибкие и расширяемые элементы <xref:System.Printing.PrintCapabilities> и <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="b01e4-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="b01e4-104">Первый элемент перечисляет возможности устройства печати, а второй указывает, как устройство должно использовать эти возможности в отношении определенной последовательности документов, отдельного документа или отдельной страницы.</span><span class="sxs-lookup"><span data-stu-id="b01e4-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="b01e4-105">Типичная последовательность задач для приложения, поддерживающего печать, будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="b01e4-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1. <span data-ttu-id="b01e4-106">Определите возможности принтера.</span><span class="sxs-lookup"><span data-stu-id="b01e4-106">Determine a printer's capabilities.</span></span>  
  
2. <span data-ttu-id="b01e4-107"><xref:System.Printing.PrintTicket> Настройте для использования этих возможностей.</span><span class="sxs-lookup"><span data-stu-id="b01e4-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3. <span data-ttu-id="b01e4-108"><xref:System.Printing.PrintTicket>Проверьте.</span><span class="sxs-lookup"><span data-stu-id="b01e4-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="b01e4-109">В этой статье показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="b01e4-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b01e4-110">Пример</span><span class="sxs-lookup"><span data-stu-id="b01e4-110">Example</span></span>  
 <span data-ttu-id="b01e4-111">В простом примере ниже мы заинтересованы только в том, поддерживает ли принтер двустороннюю печать.</span><span class="sxs-lookup"><span data-stu-id="b01e4-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="b01e4-112">Ниже приведены основные шаги.</span><span class="sxs-lookup"><span data-stu-id="b01e4-112">The major steps are as follows.</span></span>  
  
1. <span data-ttu-id="b01e4-113"><xref:System.Printing.PrintCapabilities> Получите объект <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> с помощью метода.</span><span class="sxs-lookup"><span data-stu-id="b01e4-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2. <span data-ttu-id="b01e4-114">Проверьте наличие нужных возможностей.</span><span class="sxs-lookup"><span data-stu-id="b01e4-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="b01e4-115">В приведенном ниже примере мы проверяем <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> свойство <xref:System.Printing.PrintCapabilities> объекта на наличие возможности печати на обеих сторонах листа бумаги с «поворотом страницы» на длинной стороне листа.</span><span class="sxs-lookup"><span data-stu-id="b01e4-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="b01e4-116">Поскольку <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> является коллекцией, мы `Contains` используем метод <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="b01e4-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="b01e4-117">Этот шаг не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="b01e4-117">This step is not strictly necessary.</span></span> <span data-ttu-id="b01e4-118">Метод, использованный ниже, будет проверять каждый запрос <xref:System.Printing.PrintTicket> в на соответствие возможностям принтера. <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A></span><span class="sxs-lookup"><span data-stu-id="b01e4-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="b01e4-119">Если запрошенная возможность не поддерживается принтером, драйвер принтера заменит альтернативный запрос в, <xref:System.Printing.PrintTicket> возвращенном методом.</span><span class="sxs-lookup"><span data-stu-id="b01e4-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3. <span data-ttu-id="b01e4-120">Если принтер поддерживает двустороннюю печать, в примере кода создается <xref:System.Printing.PrintTicket> запрос, запрашивающий двустороннюю печать.</span><span class="sxs-lookup"><span data-stu-id="b01e4-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="b01e4-121">Но в приложении не указываются все возможные параметры принтера, <xref:System.Printing.PrintTicket> доступные в элементе.</span><span class="sxs-lookup"><span data-stu-id="b01e4-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="b01e4-122">Это будет непроизводительна как программиста, так и программного времени.</span><span class="sxs-lookup"><span data-stu-id="b01e4-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="b01e4-123">Вместо этого код устанавливает только дуплексный запрос, а затем объединяет его <xref:System.Printing.PrintTicket> с существующим, полностью настроенным и <xref:System.Printing.PrintTicket>проверенным, в данном случае, по умолчанию <xref:System.Printing.PrintTicket>пользователем.</span><span class="sxs-lookup"><span data-stu-id="b01e4-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4. <span data-ttu-id="b01e4-124">Соответственно, в примере вызывается <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> метод для слияния нового, минимального и <xref:System.Printing.PrintTicket> пользовательского по умолчанию <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="b01e4-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="b01e4-125">Он возвращает объект <xref:System.Printing.ValidationResult> , который содержит новый <xref:System.Printing.PrintTicket> как одно из его свойств.</span><span class="sxs-lookup"><span data-stu-id="b01e4-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5. <span data-ttu-id="b01e4-126">Затем в примере проверяется, что <xref:System.Printing.PrintTicket> новые запросы являются дуплексными.</span><span class="sxs-lookup"><span data-stu-id="b01e4-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="b01e4-127">Если это так, пример делает его новым билетом печати по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b01e4-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="b01e4-128">Если приведенный выше шаг 2 был недоступен и принтер не поддерживал двустороннюю печать вдоль длинной стороны, то проверка привела `false`бы к выполнению.</span><span class="sxs-lookup"><span data-stu-id="b01e4-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="b01e4-129">(См. примечание выше.)</span><span class="sxs-lookup"><span data-stu-id="b01e4-129">(See the note above.)</span></span>  
  
6. <span data-ttu-id="b01e4-130">Последний важный шаг — фиксация изменения <xref:System.Printing.PrintQueue.UserPrintTicket%2A> свойства <xref:System.Printing.PrintQueue> объекта с помощью <xref:System.Printing.PrintQueue.Commit%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="b01e4-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="b01e4-131">Чтобы быстро протестировать этот пример, его оставшаяся часть представлена ниже.</span><span class="sxs-lookup"><span data-stu-id="b01e4-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="b01e4-132">Создайте проект и пространство имен, а затем вставьте фрагменты кода из этой статьи в блок пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b01e4-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="b01e4-133">См. также</span><span class="sxs-lookup"><span data-stu-id="b01e4-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="b01e4-134">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="b01e4-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="b01e4-135">Общие сведения о печати</span><span class="sxs-lookup"><span data-stu-id="b01e4-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="b01e4-136">Схема печати</span><span class="sxs-lookup"><span data-stu-id="b01e4-136">Print Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=186397)
