---
title: Загрузка из XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: c46c9020f07731d3d833332d77fd46a162ccb6dc
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715953"
---
# <a name="load-from-xaml"></a><span data-ttu-id="c0bcb-102">Загрузка из XAML</span><span class="sxs-lookup"><span data-stu-id="c0bcb-102">Load From XAML</span></span>
<span data-ttu-id="c0bcb-103">В этом образце показан способ динамической загрузки рабочего процесса XAML без применения средства XamlBuildTask.</span><span class="sxs-lookup"><span data-stu-id="c0bcb-103">This sample demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span> <span data-ttu-id="c0bcb-104">Вместо этого в образце вызывается метод <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="c0bcb-104">Instead, the sample calls the <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="c0bcb-105">Пример представляет собой клиентское приложение Windows Presentation Foundation (WPF), которое загружает рабочие процессы XAML с помощью класса <xref:System.Activities.XamlIntegration.ActivityXamlServices> и выполняет их.</span><span class="sxs-lookup"><span data-stu-id="c0bcb-105">The sample is a Windows Presentation Foundation (WPF) client application that loads XAML workflows using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class and executes them.</span></span> <span data-ttu-id="c0bcb-106">После загрузки этих процессов с использованием класса <xref:System.Activities.XamlIntegration.ActivityXamlServices> возвращается действие <xref:System.Activities.DynamicActivity%601>, которое может быть выполнено.</span><span class="sxs-lookup"><span data-stu-id="c0bcb-106">After they have been loaded using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class, a <xref:System.Activities.DynamicActivity%601> is returned that can be executed.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="c0bcb-107">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="c0bcb-107">To use this sample</span></span>

1. <span data-ttu-id="c0bcb-108">С помощью Visual Studio 2010 откройте файл решения Лоадфромксамл. sln.</span><span class="sxs-lookup"><span data-stu-id="c0bcb-108">Using Visual Studio 2010, open the LoadFromXAML.sln solution file.</span></span>

2. <span data-ttu-id="c0bcb-109">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="c0bcb-109">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="c0bcb-110">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="c0bcb-110">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0bcb-111">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c0bcb-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c0bcb-112">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c0bcb-112">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="c0bcb-113">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="c0bcb-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c0bcb-114">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c0bcb-114">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`
