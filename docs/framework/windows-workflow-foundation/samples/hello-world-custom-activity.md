---
title: Пользовательское действие Hello World
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72b1dd0a-9aad-47d5-95a9-a1024ee1d0a1
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa441a3019b0ef6df31dc0a46be7ea7e8e00a4b8
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="hello-world-custom-activity"></a><span data-ttu-id="0e250-102">Пользовательское действие Hello World</span><span class="sxs-lookup"><span data-stu-id="0e250-102">Hello World Custom Activity</span></span>
<span data-ttu-id="0e250-103">В этом образце показано несколько ключевых возможностей для Windows Workflow Foundation (WF), включая создание простого настраиваемого действия.</span><span class="sxs-lookup"><span data-stu-id="0e250-103">This sample demonstrates several key features of Windows Workflow Foundation (WF), including how to create a simple custom activity.</span></span> <span data-ttu-id="0e250-104">Некоторые возможности, демонстрируемые в этом образце, создают пользовательское действие в C# и используют аргументы `in` и `out` (<xref:System.Activities.InArgument> и <xref:System.Activities.OutArgument>).</span><span class="sxs-lookup"><span data-stu-id="0e250-104">Some of the features demonstrated in this sample are creating a custom activity in C# and using `in` and `out` arguments (<xref:System.Activities.InArgument> and <xref:System.Activities.OutArgument>).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0e250-105">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0e250-105">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0e250-106">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0e250-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0e250-107">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="0e250-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0e250-108">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0e250-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\HelloWorld`  
  
## <a name="creating-a-workflow-in-code"></a><span data-ttu-id="0e250-109">Создание рабочего процесса в коде</span><span class="sxs-lookup"><span data-stu-id="0e250-109">Creating a Workflow in Code</span></span>  
 <span data-ttu-id="0e250-110">В этом образце создаются два пользовательских действия с использованием кода C#.</span><span class="sxs-lookup"><span data-stu-id="0e250-110">In this sample, two custom activities are created using C# code.</span></span> <span data-ttu-id="0e250-111">Оба пользовательских действия наследуют непосредственно или косвенно от <xref:System.Activities.Activity%601> для возвращения одного значения.</span><span class="sxs-lookup"><span data-stu-id="0e250-111">Both custom activities inherit directly or indirectly from <xref:System.Activities.Activity%601> to return a single value.</span></span> <span data-ttu-id="0e250-112">Преимуществом использования универсального возвращаемого значения вместо наследования от неуниверсального класса <xref:System.Activities.Activity> является то, что некоторые действия (такие как <xref:System.Activities.Statements.Assign>) могут обращаться к возвращаемому значению, если они используются как часть составного действия.</span><span class="sxs-lookup"><span data-stu-id="0e250-112">The advantage of using the generic return value, instead of inheriting from the non-generic <xref:System.Activities.Activity> class, is that some activities (such as <xref:System.Activities.Statements.Assign>) are able to access the return value when used as part of a composed activity.</span></span>  
  
 <span data-ttu-id="0e250-113">AppendString</span><span class="sxs-lookup"><span data-stu-id="0e250-113">AppendString</span></span>  
 <span data-ttu-id="0e250-114">Это действие наследует от класса <xref:System.Activities.Activity%601> и использует действие <xref:System.Activities.Statements.Assign>, которое объединяет две строки.</span><span class="sxs-lookup"><span data-stu-id="0e250-114">This activity inherits from <xref:System.Activities.Activity%601>, and uses an <xref:System.Activities.Statements.Assign> activity that concatenates two strings together.</span></span>  
  
 <span data-ttu-id="0e250-115">Prepend String</span><span class="sxs-lookup"><span data-stu-id="0e250-115">Prepend String</span></span>  
 <span data-ttu-id="0e250-116">Это действие наследует непосредственно от <xref:System.Activities.CodeActivity%601> и создает аналогичные функциональные возможности для действия `AppendString`, которое использует логику, реализуемую в коде, а не уже имеющееся действие.</span><span class="sxs-lookup"><span data-stu-id="0e250-116">This activity inherits directly from <xref:System.Activities.CodeActivity%601>, and creates similar functionality to the `AppendString` activity, which uses logic implemented in code rather than being composed of a pre-existing activity.</span></span>  
  
 <span data-ttu-id="0e250-117">В этот проект включены следующие файлы.</span><span class="sxs-lookup"><span data-stu-id="0e250-117">The following files are included in this project.</span></span>  
  
 <span data-ttu-id="0e250-118">AppendString.cs</span><span class="sxs-lookup"><span data-stu-id="0e250-118">AppendString.cs</span></span>  
 <span data-ttu-id="0e250-119">Пользовательское действие, которое присоединяет строки друг к другу.</span><span class="sxs-lookup"><span data-stu-id="0e250-119">The custom activity that appends strings together.</span></span> <span data-ttu-id="0e250-120">Он принимает строку и объединяет их с текстовой строкой «говорит Здравствуй, мир!» в форму выходе полного сообщения.</span><span class="sxs-lookup"><span data-stu-id="0e250-120">It takes in a string and combines it with a literal text string " says hello world" to form a complete message as output.</span></span>  
  
 <span data-ttu-id="0e250-121">PrependString.cs</span><span class="sxs-lookup"><span data-stu-id="0e250-121">PrependString.cs</span></span>  
 <span data-ttu-id="0e250-122">Это действие вставляет заранее определенную строку в начало входной строки.</span><span class="sxs-lookup"><span data-stu-id="0e250-122">This activity prefixes a predefined string to an input string.</span></span>  
  
 <span data-ttu-id="0e250-123">Sequence1.xaml</span><span class="sxs-lookup"><span data-stu-id="0e250-123">Sequence1.xaml</span></span>  
 <span data-ttu-id="0e250-124">Рабочий процесс, который использует пользовательские действия `AppendString` и `PrependString`.</span><span class="sxs-lookup"><span data-stu-id="0e250-124">A workflow that uses the `AppendString` and `PrependString` custom activities.</span></span>  
  
 <span data-ttu-id="0e250-125">Program.cs</span><span class="sxs-lookup"><span data-stu-id="0e250-125">Program.cs</span></span>  
 <span data-ttu-id="0e250-126">Программа, которая выполняет рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="0e250-126">A program that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="0e250-127">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="0e250-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="0e250-128">Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения HelloWorld.sln.</span><span class="sxs-lookup"><span data-stu-id="0e250-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the HelloWorld.sln solution file.</span></span>  
  
2.  <span data-ttu-id="0e250-129">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="0e250-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="0e250-130">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="0e250-130">To run the solution, press F5.</span></span>