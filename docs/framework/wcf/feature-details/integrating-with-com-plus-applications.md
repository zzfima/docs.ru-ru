---
title: "Интеграция с приложениями COM+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, reusing code
- Windows Communication Foundation, reusing code
- Windows Communication Foundation, COM+ integration
- COM+ [WCF], Windows Communication Foundation integration
- COM+ [WCF]
- WCF, COM+ integration
ms.assetid: 98bf7dc4-d49a-4129-a59b-db7a7ec8c241
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a29b28608c9ca16dd5a2023bd3d9e135618d753
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="a1c9f-102">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="a1c9f-102">Integrating with COM+ Applications</span></span>
<span data-ttu-id="a1c9f-103">Служба [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предоставляет среду с широкими возможностями для создания распределенных приложений.</span><span class="sxs-lookup"><span data-stu-id="a1c9f-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides a rich environment for creating distributed applications.</span></span> <span data-ttu-id="a1c9f-104">При существенном изменении логики приложения на основе компонентов, размещенного на COM+, можно использовать [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для расширения существующей логики вместо ее переписывания.</span><span class="sxs-lookup"><span data-stu-id="a1c9f-104">If you have a substantial investment in component-based application logic hosted in COM+, you can use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to extend your existing logic rather than having to rewrite it.</span></span> <span data-ttu-id="a1c9f-105">В подразделах этого раздела описываются способы использования COM+ c [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1c9f-105">The topics within this section describe how to use COM+ with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1c9f-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a1c9f-106">In This Section</span></span>  
 [<span data-ttu-id="a1c9f-107">Общие сведения об интеграции с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="a1c9f-107">Integrating with COM+ Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)  
 <span data-ttu-id="a1c9f-108">Даются общие сведения о том, где и как интегрировать компоненты COM+.</span><span class="sxs-lookup"><span data-stu-id="a1c9f-108">Gives an overview of when and how to integrate COM+ components.</span></span>  
  
 [<span data-ttu-id="a1c9f-109">Практическое руководство. Использование программы командной строки настройки модели служб COM+</span><span class="sxs-lookup"><span data-stu-id="a1c9f-109">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)  
 <span data-ttu-id="a1c9f-110">Объясняется, как с помощью программы командной строки настройки модели служб COM+ (ComSvcConfig.exe) выполнять настройку интерфейсов приложения, которые нужно представить как службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1c9f-110">Explains how to use the COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) to configure the application interfaces that you want exposed as [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
 [<span data-ttu-id="a1c9f-111">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="a1c9f-111">How to: Configure COM+ Service Settings</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)  
 <span data-ttu-id="a1c9f-112">Объясняется, как настроить объект COM+ как службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1c9f-112">Explains how to configure a COM+ object as a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 [<span data-ttu-id="a1c9f-113">Практическое руководство. Развертывание приложения интеграции COM+</span><span class="sxs-lookup"><span data-stu-id="a1c9f-113">How to: Deploy a COM+ Integration Application</span></span>](../../../../docs/framework/wcf/feature-details/how-to-deploy-a-com-integration-application.md)  
 <span data-ttu-id="a1c9f-114">Объясняется, как переместить приложение интеграции COM+.</span><span class="sxs-lookup"><span data-stu-id="a1c9f-114">Explains how to move a COM+ integration application.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a1c9f-115">Ссылка</span><span class="sxs-lookup"><span data-stu-id="a1c9f-115">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="a1c9f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a1c9f-116">See Also</span></span>  
 [<span data-ttu-id="a1c9f-117">Интеграция с приложениями COM</span><span class="sxs-lookup"><span data-stu-id="a1c9f-117">Integrating with COM Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications.md)
