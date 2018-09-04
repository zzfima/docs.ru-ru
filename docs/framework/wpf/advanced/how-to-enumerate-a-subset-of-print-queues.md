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
ms.openlocfilehash: bf45d6fb3fb161ca5171e94b9ab7af1e0e6f0c3d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43562073"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="bbbdb-102">Практическое руководство. Перечисление подмножества очередей печати</span><span class="sxs-lookup"><span data-stu-id="bbbdb-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="bbbdb-103">Это распространенная ситуация, которыми специалистов по информационным технологиям (ИТ), управляющая набором принтеры всей компании сталкиваются состоит в создании списка принтеров, имеющих определенные характеристики.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="bbbdb-104">Эта функциональность обеспечивается <xref:System.Printing.PrintServer.GetPrintQueues%2A> метод <xref:System.Printing.PrintServer> объекта и <xref:System.Printing.EnumeratedPrintQueueTypes> перечисления.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbbdb-105">Пример</span><span class="sxs-lookup"><span data-stu-id="bbbdb-105">Example</span></span>  
 <span data-ttu-id="bbbdb-106">В следующем примере код начинается с создания массив флагов, определяющих характеристики очередей печати, которые требуется внести в список.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="bbbdb-107">В этом примере мы ищем очередей печати, которые устанавливаются локально на сервере печати и являются общими.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="bbbdb-108"><xref:System.Printing.EnumeratedPrintQueueTypes> Перечисление предоставляет множество других возможностей.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="bbbdb-109">Затем он создает <xref:System.Printing.LocalPrintServer> объект, производный от класса <xref:System.Printing.PrintServer>.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="bbbdb-110">Локальный сервер печати — это компьютер, на котором выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="bbbdb-111">Последним значительным шагом является передача массив, в который <xref:System.Printing.PrintServer.GetPrintQueues%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="bbbdb-112">В конечном итоге результаты предоставляются пользователю.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="bbbdb-113">Вы можете расширить этот пример за счет `foreach` цикл, который проходит по каждой очереди печати для дальнейшей блокировки.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="bbbdb-114">Например, можно блокировать принтеры, которые не поддерживают двухсторонней печати, вызвав в цикле каждой очереди печати <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> метод и проверяйте возвращаемое значение наличие блока двусторонней печати.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbbdb-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bbbdb-115">See Also</span></span>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="bbbdb-116">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="bbbdb-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="bbbdb-117">Общие сведения о печати</span><span class="sxs-lookup"><span data-stu-id="bbbdb-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="bbbdb-118">Средство записи документов Microsoft XPS</span><span class="sxs-lookup"><span data-stu-id="bbbdb-118">Microsoft XPS Document Writer</span></span>](https://go.microsoft.com/fwlink/?LinkId=147319)
