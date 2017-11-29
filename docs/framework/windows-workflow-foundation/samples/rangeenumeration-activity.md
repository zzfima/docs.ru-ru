---
title: "Действие RangeEnumeration"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 024cdc9ae082171fb33a63493ac0fbfdd45d3c72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="rangeenumeration-activity"></a><span data-ttu-id="ef57e-102">Действие RangeEnumeration</span><span class="sxs-lookup"><span data-stu-id="ef57e-102">RangeEnumeration Activity</span></span>
<span data-ttu-id="ef57e-103">В этом образце демонстрируется создание пользовательского действия, выполняющего итерацию по коллекции чисел. В следующей таблице приведены основные файлы, содержащиеся в образце.</span><span class="sxs-lookup"><span data-stu-id="ef57e-103">This sample demonstrates how to create a custom activity that iterates over a collection of numbers.The following table details the main files included in the sample.</span></span>  
  
|<span data-ttu-id="ef57e-104">Имя файла</span><span class="sxs-lookup"><span data-stu-id="ef57e-104">File name</span></span>|<span data-ttu-id="ef57e-105">Описание</span><span class="sxs-lookup"><span data-stu-id="ef57e-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef57e-106">RangeEnumeration.cs</span><span class="sxs-lookup"><span data-stu-id="ef57e-106">RangeEnumeration.cs</span></span>|<span data-ttu-id="ef57e-107">Определяет пользовательское действие с названием `RangeEnumeration`, которое переопределяет класс <xref:System.Activities.NativeActivity> и перебирает в цикле ряд чисел.</span><span class="sxs-lookup"><span data-stu-id="ef57e-107">Defines a custom activity named `RangeEnumeration` that overrides the <xref:System.Activities.NativeActivity> class and loops through a series of numbers.</span></span>|  
|<span data-ttu-id="ef57e-108">RangeEnumerationSample.cs</span><span class="sxs-lookup"><span data-stu-id="ef57e-108">RangeEnumerationSample.cs</span></span>|<span data-ttu-id="ef57e-109">Клиентское приложение, использующее действие `RangeEnumeration` для итерации по коллекции чисел.</span><span class="sxs-lookup"><span data-stu-id="ef57e-109">A client application that uses the `RangeEnumeration` activity to iterate over a collection of numbers.</span></span>|  
  
 <span data-ttu-id="ef57e-110">В приведенной ниже таблице показаны свойства действия `RangeEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="ef57e-110">The following table details the properties of the `RangeEnumeration` activity.</span></span>  
  
|<span data-ttu-id="ef57e-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="ef57e-111">Property</span></span>|<span data-ttu-id="ef57e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ef57e-112">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="ef57e-113">Запуск</span><span class="sxs-lookup"><span data-stu-id="ef57e-113">Start</span></span>|<span data-ttu-id="ef57e-114">Целое число, с которого начинается цикл.</span><span class="sxs-lookup"><span data-stu-id="ef57e-114">The integer to start the loop from.</span></span>|  
|<span data-ttu-id="ef57e-115">Остановить</span><span class="sxs-lookup"><span data-stu-id="ef57e-115">Stop</span></span>|<span data-ttu-id="ef57e-116">Целое число, на котором заканчивается цикл.</span><span class="sxs-lookup"><span data-stu-id="ef57e-116">The integer to stop the loop at.</span></span>|  
|<span data-ttu-id="ef57e-117">Шаг</span><span class="sxs-lookup"><span data-stu-id="ef57e-117">Step</span></span>|<span data-ttu-id="ef57e-118">Указывает, в каком объеме проводить итерацию каждый раз.</span><span class="sxs-lookup"><span data-stu-id="ef57e-118">Specifies how much to iterate each time.</span></span>|  
|<span data-ttu-id="ef57e-119">Body</span><span class="sxs-lookup"><span data-stu-id="ef57e-119">Body</span></span>|<span data-ttu-id="ef57e-120">Указывает код для выполнения в ходе каждой итерации.</span><span class="sxs-lookup"><span data-stu-id="ef57e-120">Specifies the code to execute during each iteration.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ef57e-121">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="ef57e-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="ef57e-122">Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения RangeEnumeration.sln.</span><span class="sxs-lookup"><span data-stu-id="ef57e-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RangeEnumeration.sln solution file.</span></span>  
  
2.  <span data-ttu-id="ef57e-123">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="ef57e-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ef57e-124">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="ef57e-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ef57e-125">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ef57e-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ef57e-126">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ef57e-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ef57e-127">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef57e-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ef57e-128">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ef57e-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`  
  
## <a name="see-also"></a><span data-ttu-id="ef57e-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ef57e-129">See Also</span></span>
