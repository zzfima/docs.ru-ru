---
title: "Использование процедурных действий"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d0aeafeaf78e25f612ededf2f6a15061ec280a2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="using-procedural-activities"></a><span data-ttu-id="d6029-102">Использование процедурных действий</span><span class="sxs-lookup"><span data-stu-id="d6029-102">Using Procedural Activities</span></span>
<span data-ttu-id="d6029-103">В образце действия <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch> и <xref:System.Activities.Statements.WriteLine> используются для реализации игры по угадыванию числа.</span><span class="sxs-lookup"><span data-stu-id="d6029-103">The sample uses the <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch>, and <xref:System.Activities.Statements.WriteLine> activities to implement a guessing game.</span></span> <span data-ttu-id="d6029-104">В игре по угадыванию числа компьютер выбирает случайное число, а игрок должен угадать это число.</span><span class="sxs-lookup"><span data-stu-id="d6029-104">The guessing game selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="d6029-105">Если игрок дает неверный ответ, рабочий процесс подсказывает, является ли загаданное число большим или меньшим предложенного.</span><span class="sxs-lookup"><span data-stu-id="d6029-105">When the player submits an incorrect guess, the workflow provides a hint whether to guess higher or lower.</span></span> <span data-ttu-id="d6029-106">Если игрок угадывает число менее чем за 7 попыток, отображается особое поздравление.</span><span class="sxs-lookup"><span data-stu-id="d6029-106">If the player guesses the number in less than 7 attempts, a special congratulations is displayed to the user.</span></span>  
  
## <a name="custom-activities-in-this-sample"></a><span data-ttu-id="d6029-107">Пользовательские действия в этом образце</span><span class="sxs-lookup"><span data-stu-id="d6029-107">Custom Activities in this Sample</span></span>  
  
### <a name="readline"></a><span data-ttu-id="d6029-108">ReadLine</span><span class="sxs-lookup"><span data-stu-id="d6029-108">ReadLine</span></span>  
 <span data-ttu-id="d6029-109">Считывает строку текста из консоли.</span><span class="sxs-lookup"><span data-stu-id="d6029-109">Reads a line of text from the console.</span></span> <span data-ttu-id="d6029-110">Это действие является производным от класса <xref:System.Activities.NativeActivity> и создает закладку, которая возобновляется консольным приложением при прочтении строки.</span><span class="sxs-lookup"><span data-stu-id="d6029-110">This activity derives from the <xref:System.Activities.NativeActivity> class and creates a bookmark that is resumed by the console application when a line is read.</span></span>  
  
### <a name="promptint"></a><span data-ttu-id="d6029-111">PromptInt</span><span class="sxs-lookup"><span data-stu-id="d6029-111">PromptInt</span></span>  
 <span data-ttu-id="d6029-112">Предлагает пользователю ввести число, затем считывает это число из окна консоли.</span><span class="sxs-lookup"><span data-stu-id="d6029-112">Prompts the user to type in a number and then reads it from a console window.</span></span> <span data-ttu-id="d6029-113">Действие является производным от <xref:System.Activities.Activity%601> и использует действия <xref:System.Activities.Statements.WriteLine> и `ReadLine`.</span><span class="sxs-lookup"><span data-stu-id="d6029-113">The activity derives from <xref:System.Activities.Activity%601> and uses the <xref:System.Activities.Statements.WriteLine> and `ReadLine` activities.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="d6029-114">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="d6029-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="d6029-115">С помощью [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] откройте файл решения GuessingGame.sln.</span><span class="sxs-lookup"><span data-stu-id="d6029-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the GuessingGame.sln solution file.</span></span>  
  
2.  <span data-ttu-id="d6029-116">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="d6029-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d6029-117">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="d6029-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d6029-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d6029-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d6029-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d6029-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d6029-120">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d6029-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d6029-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d6029-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`