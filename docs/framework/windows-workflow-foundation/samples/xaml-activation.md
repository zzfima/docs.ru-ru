---
title: "Активация XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f513b10c84de968d5a18b800037b512aad90399e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="xaml-activation"></a><span data-ttu-id="3f4e5-102">Активация XAML</span><span class="sxs-lookup"><span data-stu-id="3f4e5-102">XAML Activation</span></span>
<span data-ttu-id="3f4e5-103">В этом образце показано, как разместить декларативное бизнес-правило в IIS.</span><span class="sxs-lookup"><span data-stu-id="3f4e5-103">This sample demonstrates how to host a declarative workflow in IIS.</span></span> <span data-ttu-id="3f4e5-104">Образец представляет базовый рабочий процесс с именем `EchoService`, в котором имеется одна операция.</span><span class="sxs-lookup"><span data-stu-id="3f4e5-104">The sample is a basic workflow called `EchoService` that has one operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3f4e5-105">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3f4e5-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3f4e5-106">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3f4e5-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3f4e5-107">Если этот каталог не существует, перейдите на страницу загрузки, чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f4e5-107">If this directory does not exist, go to (download page) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3f4e5-108">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="3f4e5-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3f4e5-109">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="3f4e5-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3f4e5-110">Откройте решение XAMLActivation.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f4e5-110">Open the XAMLActivation.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="3f4e5-111">Постройте решение, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="3f4e5-111">Build the solution by pressing **F5**.</span></span>  
  
3.  <span data-ttu-id="3f4e5-112">Запустите файл WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="3f4e5-112">Run WcfTestClient.exe.</span></span> <span data-ttu-id="3f4e5-113">Введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="3f4e5-113">From a command prompt, type in the following:</span></span>  
  
    1.  <span data-ttu-id="3f4e5-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="3f4e5-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span></span>  
  
    2.  <span data-ttu-id="3f4e5-115">Запустите файл WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="3f4e5-115">Run WcfTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="3f4e5-116">Установите адрес службы в WcfTestClient.exe, нажав CTRL+SHIFT+A и установив для адреса службы значение http://localhost:56133/Service.xamlx.</span><span class="sxs-lookup"><span data-stu-id="3f4e5-116">Set the address of the service on WcfTestClient.exe by pressing CTRL+SHIFT+A and setting the service address to http://localhost:56133/Service.xamlx.</span></span>  
  
5.  <span data-ttu-id="3f4e5-117">Произведите операцию Echo для проверки службы.</span><span class="sxs-lookup"><span data-stu-id="3f4e5-117">Perform the echo operation to test the service.</span></span>  
  
6.  <span data-ttu-id="3f4e5-118">Разверните службу в IIS, используя файл DeployToIIS.Bat из командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="3f4e5-118">Deploy the Service in IIS using DeployToIIS.Bat in a command prompt with administrator privileges.</span></span>  
  
7.  <span data-ttu-id="3f4e5-119">Обновите адрес службы в клиенте на http://localhost/XAMLActivation/Service.xamlx и снова проверьте службу, используя WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="3f4e5-119">Update the service address in the client to http://localhost/XAMLActivation/Service.xamlx and test the service again using WcfTestClient.exe.</span></span>
