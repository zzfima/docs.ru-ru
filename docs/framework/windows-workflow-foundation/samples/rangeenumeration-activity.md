---
title: Действие RangeEnumeration
ms.date: 03/30/2017
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
ms.openlocfilehash: c9cf522227620422b414adc26cbc0bf338bf57d4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556296"
---
# <a name="rangeenumeration-activity"></a><span data-ttu-id="8a4df-102">Действие RangeEnumeration</span><span class="sxs-lookup"><span data-stu-id="8a4df-102">RangeEnumeration Activity</span></span>
<span data-ttu-id="8a4df-103">В этом образце демонстрируется создание пользовательского действия, выполняющего итерацию по коллекции чисел. В следующей таблице приведены основные файлы, содержащиеся в образце.</span><span class="sxs-lookup"><span data-stu-id="8a4df-103">This sample demonstrates how to create a custom activity that iterates over a collection of numbers.The following table details the main files included in the sample.</span></span>  
  
|<span data-ttu-id="8a4df-104">Имя файла</span><span class="sxs-lookup"><span data-stu-id="8a4df-104">File name</span></span>|<span data-ttu-id="8a4df-105">Описание</span><span class="sxs-lookup"><span data-stu-id="8a4df-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8a4df-106">RangeEnumeration.cs</span><span class="sxs-lookup"><span data-stu-id="8a4df-106">RangeEnumeration.cs</span></span>|<span data-ttu-id="8a4df-107">Определяет пользовательское действие с названием `RangeEnumeration`, которое переопределяет класс <xref:System.Activities.NativeActivity> и перебирает в цикле ряд чисел.</span><span class="sxs-lookup"><span data-stu-id="8a4df-107">Defines a custom activity named `RangeEnumeration` that overrides the <xref:System.Activities.NativeActivity> class and loops through a series of numbers.</span></span>|  
|<span data-ttu-id="8a4df-108">RangeEnumerationSample.cs</span><span class="sxs-lookup"><span data-stu-id="8a4df-108">RangeEnumerationSample.cs</span></span>|<span data-ttu-id="8a4df-109">Клиентское приложение, использующее действие `RangeEnumeration` для итерации по коллекции чисел.</span><span class="sxs-lookup"><span data-stu-id="8a4df-109">A client application that uses the `RangeEnumeration` activity to iterate over a collection of numbers.</span></span>|  
  
 <span data-ttu-id="8a4df-110">В приведенной ниже таблице показаны свойства действия `RangeEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="8a4df-110">The following table details the properties of the `RangeEnumeration` activity.</span></span>  
  
|<span data-ttu-id="8a4df-111">Свойство</span><span class="sxs-lookup"><span data-stu-id="8a4df-111">Property</span></span>|<span data-ttu-id="8a4df-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8a4df-112">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8a4df-113">Запуск</span><span class="sxs-lookup"><span data-stu-id="8a4df-113">Start</span></span>|<span data-ttu-id="8a4df-114">Целое число, с которого начинается цикл.</span><span class="sxs-lookup"><span data-stu-id="8a4df-114">The integer to start the loop from.</span></span>|  
|<span data-ttu-id="8a4df-115">Остановить</span><span class="sxs-lookup"><span data-stu-id="8a4df-115">Stop</span></span>|<span data-ttu-id="8a4df-116">Целое число, на котором заканчивается цикл.</span><span class="sxs-lookup"><span data-stu-id="8a4df-116">The integer to stop the loop at.</span></span>|  
|<span data-ttu-id="8a4df-117">Шаг</span><span class="sxs-lookup"><span data-stu-id="8a4df-117">Step</span></span>|<span data-ttu-id="8a4df-118">Указывает, в каком объеме проводить итерацию каждый раз.</span><span class="sxs-lookup"><span data-stu-id="8a4df-118">Specifies how much to iterate each time.</span></span>|  
|<span data-ttu-id="8a4df-119">Body</span><span class="sxs-lookup"><span data-stu-id="8a4df-119">Body</span></span>|<span data-ttu-id="8a4df-120">Указывает код для выполнения в ходе каждой итерации.</span><span class="sxs-lookup"><span data-stu-id="8a4df-120">Specifies the code to execute during each iteration.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="8a4df-121">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="8a4df-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="8a4df-122">Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения RangeEnumeration.sln.</span><span class="sxs-lookup"><span data-stu-id="8a4df-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RangeEnumeration.sln solution file.</span></span>  
  
2.  <span data-ttu-id="8a4df-123">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="8a4df-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="8a4df-124">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="8a4df-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8a4df-125">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8a4df-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8a4df-126">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="8a4df-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8a4df-127">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="8a4df-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8a4df-128">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="8a4df-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`