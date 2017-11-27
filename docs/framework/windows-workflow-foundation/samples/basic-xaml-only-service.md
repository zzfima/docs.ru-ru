---
title: "Базовая служба с использованием только XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c106feb0-0245-43b5-aefe-93ce0e4d38eb
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3fbf8a719647199439e2333ba5e26cbe51be3add
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="basic-xaml-only-service"></a><span data-ttu-id="f794d-102">Базовая служба с использованием только XAML</span><span class="sxs-lookup"><span data-stu-id="f794d-102">Basic XAML only Service</span></span>
<span data-ttu-id="f794d-103">В этом образце демонстрируется создание службы, работающей только с языком XAML.</span><span class="sxs-lookup"><span data-stu-id="f794d-103">This sample demonstrates how to create a XAML only service.</span></span> <span data-ttu-id="f794d-104">В данном сценарии рассматривается диагностическая служба для автомобильных проблем.</span><span class="sxs-lookup"><span data-stu-id="f794d-104">The scenario is a diagnostics service for car-related problems.</span></span> <span data-ttu-id="f794d-105">Служба реализована в виде рабочего процесса, задающего клиенту ряд вопросов для диагностики проблемы.</span><span class="sxs-lookup"><span data-stu-id="f794d-105">The service is implemented as a workflow that asks the client a series of questions to diagnose the problem.</span></span> <span data-ttu-id="f794d-106">Эта служба может выполнять диагностику двух типов проблем (машина не заводится, или система кондиционирования не работает).</span><span class="sxs-lookup"><span data-stu-id="f794d-106">There are two types of issues the service can diagnose (car does not start or air conditioning not working).</span></span> <span data-ttu-id="f794d-107">Для представления трех простых операций служб в рабочем процессе использует шаблон «Запрос-ответ» из конструктора.</span><span class="sxs-lookup"><span data-stu-id="f794d-107">The workflow uses Request/Reply template from the designer to expose three simple service operations.</span></span> <span data-ttu-id="f794d-108">Служба размещается в службах IIS путем создания виртуального каталога в IIS и копирования service1.xamlx и файлов Web.config в виртуальный каталог, скомпилированный код не требуется.</span><span class="sxs-lookup"><span data-stu-id="f794d-108">The service is hosted in IIS by creating a virtual directory in IIS and copying the service1.xamlx and Web.config files into the virtual directory, no compiled code is required.</span></span> <span data-ttu-id="f794d-109">По умолчанию в этом примере автоматически скопирует необходимые файлы в виртуальный каталог, созданный при выполнении процедуры настройки для образцов WCF и WF: [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) при построении в Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="f794d-109">By default this sample will automatically copy the needed files into the virtual directory created when you follow the setup instructions for the WCF and WF samples: [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) when built in Visual Studio 2010.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f794d-110">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="f794d-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="f794d-111">Загрузите решение проекта в среду [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и постройте проект.</span><span class="sxs-lookup"><span data-stu-id="f794d-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="f794d-112">Запустите клиентское приложение, созданное в папке [основной каталог решения]\Client\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="f794d-112">Run the Client application generated in [solution base directory]\Client\bin\debug.</span></span>  
  
3.  <span data-ttu-id="f794d-113">Приложение выводит варианты, выберите один из вариантов.</span><span class="sxs-lookup"><span data-stu-id="f794d-113">The application prints out options, selects an option.</span></span> <span data-ttu-id="f794d-114">Затем приложение задает вопросы, на которые следует ответить «да» или «нет» (с использованием клавиш Y и N).</span><span class="sxs-lookup"><span data-stu-id="f794d-114">The application then asks some questions, answer them yes or no (using Y/N keys).</span></span> <span data-ttu-id="f794d-115">Когда служба завершит диагностику проблем, приложение выведет диагноз.</span><span class="sxs-lookup"><span data-stu-id="f794d-115">When the service is done diagnosing the issues, the application prints out a diagnosis.</span></span>  
  
4.  <span data-ttu-id="f794d-116">Приложение возвратится к вариантам.</span><span class="sxs-lookup"><span data-stu-id="f794d-116">The application goes back to the options.</span></span> <span data-ttu-id="f794d-117">Можно выполнить диагностику другой проблемы или выйти из приложения.</span><span class="sxs-lookup"><span data-stu-id="f794d-117">You can diagnose another problem or exit the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f794d-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f794d-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f794d-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f794d-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f794d-120">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f794d-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f794d-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f794d-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLService`  
  
## <a name="see-also"></a><span data-ttu-id="f794d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f794d-122">See Also</span></span>
