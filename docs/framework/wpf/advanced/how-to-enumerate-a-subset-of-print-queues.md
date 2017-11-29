---
title: "Практическое руководство. Перечисление подмножества очередей печати"
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
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 393d1692526551b1eb9aa16f48d3c78c3cd6692f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="12e25-102">Практическое руководство. Перечисление подмножества очередей печати</span><span class="sxs-lookup"><span data-stu-id="12e25-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="12e25-103">Распространенные ситуации, сталкиваются ИТ-специалистов в области информационных управление всей компании набор принтеры заключается в создании списка принтеров, имеющих определенные характеристики.</span><span class="sxs-lookup"><span data-stu-id="12e25-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="12e25-104">Эта функциональность обеспечивается <xref:System.Printing.PrintServer.GetPrintQueues%2A> метод <xref:System.Printing.PrintServer> объекта и <xref:System.Printing.EnumeratedPrintQueueTypes> перечисления.</span><span class="sxs-lookup"><span data-stu-id="12e25-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12e25-105">Пример</span><span class="sxs-lookup"><span data-stu-id="12e25-105">Example</span></span>  
 <span data-ttu-id="12e25-106">В приведенном ниже примере код начинается с создания массива флагов, определяющих характеристики очередей печати, которые требуется внести в список.</span><span class="sxs-lookup"><span data-stu-id="12e25-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="12e25-107">В этом примере мы ищем очередей печати, установленные локально на сервере печати и являются общими.</span><span class="sxs-lookup"><span data-stu-id="12e25-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="12e25-108"><xref:System.Printing.EnumeratedPrintQueueTypes> Перечисление предоставляет множество других возможностей.</span><span class="sxs-lookup"><span data-stu-id="12e25-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="12e25-109">Затем он создает <xref:System.Printing.LocalPrintServer> объекта, класс, производный от <xref:System.Printing.PrintServer>.</span><span class="sxs-lookup"><span data-stu-id="12e25-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="12e25-110">Локальный сервер печати — компьютер, на котором выполняется приложение.</span><span class="sxs-lookup"><span data-stu-id="12e25-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="12e25-111">Последним значительным шагом является передача массив, в который <xref:System.Printing.PrintServer.GetPrintQueues%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="12e25-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="12e25-112">В конечном итоге результаты предоставляются пользователю.</span><span class="sxs-lookup"><span data-stu-id="12e25-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="12e25-113">Вы можете расширить этот пример, задав `foreach` цикл, который проходит по каждой очереди печати для дальнейшей блокировки.</span><span class="sxs-lookup"><span data-stu-id="12e25-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="12e25-114">Например, можно блокировать принтеры, которые не поддерживают двусторонней печати, вызвав в цикле каждой очереди печати <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> метод и проверив возвращаемое значение на наличие блока двусторонней печати.</span><span class="sxs-lookup"><span data-stu-id="12e25-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e25-115">См. также</span><span class="sxs-lookup"><span data-stu-id="12e25-115">See Also</span></span>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="12e25-116">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="12e25-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="12e25-117">Общие сведения о печати</span><span class="sxs-lookup"><span data-stu-id="12e25-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="12e25-118">Записи Microsoft XPS-документов</span><span class="sxs-lookup"><span data-stu-id="12e25-118">Microsoft XPS Document Writer</span></span>](http://go.microsoft.com/fwlink/?LinkId=147319)
