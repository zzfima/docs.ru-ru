---
title: Использование Interop для обмена с внешними данными
ms.date: 03/30/2017
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
ms.openlocfilehash: 534321e5b5568e0dd0988333dc98ccc18ff33df8
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44508300"
---
# <a name="using-interop-with-external-data-exchange"></a><span data-ttu-id="0189e-102">Использование Interop для обмена с внешними данными</span><span class="sxs-lookup"><span data-stu-id="0189e-102">Using Interop with External Data Exchange</span></span>
<span data-ttu-id="0189e-103"><xref:System.Activities.Statements.Interop> Действие может использоваться для выполнения действий из Windows Workflow Foundation (WF) в [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] и [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3) и рабочие процессы в Windows Workflow Foundation в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span><span class="sxs-lookup"><span data-stu-id="0189e-103">The <xref:System.Activities.Statements.Interop> activity can be used to execute activities from Windows Workflow Foundation (WF) in [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF3), and workflows within Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF4).</span></span> <span data-ttu-id="0189e-104">В этом образце описывается настройка и выполнение рабочего процесса WF3, использующего <xref:System.Workflow.Activities.ExternalDataExchangeService> (и соответствующих настраиваемых действий для вызова методов и обработки событий) с помощью действия <xref:System.Activities.Statements.Interop> в службе рабочего процесса WF4.</span><span class="sxs-lookup"><span data-stu-id="0189e-104">This sample shows how to configure and run a WF3 workflow that uses <xref:System.Workflow.Activities.ExternalDataExchangeService> (and corresponding custom activities for calling methods and handling events) by using the <xref:System.Activities.Statements.Interop> activity in a WF4 workflow service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0189e-105">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0189e-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0189e-106">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0189e-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0189e-107">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="0189e-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0189e-108">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0189e-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="0189e-109">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="0189e-109">To use this sample</span></span>  
  
1.  <span data-ttu-id="0189e-110">Откройте файл ExternalDataExchange.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0189e-110">Open the ExternalDataExchange.sln file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="0189e-111">Для построения образца нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="0189e-111">To build the sample, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="0189e-112">Нажмите клавишу F5, чтобы запустить образец.</span><span class="sxs-lookup"><span data-stu-id="0189e-112">To run the sample, press F5.</span></span>
