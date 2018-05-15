---
title: Активация XAML
ms.date: 03/30/2017
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
ms.openlocfilehash: 8621b0ea7b390c81e76ac7eeedb0b547b44320d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="xaml-activation"></a><span data-ttu-id="805ca-102">Активация XAML</span><span class="sxs-lookup"><span data-stu-id="805ca-102">XAML Activation</span></span>
<span data-ttu-id="805ca-103">В этом образце показано, как разместить декларативное бизнес-правило в IIS.</span><span class="sxs-lookup"><span data-stu-id="805ca-103">This sample demonstrates how to host a declarative workflow in IIS.</span></span> <span data-ttu-id="805ca-104">Образец представляет базовый рабочий процесс с именем `EchoService`, в котором имеется одна операция.</span><span class="sxs-lookup"><span data-stu-id="805ca-104">The sample is a basic workflow called `EchoService` that has one operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="805ca-105">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="805ca-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="805ca-106">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="805ca-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="805ca-107">Если этот каталог не существует, перейдите на загрузки страницы, чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="805ca-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="805ca-108">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="805ca-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="805ca-109">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="805ca-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="805ca-110">Откройте решение XAMLActivation.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="805ca-110">Open the XAMLActivation.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="805ca-111">Постройте решение, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="805ca-111">Build the solution by pressing **F5**.</span></span>  
  
3.  <span data-ttu-id="805ca-112">Запустите файл WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="805ca-112">Run WcfTestClient.exe.</span></span> <span data-ttu-id="805ca-113">Введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="805ca-113">From a command prompt, type in the following:</span></span>  
  
    1.  <span data-ttu-id="805ca-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="805ca-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span></span>  
  
    2.  <span data-ttu-id="805ca-115">Запустите файл WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="805ca-115">Run WcfTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="805ca-116">Задать адрес службы в WcfTestClient.exe, нажав сочетание клавиш CTRL + SHIFT + A и установив для адреса службы http://localhost:56133/Service.xamlx.</span><span class="sxs-lookup"><span data-stu-id="805ca-116">Set the address of the service on WcfTestClient.exe by pressing CTRL+SHIFT+A and setting the service address to http://localhost:56133/Service.xamlx.</span></span>  
  
5.  <span data-ttu-id="805ca-117">Произведите операцию Echo для проверки службы.</span><span class="sxs-lookup"><span data-stu-id="805ca-117">Perform the echo operation to test the service.</span></span>  
  
6.  <span data-ttu-id="805ca-118">Разверните службу в IIS, используя файл DeployToIIS.Bat из командной строки с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="805ca-118">Deploy the Service in IIS using DeployToIIS.Bat in a command prompt with administrator privileges.</span></span>  
  
7.  <span data-ttu-id="805ca-119">Обновите адрес службы в клиенте для http://localhost/XAMLActivation/Service.xamlx и проверьте службу, используя WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="805ca-119">Update the service address in the client to http://localhost/XAMLActivation/Service.xamlx and test the service again using WcfTestClient.exe.</span></span>
