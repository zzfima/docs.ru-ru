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
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="6ec78-102">Практическое руководство. Проверка и слияние PrintTickets</span><span class="sxs-lookup"><span data-stu-id="6ec78-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="6ec78-103">[Схема печати](/windows/win32/printdocs/printschema) Microsoft Windows включает гибкие и расширяемые элементы <xref:System.Printing.PrintCapabilities> и <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="6ec78-103">The Microsoft Windows [Print Schema](/windows/win32/printdocs/printschema) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="6ec78-104">Первый элемент перечисляет возможности устройства печати, а второй указывает, как устройство должно использовать эти возможности в отношении определенной последовательности документов, отдельного документа или отдельной страницы.</span><span class="sxs-lookup"><span data-stu-id="6ec78-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="6ec78-105">Типичная последовательность задач для приложения, поддерживающего печать, будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6ec78-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1. <span data-ttu-id="6ec78-106">Определите возможности принтера.</span><span class="sxs-lookup"><span data-stu-id="6ec78-106">Determine a printer's capabilities.</span></span>  
  
2. <span data-ttu-id="6ec78-107">Настройте <xref:System.Printing.PrintTicket> для использования этих возможностей.</span><span class="sxs-lookup"><span data-stu-id="6ec78-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3. <span data-ttu-id="6ec78-108">Проверьте <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="6ec78-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="6ec78-109">В этой статье показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="6ec78-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ec78-110">Пример</span><span class="sxs-lookup"><span data-stu-id="6ec78-110">Example</span></span>  
 <span data-ttu-id="6ec78-111">В простом примере ниже мы заинтересованы только в том, поддерживает ли принтер двустороннюю печать.</span><span class="sxs-lookup"><span data-stu-id="6ec78-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="6ec78-112">Ниже приведены основные шаги.</span><span class="sxs-lookup"><span data-stu-id="6ec78-112">The major steps are as follows.</span></span>  
  
1. <span data-ttu-id="6ec78-113">Получите объект <xref:System.Printing.PrintCapabilities> с помощью метода <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ec78-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2. <span data-ttu-id="6ec78-114">Проверьте наличие нужных возможностей.</span><span class="sxs-lookup"><span data-stu-id="6ec78-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="6ec78-115">В приведенном ниже примере мы протестируем свойство <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> объекта <xref:System.Printing.PrintCapabilities> на наличие возможности печати на обеих сторонах листа бумаги с «поворотом страницы» на длинной стороне листа.</span><span class="sxs-lookup"><span data-stu-id="6ec78-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="6ec78-116">Поскольку <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> является коллекцией, мы используем метод `Contains` <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="6ec78-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6ec78-117">Этот шаг не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="6ec78-117">This step is not strictly necessary.</span></span> <span data-ttu-id="6ec78-118">Используемый ниже метод <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> будет проверять каждый запрос в <xref:System.Printing.PrintTicket> на соответствие возможностям принтера.</span><span class="sxs-lookup"><span data-stu-id="6ec78-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="6ec78-119">Если запрошенная возможность не поддерживается принтером, драйвер принтера заменит альтернативный запрос в <xref:System.Printing.PrintTicket>, возвращаемый методом.</span><span class="sxs-lookup"><span data-stu-id="6ec78-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3. <span data-ttu-id="6ec78-120">Если принтер поддерживает двустороннюю печать, в примере кода создается <xref:System.Printing.PrintTicket> с запросом на двустороннюю печать.</span><span class="sxs-lookup"><span data-stu-id="6ec78-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="6ec78-121">Но в приложении не указываются все возможные параметры принтера, доступные в элементе <xref:System.Printing.PrintTicket>.</span><span class="sxs-lookup"><span data-stu-id="6ec78-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="6ec78-122">Это будет непроизводительна как программиста, так и программного времени.</span><span class="sxs-lookup"><span data-stu-id="6ec78-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="6ec78-123">Вместо этого код задает только дуплексный запрос, а затем объединяет этот <xref:System.Printing.PrintTicket> с существующим, полностью настроенным и проверенным, <xref:System.Printing.PrintTicket>в данном случае <xref:System.Printing.PrintTicket>пользователя по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6ec78-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4. <span data-ttu-id="6ec78-124">Соответственно, в примере вызывается метод <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> для слияния нового, минимального <xref:System.Printing.PrintTicket> с <xref:System.Printing.PrintTicket>ом по умолчанию пользователя.</span><span class="sxs-lookup"><span data-stu-id="6ec78-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="6ec78-125">Он возвращает <xref:System.Printing.ValidationResult>, включающий в себя новый <xref:System.Printing.PrintTicket> в качестве одного из его свойств.</span><span class="sxs-lookup"><span data-stu-id="6ec78-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5. <span data-ttu-id="6ec78-126">Затем в примере проверяется, что новый <xref:System.Printing.PrintTicket> запрашивает двустороннюю печать.</span><span class="sxs-lookup"><span data-stu-id="6ec78-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="6ec78-127">Если это так, пример делает его новым билетом печати по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="6ec78-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="6ec78-128">Если приведенный выше шаг 2 был оставлен и принтер не поддерживал двустороннюю печать вдоль длинной стороны, то тест привел бы к `false`у.</span><span class="sxs-lookup"><span data-stu-id="6ec78-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="6ec78-129">(См. примечание выше.)</span><span class="sxs-lookup"><span data-stu-id="6ec78-129">(See the note above.)</span></span>  
  
6. <span data-ttu-id="6ec78-130">Последний важный шаг — фиксация изменения свойства <xref:System.Printing.PrintQueue.UserPrintTicket%2A> <xref:System.Printing.PrintQueue> с помощью метода <xref:System.Printing.PrintQueue.Commit%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ec78-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="6ec78-131">Чтобы быстро протестировать этот пример, его оставшаяся часть представлена ниже.</span><span class="sxs-lookup"><span data-stu-id="6ec78-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="6ec78-132">Создайте проект и пространство имен, а затем вставьте фрагменты кода из этой статьи в блок пространства имен.</span><span class="sxs-lookup"><span data-stu-id="6ec78-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="6ec78-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6ec78-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="6ec78-134">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="6ec78-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="6ec78-135">Общие сведения о печати</span><span class="sxs-lookup"><span data-stu-id="6ec78-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="6ec78-136">Схема печати</span><span class="sxs-lookup"><span data-stu-id="6ec78-136">Print Schema</span></span>](/windows/win32/printdocs/printschema)
