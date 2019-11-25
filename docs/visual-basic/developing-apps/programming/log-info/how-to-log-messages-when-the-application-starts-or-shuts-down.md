---
title: Практическое руководство. Запись в журнал сообщений при запуске и завершении приложения
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, shutdown
- My.Application.Log object, logging
- Startup event [Visual Basic]
- event logs, startup
- Shutdown event [Visual Basic]
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
ms.openlocfilehash: 5a4ef3888ba8371d26204c3569b5fb9bae1f15f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352099"
---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a><span data-ttu-id="1d3cb-102">Практическое руководство. Запись в журнал сообщений при запуске и завершении приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d3cb-102">How to: Log Messages When the Application Starts or Shuts Down (Visual Basic)</span></span>

<span data-ttu-id="1d3cb-103">Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="1d3cb-104">В этом примере показан способ использования метода `My.Application.Log.WriteEntry` с событиями `Startup` и `Shutdown` для записи сведений трассировки.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-104">This example shows how to use the `My.Application.Log.WriteEntry` method with the `Startup` and `Shutdown` events to write tracing information.</span></span>  
  
### <a name="to-access-the-applications-event-handler-code"></a><span data-ttu-id="1d3cb-105">Доступ к коду обработчика событий приложения</span><span class="sxs-lookup"><span data-stu-id="1d3cb-105">To access the application's event-handler code</span></span>  
  
1. <span data-ttu-id="1d3cb-106">Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-106">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1d3cb-107">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-107">On the **Project** menu, choose **Properties**.</span></span>  
  
2. <span data-ttu-id="1d3cb-108">Перейдите на вкладку **Приложение** .</span><span class="sxs-lookup"><span data-stu-id="1d3cb-108">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="1d3cb-109">Нажмите кнопку **Просмотреть события приложения** , чтобы открыть редактор кода.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-109">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="1d3cb-110">Откроется файл ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-110">This opens the ApplicationEvents.vb file.</span></span>  
  
### <a name="to-log-messages-when-the-application-starts"></a><span data-ttu-id="1d3cb-111">Запись сообщений в журнал при запуске приложения</span><span class="sxs-lookup"><span data-stu-id="1d3cb-111">To log messages when the application starts</span></span>  
  
1. <span data-ttu-id="1d3cb-112">Откройте в редакторе кода файл ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-112">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="1d3cb-113">В меню **Общие** выберите пункт **События MyApplication**.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-113">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2. <span data-ttu-id="1d3cb-114">В меню **Объявления** выберите пункт **Запуск**.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-114">On the **Declarations** menu, choose **Startup**.</span></span>  
  
     <span data-ttu-id="1d3cb-115">Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> до запуска главного приложения.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-115">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> event before the main application runs.</span></span>  
  
3. <span data-ttu-id="1d3cb-116">Добавьте метод `My.Application.Log.WriteEntry` в обработчик событий `Startup` .</span><span class="sxs-lookup"><span data-stu-id="1d3cb-116">Add the `My.Application.Log.WriteEntry` method to the `Startup` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#1)]  
  
### <a name="to-log-messages-when-the-application-shuts-down"></a><span data-ttu-id="1d3cb-117">Запись сообщений в журнал при завершении работы приложения</span><span class="sxs-lookup"><span data-stu-id="1d3cb-117">To log messages when the application shuts down</span></span>  
  
1. <span data-ttu-id="1d3cb-118">Откройте в редакторе кода файл ApplicationEvents.vb.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-118">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="1d3cb-119">В меню **Общие** выберите пункт **События MyApplication**.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-119">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2. <span data-ttu-id="1d3cb-120">В меню **Объявления** выберите пункт **Завершение работы**.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-120">On the **Declarations** menu, choose **Shutdown**.</span></span>  
  
     <span data-ttu-id="1d3cb-121">Приложение создает событие <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> после запуска основного приложения, но до завершения его работы.</span><span class="sxs-lookup"><span data-stu-id="1d3cb-121">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> event after the main application runs, but before it shuts down.</span></span>  
  
3. <span data-ttu-id="1d3cb-122">Добавьте метод `My.Application.Log.WriteEntry` в обработчик событий `Shutdown` .</span><span class="sxs-lookup"><span data-stu-id="1d3cb-122">Add the `My.Application.Log.WriteEntry` method to the `Shutdown` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="1d3cb-123">Пример</span><span class="sxs-lookup"><span data-stu-id="1d3cb-123">Example</span></span>  

 <span data-ttu-id="1d3cb-124">Для доступа к событиям приложения в редакторе кода можно использовать **конструктор проектов** .</span><span class="sxs-lookup"><span data-stu-id="1d3cb-124">You can use the **Project Designer** to access the application events in the Code Editor.</span></span> <span data-ttu-id="1d3cb-125">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="1d3cb-125">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 [!code-vb[VbVbalrMyApplicationLog#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="1d3cb-126">См. также</span><span class="sxs-lookup"><span data-stu-id="1d3cb-126">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="1d3cb-127">Страница "Приложение" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d3cb-127">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
- [<span data-ttu-id="1d3cb-128">Работа с журналами приложения</span><span class="sxs-lookup"><span data-stu-id="1d3cb-128">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
