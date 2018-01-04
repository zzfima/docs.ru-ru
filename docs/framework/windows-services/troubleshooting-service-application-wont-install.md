---
title: "Устранение неполадок: Реализовано службы приложения &#39; Установка t"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 43c973d83d2d1b614cf0ce49ba8d4af24123b47e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="41220-102">Устранение неполадок: Реализовано службы приложения &#39; Установка t</span><span class="sxs-lookup"><span data-stu-id="41220-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="41220-103">Если приложение службы не устанавливается правильно, проверьте, убедитесь, что <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> свойства для класса службы имеет значение то же значение, как показано в программе установки для этой службы.</span><span class="sxs-lookup"><span data-stu-id="41220-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="41220-104">Значение должно быть одинаковым в обоих случаях для правильной установки службы.</span><span class="sxs-lookup"><span data-stu-id="41220-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41220-105">Можно также найти журналы установки, чтобы получить отзывы о ходе процесса установки.</span><span class="sxs-lookup"><span data-stu-id="41220-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="41220-106">Необходимо также проверить, чтобы убедиться, что другая служба с таким именем уже установлен.</span><span class="sxs-lookup"><span data-stu-id="41220-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="41220-107">Имена служб должны быть уникальными для успешной установки.</span><span class="sxs-lookup"><span data-stu-id="41220-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41220-108">См. также</span><span class="sxs-lookup"><span data-stu-id="41220-108">See Also</span></span>  
 [<span data-ttu-id="41220-109">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="41220-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
