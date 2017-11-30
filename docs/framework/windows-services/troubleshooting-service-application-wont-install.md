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
ms.openlocfilehash: 82eb870761a7865385631cd9961ce99e0b0d3502
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="8a779-102">Устранение неполадок: Реализовано службы приложения &#39; Установка t</span><span class="sxs-lookup"><span data-stu-id="8a779-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="8a779-103">Если приложение службы не устанавливается правильно, проверьте, убедитесь, что <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> свойства для класса службы имеет значение то же значение, как показано в программе установки для этой службы.</span><span class="sxs-lookup"><span data-stu-id="8a779-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="8a779-104">Значение должно быть одинаковым в обоих случаях для правильной установки службы.</span><span class="sxs-lookup"><span data-stu-id="8a779-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a779-105">Можно также найти журналы установки, чтобы получить отзывы о ходе процесса установки.</span><span class="sxs-lookup"><span data-stu-id="8a779-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="8a779-106">Необходимо также проверить, чтобы убедиться, что другая служба с таким именем уже установлен.</span><span class="sxs-lookup"><span data-stu-id="8a779-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="8a779-107">Имена служб должны быть уникальными для успешной установки.</span><span class="sxs-lookup"><span data-stu-id="8a779-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a779-108">См. также</span><span class="sxs-lookup"><span data-stu-id="8a779-108">See Also</span></span>  
 [<span data-ttu-id="8a779-109">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="8a779-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
