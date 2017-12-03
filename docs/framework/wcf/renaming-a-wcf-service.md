---
title: "Переименование службы WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c2ecd78a7d72b86460f4d1972c42c8550010f02
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="dcad1-102">Переименование службы WCF</span><span class="sxs-lookup"><span data-stu-id="dcad1-102">Renaming a WCF Service</span></span>
<span data-ttu-id="dcad1-103">В данном разделе описывается, как переименовать службу [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcad1-103">This topic describes how you can rename a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="dcad1-104">Переименование службы WCF</span><span class="sxs-lookup"><span data-stu-id="dcad1-104">Renaming a WCF Service</span></span>  
 <span data-ttu-id="dcad1-105">Выполните следующие действия для переименования службы в шаблоне [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcad1-105">Perform the following steps to rename a service in a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] template,</span></span>  
  
-   <span data-ttu-id="dcad1-106">Измените имя класса, реализующего службу.</span><span class="sxs-lookup"><span data-stu-id="dcad1-106">Change the name of the class that implements the service.</span></span>  
  
-   <span data-ttu-id="dcad1-107">В файле конфигурации службы измените имя службы на новое выбранное имя, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dcad1-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="dcad1-108">В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.</span><span class="sxs-lookup"><span data-stu-id="dcad1-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
-   <span data-ttu-id="dcad1-109">Если служба размещена на веб-сайте, то она использует файл *.svc.</span><span class="sxs-lookup"><span data-stu-id="dcad1-109">If your service is webhosted, it uses an *.svc file.</span></span> <span data-ttu-id="dcad1-110">Откройте SVC-файл и измените имя службы, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dcad1-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="dcad1-111">Этот шаг необязателен для резидентных приложений, так как у них нет SVC-файла.</span><span class="sxs-lookup"><span data-stu-id="dcad1-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```  
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="dcad1-112">Переименование контракта службы WCF</span><span class="sxs-lookup"><span data-stu-id="dcad1-112">Renaming a WCF Service Contract</span></span>  
  
-   <span data-ttu-id="dcad1-113">Выполните следующие действия для переименования контракта службы.</span><span class="sxs-lookup"><span data-stu-id="dcad1-113">Perform the following steps to rename the service contract,</span></span>  
  
-   <span data-ttu-id="dcad1-114">Измените имя контракта службы.</span><span class="sxs-lookup"><span data-stu-id="dcad1-114">Change the name of the service contract.</span></span>  
  
-   <span data-ttu-id="dcad1-115">В файле конфигурации службы измените имя контракта службы на новое выбранное имя, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dcad1-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="dcad1-116">В зависимости от модели размещения файлом конфигурации может быть файл app.config или файл web.config.</span><span class="sxs-lookup"><span data-stu-id="dcad1-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
