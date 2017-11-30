---
title: "Загрузка из XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 19fd22f2756399cc768332cbaa653717611e5e54
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="load-from-xaml"></a><span data-ttu-id="7dccf-102">Загрузка из XAML</span><span class="sxs-lookup"><span data-stu-id="7dccf-102">Load From XAML</span></span>
<span data-ttu-id="7dccf-103">В этом образце показан способ динамической загрузки рабочего процесса XAML без применения средства XamlBuildTask.</span><span class="sxs-lookup"><span data-stu-id="7dccf-103">This sample demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span> <span data-ttu-id="7dccf-104">Вместо этого в образце вызывается метод <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="7dccf-104">Instead, the sample calls the <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="7dccf-105">Образец представляет клиентское приложение [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)], которое загружает рабочие процессы XAML, используя класс <xref:System.Activities.XamlIntegration.ActivityXamlServices>, и выполняет их.</span><span class="sxs-lookup"><span data-stu-id="7dccf-105">The sample is a [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] client application that loads XAML workflows using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class and executes them.</span></span> <span data-ttu-id="7dccf-106">После загрузки этих процессов с использованием класса <xref:System.Activities.XamlIntegration.ActivityXamlServices> возвращается действие <xref:System.Activities.DynamicActivity%601>, которое может быть выполнено.</span><span class="sxs-lookup"><span data-stu-id="7dccf-106">After they have been loaded using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class, a <xref:System.Activities.DynamicActivity%601> is returned that can be executed.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="7dccf-107">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="7dccf-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="7dccf-108">Используя [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], откройте файл решения LoadFromXAML.sln.</span><span class="sxs-lookup"><span data-stu-id="7dccf-108">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LoadFromXAML.sln solution file.</span></span>  
  
2.  <span data-ttu-id="7dccf-109">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="7dccf-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7dccf-110">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="7dccf-110">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7dccf-111">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="7dccf-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7dccf-112">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="7dccf-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7dccf-113">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7dccf-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7dccf-114">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="7dccf-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`