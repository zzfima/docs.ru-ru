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
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="bf3ff-102">Практическое руководство. Перечисление подмножества очередей печати</span><span class="sxs-lookup"><span data-stu-id="bf3ff-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="bf3ff-103">Распространенной ситуацией, с которой сталкиваются специалисты по информационным технологиям, управляющие корпоративным набором принтеров, является создание списка принтеров с определенными характеристиками.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="bf3ff-104">Эта функциональность обеспечивается методом <xref:System.Printing.PrintServer.GetPrintQueues%2A> объекта <xref:System.Printing.PrintServer> и перечислением <xref:System.Printing.EnumeratedPrintQueueTypes>.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf3ff-105">Пример</span><span class="sxs-lookup"><span data-stu-id="bf3ff-105">Example</span></span>  
 <span data-ttu-id="bf3ff-106">В приведенном ниже примере код начинается с создания массива флагов, указывающих характеристики очередей печати, которые нужно вывести в список.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="bf3ff-107">В этом примере мы ищем очереди печати, которые установлены локально на сервере печати и являются общими.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="bf3ff-108">Перечисление <xref:System.Printing.EnumeratedPrintQueueTypes> предоставляет множество других возможностей.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="bf3ff-109">Затем код создает объект <xref:System.Printing.LocalPrintServer> — класс, производный от <xref:System.Printing.PrintServer>.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="bf3ff-110">Локальный сервер печати — это компьютер, на котором работает приложение.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="bf3ff-111">Последний важный шаг — передать массив методу <xref:System.Printing.PrintServer.GetPrintQueues%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="bf3ff-112">В конечном итоге результаты предоставляются пользователю.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="bf3ff-113">Этот пример можно расширить, получив цикл `foreach`, который проходит по каждой очереди печати и выполняет дальнейший отбор.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="bf3ff-114">Например, можно вывести на экран принтеры, не поддерживающие двустороннюю печать, вызвав каждый метод <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> очереди печати и протестировать возвращаемое значение для обеспечения двусторонней печати.</span><span class="sxs-lookup"><span data-stu-id="bf3ff-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3ff-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bf3ff-115">See also</span></span>

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="bf3ff-116">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="bf3ff-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="bf3ff-117">Общие сведения о печати</span><span class="sxs-lookup"><span data-stu-id="bf3ff-117">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="bf3ff-118">Средство записи документов XPS (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="bf3ff-118">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
