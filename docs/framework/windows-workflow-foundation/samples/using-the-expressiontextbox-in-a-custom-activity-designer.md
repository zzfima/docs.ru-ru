---
title: "Использование ExpressionTextBox в пользовательском конструкторе действия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 85fe8dcbd0ef5e774ab81ed167ff937ec2e09d83
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a><span data-ttu-id="cd1a7-102">Использование ExpressionTextBox в пользовательском конструкторе действия</span><span class="sxs-lookup"><span data-stu-id="cd1a7-102">Using the ExpressionTextBox in a Custom Activity Designer</span></span>
<span data-ttu-id="cd1a7-103">В этом образце показано, как использовать <xref:System.Activities.Presentation.View.ExpressionTextBox> в настраиваемом конструкторе действий.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-103">This sample shows how to use the <xref:System.Activities.Presentation.View.ExpressionTextBox> in a custom activity designer.</span></span> <span data-ttu-id="cd1a7-104">Пользовательское действие `MultiAssign` присваивает два строковых значения двум строковым переменным.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-104">The custom activity, `MultiAssign`, assigns two string values to two string variables.</span></span> <span data-ttu-id="cd1a7-105">Некоторые элементы управления <xref:System.Activities.Presentation.View.ExpressionTextBox> привязываются к аргументу <xref:System.Activities.InArgument>, а некоторые - к аргументу <xref:System.Activities.OutArgument>.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-105">Some <xref:System.Activities.Presentation.View.ExpressionTextBox> controls bind to <xref:System.Activities.InArgument>s and some bind to <xref:System.Activities.OutArgument>s.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="cd1a7-106">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="cd1a7-106">Sample details</span></span>  
 <span data-ttu-id="cd1a7-107">`ArgumentToExpressionConverter` - это преобразователь типов, используемый для привязки выражений к аргументам.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-107">The `ArgumentToExpressionConverter` is the type converter used when binding expressions to arguments.</span></span> <span data-ttu-id="cd1a7-108">Параметр `ConverterParameter` необходимо установить в соответствующее значение `In` или `Out`.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-108">The `ConverterParameter` must be set to `In` or `Out` as appropriate.</span></span> <span data-ttu-id="cd1a7-109">Тип `InOut` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-109">`InOut` is not supported.</span></span>  
  
 <span data-ttu-id="cd1a7-110">`UseLocationExpression` Атрибут используется на `OutArgument`s, чтобы указать, что выражение должно иметь выражения L-значение («левое значение» или «расположение значение»).</span><span class="sxs-lookup"><span data-stu-id="cd1a7-110">The `UseLocationExpression` attribute is used on `OutArgument`s to specify that the expression should be an L-value ("left value" or "location value") expression.</span></span> <span data-ttu-id="cd1a7-111">В большинстве случаев левостороннее выражение является допустимым идентификатором Visual Basic, используемым для указания того, что возвращаемый аргумент `OutArgument` является переменной или именем аргумента.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-111">In most cases, an L-value expression is a valid Visual Basic identifier used to indicate that the `OutArgument` being returned is a variable or argument name.</span></span>  
  
 <span data-ttu-id="cd1a7-112">В этом примере для атрибута `MaxLines` установлено значение 1, а значение атрибута `MinLines` не задано.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-112">The `MaxLines` attribute is set to one in this example and `MinLines` is not set.</span></span> <span data-ttu-id="cd1a7-113">Это указывает, что текстовое поле <xref:System.Activities.Presentation.View.ExpressionTextBox> имеет фиксированный размер в одну строку независимо от объема текста, введенного пользователем.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-113">This indicates that the <xref:System.Activities.Presentation.View.ExpressionTextBox> is a fixed size of one line regardless of the amount of text typed by the user.</span></span> <span data-ttu-id="cd1a7-114">Чтобы разрешить изменение размера текстового поля <xref:System.Activities.Presentation.View.ExpressionTextBox> в соответствии с объемом вводимых пользователем данных, задайте значение `MaxLines`, которое больше значения `MinLines`.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-114">To allow the <xref:System.Activities.Presentation.View.ExpressionTextBox> to grow to fit user input, set `MaxLines` greater than `MinLines`.</span></span>  
  
 <span data-ttu-id="cd1a7-115">Текстовое поле ExpressionTextBox может быть привязано только к аргументам и не может быть привязано к свойствам CLR.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-115">An ExpressionTextBox can only be bound to arguments, and cannot be bound to CLR properties.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="cd1a7-116">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="cd1a7-116">To use this sample</span></span>  
  
1.  <span data-ttu-id="cd1a7-117">Откройте файл ExpressionTextBoxSample.sln с помощью [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd1a7-117">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ExpressionTextBoxSample.sln file.</span></span>  
  
2.  <span data-ttu-id="cd1a7-118">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-118">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="cd1a7-119">Запуск образца</span><span class="sxs-lookup"><span data-stu-id="cd1a7-119">To run this sample</span></span>  
  
1.  <span data-ttu-id="cd1a7-120">Добавьте в решение новое консольное приложение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-120">Add a new Workflow Console Application to the solution.</span></span>  
  
2.  <span data-ttu-id="cd1a7-121">Добавьте ссылку на **ExpressionTextBoxSample** проекта из нового проекта консольного приложения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-121">Add a reference to the **ExpressionTextBoxSample** project from the new Workflow Console Application project.</span></span>  
  
3.  <span data-ttu-id="cd1a7-122">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-122">Build the solution.</span></span>  
  
4.  <span data-ttu-id="cd1a7-123">Перетащите **MultiAssign** из области элементов и поместите его в рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-123">Drag the **MultiAssign** activity from the toolbox and drop it into the workflow.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cd1a7-124">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cd1a7-125">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cd1a7-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cd1a7-126">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cd1a7-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cd1a7-127">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="cd1a7-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a><span data-ttu-id="cd1a7-128">См. также</span><span class="sxs-lookup"><span data-stu-id="cd1a7-128">See Also</span></span>  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>  
 [<span data-ttu-id="cd1a7-129">Разработка приложений с помощью конструктора рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="cd1a7-129">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
