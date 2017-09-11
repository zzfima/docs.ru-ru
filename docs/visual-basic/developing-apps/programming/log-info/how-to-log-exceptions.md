---
title: "Практическое руководство. Запись в журнал сведений об исключениях в Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: adf2dc683a139d21f24379efc779d4510a2057eb
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="a7c3b-102">Практическое руководство. Запись в журнал сведений об исключениях в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7c3b-102">How to: Log Exceptions in Visual Basic</span></span>
<span data-ttu-id="a7c3b-103">Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал сведений об исключениях, возникающих в приложении.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-103">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="a7c3b-104">Эти примеры демонстрируют применение метода `My.Application.Log.WriteException` для регистрации явно перехваченных исключений и исключений, которые не обрабатываются.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-104">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="a7c3b-105">Для записи сведений в журнал используйте метод `My.Application.Log.WriteEntry`.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-105">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="a7c3b-106">Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-106">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="a7c3b-107">Запись обработанного исключения в журнал</span><span class="sxs-lookup"><span data-stu-id="a7c3b-107">To log a handled exception</span></span>  
  
1.  <span data-ttu-id="a7c3b-108">Создайте метод, который будет генерировать сведения об исключении.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-108">Create the method that will generate the exception information.</span></span>  
  
     <span data-ttu-id="a7c3b-109">[!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a7c3b-109">[!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]</span></span>  
  
2.  <span data-ttu-id="a7c3b-110">Воспользуйтесь блоком `Try...Catch` для перехвата исключения.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-110">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     <span data-ttu-id="a7c3b-111">[!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a7c3b-111">[!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]</span></span>  
  
3.  <span data-ttu-id="a7c3b-112">Поместите код, который может генерировать исключение, в блок `Try`.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-112">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="a7c3b-113">Раскомментируйте строки `Dim` и `MsgBox`, чтобы вызвать исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-113">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     <span data-ttu-id="a7c3b-114">[!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="a7c3b-114">[!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]</span></span>  
  
4.  <span data-ttu-id="a7c3b-115">В блоке `Catch` для записи сведений об исключении используйте метод `My.Application.Log.WriteException`.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-115">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     <span data-ttu-id="a7c3b-116">[!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="a7c3b-116">[!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]</span></span>  
  
     <span data-ttu-id="a7c3b-117">В следующем примере показан полный код для записи обработанного исключения в журнал.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-117">The following example shows the complete code for logging a handled exception.</span></span>  
  
     <span data-ttu-id="a7c3b-118">[!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="a7c3b-118">[!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]</span></span>  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="a7c3b-119">Запись необработанного исключения в журнал</span><span class="sxs-lookup"><span data-stu-id="a7c3b-119">To log an unhandled exception</span></span>  
  
1.  <span data-ttu-id="a7c3b-120">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a7c3b-121">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-121">On the **Project** menu, choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="a7c3b-122">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="a7c3b-122">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="a7c3b-123">Нажмите кнопку **Просмотреть события приложения** , чтобы открыть редактор кода.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-123">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="a7c3b-124">Откроется файл ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-124">This opens the ApplicationEvents.vb file.</span></span>  
  
4.  <span data-ttu-id="a7c3b-125">Откройте в редакторе кода файл ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-125">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="a7c3b-126">В меню **Общие** выберите пункт **События MyApplication**.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-126">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5.  <span data-ttu-id="a7c3b-127">В меню **Объявления** выберите пункт **UnhandledException**.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-127">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="a7c3b-128">Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> до запуска главного приложения.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-128">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6.  <span data-ttu-id="a7c3b-129">Добавьте метод `My.Application.Log.WriteException` в обработчик событий `UnhandledException` .</span><span class="sxs-lookup"><span data-stu-id="a7c3b-129">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     <span data-ttu-id="a7c3b-130">[!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="a7c3b-130">[!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]</span></span>  
  
     <span data-ttu-id="a7c3b-131">В следующем примере показан полный код для записи необработанного исключения в журнал.</span><span class="sxs-lookup"><span data-stu-id="a7c3b-131">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     <span data-ttu-id="a7c3b-132">[!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="a7c3b-132">[!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c3b-133">См. также</span><span class="sxs-lookup"><span data-stu-id="a7c3b-133">See Also</span></span>  
 <span data-ttu-id="a7c3b-134"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7c3b-134"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="a7c3b-135"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="a7c3b-135"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>   
 <span data-ttu-id="a7c3b-136"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span><span class="sxs-lookup"><span data-stu-id="a7c3b-136"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span></span>   
 <span data-ttu-id="a7c3b-137">[Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="a7c3b-137">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="a7c3b-138">[Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a7c3b-138">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 <span data-ttu-id="a7c3b-139">[Пошаговое руководство. Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="a7c3b-139">[Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span></span>  
 [<span data-ttu-id="a7c3b-140">Пошаговое руководство. Изменение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="a7c3b-140">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)

