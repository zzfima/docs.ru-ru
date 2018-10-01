---
title: 'Устранение неполадок: невозможно установить приложение-службу'
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
author: ghogen
ms.openlocfilehash: 0912ff0909ffa5b22bed07543a2e514de4fb1ff5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47208016"
---
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="91521-102">Устранение неполадок: невозможно установить приложение-службу</span><span class="sxs-lookup"><span data-stu-id="91521-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="91521-103">Если приложение-служба не устанавливается надлежащим образом, убедитесь, что для свойства <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> класса службы задано значение, которое отображается в установщике этой службы.</span><span class="sxs-lookup"><span data-stu-id="91521-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="91521-104">Для правильной установки службы необходимо, чтобы эти значения совпадали.</span><span class="sxs-lookup"><span data-stu-id="91521-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91521-105">Сведения о ходе установки также можно найти в журналах установки.</span><span class="sxs-lookup"><span data-stu-id="91521-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="91521-106">Также убедитесь, что у вас не установлена другая служба с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="91521-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="91521-107">Для успешной установки необходимо, чтобы у каждой службы было уникальное имя.</span><span class="sxs-lookup"><span data-stu-id="91521-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91521-108">См. также</span><span class="sxs-lookup"><span data-stu-id="91521-108">See Also</span></span>  
 [<span data-ttu-id="91521-109">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="91521-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
