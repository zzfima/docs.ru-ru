---
title: Практическое руководство. Удаленный опрос состояний принтеров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
ms.openlocfilehash: 0a7756684d5a133fa9cb014f109d14e413223ea9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945228"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="99f21-102">Практическое руководство. Удаленный опрос состояний принтеров</span><span class="sxs-lookup"><span data-stu-id="99f21-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="99f21-103">В средних и крупных компаниях могут возникнуть ситуации, когда из-за замятия или отсутствия бумаги либо по иным причинам не работают сразу несколько принтеров.</span><span class="sxs-lookup"><span data-stu-id="99f21-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="99f21-104">Широкий набор свойств принтера, предоставляемых API Microsoft .NET Framework, предоставляет средства для быстрого опроса состояний принтеров.</span><span class="sxs-lookup"><span data-stu-id="99f21-104">The rich set of printer properties exposed in the APIs of Microsoft .NET Framework provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99f21-105">Пример</span><span class="sxs-lookup"><span data-stu-id="99f21-105">Example</span></span>  
 <span data-ttu-id="99f21-106">Ниже представлены основные этапы создания подобной служебной программы.</span><span class="sxs-lookup"><span data-stu-id="99f21-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1. <span data-ttu-id="99f21-107">Получите список всех серверов печати.</span><span class="sxs-lookup"><span data-stu-id="99f21-107">Obtain a list of all print servers.</span></span>  
  
2. <span data-ttu-id="99f21-108">Выполните циклический просмотр всех серверов, чтобы запросить их очереди печати.</span><span class="sxs-lookup"><span data-stu-id="99f21-108">Loop through the servers to query their print queues.</span></span>  
  
3. <span data-ttu-id="99f21-109">Для каждого сервера выполните циклический просмотр всех очередей сервера и прочтите каждое свойство, которое может указывать на то, что очередь в данный момент не работает.</span><span class="sxs-lookup"><span data-stu-id="99f21-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="99f21-110">Представленный ниже код представляет собой набор фрагментов.</span><span class="sxs-lookup"><span data-stu-id="99f21-110">The code below is a series of snippets.</span></span> <span data-ttu-id="99f21-111">Для простоты в этом примере предполагается наличие списка серверов печати, разделенного символами перевода строки.</span><span class="sxs-lookup"><span data-stu-id="99f21-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="99f21-112">`fileOfPrintServers` Переменная<xref:System.IO.StreamReader> является объектом для этого файла.</span><span class="sxs-lookup"><span data-stu-id="99f21-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="99f21-113">Поскольку каждое имя сервера находится в отдельной строке, любой вызов <xref:System.IO.StreamReader.ReadLine%2A> получает имя следующего сервера и <xref:System.IO.StreamReader>перемещает курсор в начало следующей строки.</span><span class="sxs-lookup"><span data-stu-id="99f21-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="99f21-114">Во внешнем цикле код создает <xref:System.Printing.PrintServer> объект для последнего сервера печати и указывает, что приложение имеет права администратора на сервере.</span><span class="sxs-lookup"><span data-stu-id="99f21-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="99f21-115">При наличии большого количества серверов можно повысить производительность с помощью <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> конструкторов, которые только инициализируют нужные свойства.</span><span class="sxs-lookup"><span data-stu-id="99f21-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="99f21-116">Затем в примере используется <xref:System.Printing.PrintServer.GetPrintQueues%2A> для создания коллекции всех очередей сервера и начинается их цикл.</span><span class="sxs-lookup"><span data-stu-id="99f21-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="99f21-117">Этот внутренний цикл содержит структуру ветвления, соответствующую двум способам проверки состояния принтера:</span><span class="sxs-lookup"><span data-stu-id="99f21-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
- <span data-ttu-id="99f21-118">Можно прочитать флаги <xref:System.Printing.PrintQueue.QueueStatus%2A> свойства, имеющего тип <xref:System.Printing.PrintQueueStatus>.</span><span class="sxs-lookup"><span data-stu-id="99f21-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
- <span data-ttu-id="99f21-119">Можно прочитать каждое соответствующее свойство <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, например, и. <xref:System.Printing.PrintQueue.IsPaperJammed%2A></span><span class="sxs-lookup"><span data-stu-id="99f21-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="99f21-120">В этом примере демонстрируются оба метода, поэтому пользователю ранее было предложено, какой метод использовать, и ответил "y", если ему нужно использовать флаги <xref:System.Printing.PrintQueue.QueueStatus%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="99f21-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if he or she wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="99f21-121">Ниже представлены подробные сведения об этих двух методах.</span><span class="sxs-lookup"><span data-stu-id="99f21-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="99f21-122">В конечном итоге результаты предоставляются пользователю.</span><span class="sxs-lookup"><span data-stu-id="99f21-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="99f21-123">Чтобы проверить состояние принтера с помощью флагов <xref:System.Printing.PrintQueue.QueueStatus%2A> свойства, необходимо проверить каждый соответствующий флаг, чтобы проверить, задан ли он.</span><span class="sxs-lookup"><span data-stu-id="99f21-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="99f21-124">Обычно определить, задан ли один бит в наборе битовых флагов, позволяет логическая операция И с набором флагов в качестве одной операнды и самим флагом в качестве второй.</span><span class="sxs-lookup"><span data-stu-id="99f21-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="99f21-125">Поскольку сам флаг имеет только один набор битов, результатом логической операции И может стать максимум установка самого бита.</span><span class="sxs-lookup"><span data-stu-id="99f21-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="99f21-126">Чтобы определить, установлен ли этот бит, просто сравните результат логической операции И с самим флагом.</span><span class="sxs-lookup"><span data-stu-id="99f21-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="99f21-127">Дополнительные сведения см. в <xref:System.Printing.PrintQueueStatus>разделе, [оператор & (C# Reference)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)и. <xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="99f21-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="99f21-128">Для каждого атрибута с установленным битом код добавляет уведомление в итоговый отчет, который будет представлен пользователю.</span><span class="sxs-lookup"><span data-stu-id="99f21-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="99f21-129">(Метод **ReportAvailabilityAtThisTime**, вызываемый в конце кода, описывается ниже.)</span><span class="sxs-lookup"><span data-stu-id="99f21-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="99f21-130">Чтобы проверить состояние принтера с помощью каждого свойства, просто прочтите каждое свойство и добавьте примечание, если какое-либо свойство имеет значение `true`, в итоговый отчет для пользователя.</span><span class="sxs-lookup"><span data-stu-id="99f21-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="99f21-131">(Метод **ReportAvailabilityAtThisTime**, вызываемый в конце кода, описывается ниже.)</span><span class="sxs-lookup"><span data-stu-id="99f21-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="99f21-132">Метод **ReportAvailabilityAtThisTime** позволяет определить наличие очереди в текущее время суток.</span><span class="sxs-lookup"><span data-stu-id="99f21-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="99f21-133">Метод не будет выполнять никаких действий, <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> если <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> свойства и равны; так как в этом случае принтер доступен постоянно.</span><span class="sxs-lookup"><span data-stu-id="99f21-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="99f21-134">Если они различаются, метод получает текущее время, которое затем должно быть преобразовано в общее число минут после полуночи, так <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> как <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> свойства и <xref:System.Int32>представляют собой минуты после полуночи, а не <xref:System.DateTime> объект.</span><span class="sxs-lookup"><span data-stu-id="99f21-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="99f21-135">В конечном итоге метод проверяет, находится ли текущее время в промежутке между временем начала и окончания.</span><span class="sxs-lookup"><span data-stu-id="99f21-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="99f21-136">См. также</span><span class="sxs-lookup"><span data-stu-id="99f21-136">See also</span></span>

- <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>
- <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>
- <xref:System.DateTime>
- <xref:System.Printing.PrintQueueStatus>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- [<span data-ttu-id="99f21-137">Оператор & (C# Reference)</span><span class="sxs-lookup"><span data-stu-id="99f21-137">& Operator (C# Reference)</span></span>](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [<span data-ttu-id="99f21-138">Документы в WPF</span><span class="sxs-lookup"><span data-stu-id="99f21-138">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="99f21-139">Общие сведения о печати</span><span class="sxs-lookup"><span data-stu-id="99f21-139">Printing Overview</span></span>](printing-overview.md)
