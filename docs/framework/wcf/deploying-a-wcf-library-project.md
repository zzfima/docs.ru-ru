---
title: "Развертывание проекта библиотеки WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04567b0b06ef5c8f105e866e150bfaa221d64057
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="deploying-a-wcf-library-project"></a><span data-ttu-id="5a6ec-102">Развертывание проекта библиотеки WCF</span><span class="sxs-lookup"><span data-stu-id="5a6ec-102">Deploying a WCF Library Project</span></span>
<span data-ttu-id="5a6ec-103">В данном разделе описывается развертывание проекта библиотеки службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a6ec-103">This topic describes how you can deploy a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Library Project.</span></span>  
  
## <a name="deploying-a-wcf-service-library"></a><span data-ttu-id="5a6ec-104">Развертывание библиотеки службы WCF</span><span class="sxs-lookup"><span data-stu-id="5a6ec-104">Deploying a WCF Service Library</span></span>  
 <span data-ttu-id="5a6ec-105">Библиотека службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] - это динамически подключаемая библиотека (DLL).</span><span class="sxs-lookup"><span data-stu-id="5a6ec-105">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library is a dynamic-link library (DLL).</span></span> <span data-ttu-id="5a6ec-106">Поэтому она не может выполняться сама по себе.</span><span class="sxs-lookup"><span data-stu-id="5a6ec-106">As such, it cannot be executed on its own.</span></span> <span data-ttu-id="5a6ec-107">Ее необходимо развернуть в среде размещения.</span><span class="sxs-lookup"><span data-stu-id="5a6ec-107">It needs to be deployed into a hosting environment.</span></span> <span data-ttu-id="5a6ec-108">Дополнительные сведения об этом процессе см. в разделе [размещение и использование служб WCF](http://go.microsoft.com/fwlink/?LinkId=99932).</span><span class="sxs-lookup"><span data-stu-id="5a6ec-108">For more information about this process, see [Hosting and Consuming WCF Services](http://go.microsoft.com/fwlink/?LinkId=99932).</span></span>  
  
 <span data-ttu-id="5a6ec-109">Библиотека службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] может быть развернута как любая другая служба [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a6ec-109">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library can be deployed like any other [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="5a6ec-110">Однако следует помнить, что [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] не поддерживает конфигурацию для DLL-библиотек.</span><span class="sxs-lookup"><span data-stu-id="5a6ec-110">However, be aware that [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] does not support configuration for DLLs.</span></span> <span data-ttu-id="5a6ec-111"><xref:System.Configuration> поддерживает один файл конфигурации на домен приложений.</span><span class="sxs-lookup"><span data-stu-id="5a6ec-111"><xref:System.Configuration> supports one configuration file per app-domain.</span></span> <span data-ttu-id="5a6ec-112">Проект библиотеки служб [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] снимает это ограничение путем предоставления файла App.config для библиотеки при развертывании.</span><span class="sxs-lookup"><span data-stu-id="5a6ec-112">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service library project alleviates this limitation by providing an App.config file for the library during development.</span></span> <span data-ttu-id="5a6ec-113">Однако файл App.config после развертывания не распознается.</span><span class="sxs-lookup"><span data-stu-id="5a6ec-113">However, the App.config file is not recognized after deployment.</span></span>  
  
 <span data-ttu-id="5a6ec-114">Необходимо переместить код конфигурации в файл конфигурации, который распознается средой размещения.</span><span class="sxs-lookup"><span data-stu-id="5a6ec-114">You have to move your configuration code into the configuration file recognized by your hosting environment.</span></span> <span data-ttu-id="5a6ec-115">Для резидентного размещения необходимо скопировать содержимое файла App.config в файл App.config исполняемого файла размещения.</span><span class="sxs-lookup"><span data-stu-id="5a6ec-115">For self-hosting, you should copy the contents of the App.config file into the App.config file of the hosting executable.</span></span> <span data-ttu-id="5a6ec-116">Если для размещения службы используется узел IIS, то необходимо копировать содержимое файла App.config в файл Web.config виртуального каталога.</span><span class="sxs-lookup"><span data-stu-id="5a6ec-116">If you use IIS to host your service, you should copy the contents of the App.config file into the Web.config file of the virtual directory.</span></span>
